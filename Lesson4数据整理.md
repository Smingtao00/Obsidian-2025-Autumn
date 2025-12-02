# Lesson4: 数据整理

---

## sed

`sed`是一个基于文本编辑器`ed`构建的 “流编辑器” 。在`sed`中，您基本上是利用一些简短的命令来修改文件，而不是直接操作文件的内容（尽管您也可以选择这样做）。相关的命令行非常多，但是最常用的是`s`，即***替换***命令，例如我们可以这样写:

```bash
ssh myserver journalctl
 | grep sshd
 | grep "Disconnected from"
 | sed 's/.*Disconnected from //'ssh myserver journalctl
```

`s`命令的语法如下:`s/REGEX/SUBSTITUTION/`, 其中`REGEX`部分是我们需要使用的正则表达式，而 `SUBSTITUTION`是用于替换匹配结果的文本。

(**Vim** 使用的搜索和替换语法与`sed`的替换命令相似这一块)

---

## 浅谈正则表达式

`/.*Disconnexted from /`
正则表达式通常以`/`开始和结束

- `.`除换行符之外的 “任意单个字符”
- `*`匹配前面字符零次或多次
- `+`匹配前面字符一次或多次
- `-[abc]`匹配 a, b 和 c 中的任意一个
- `(RX1|RX2)`任何能够匹配 RX1 或 RX2 的结果
- `^`行首
- `$`行尾

`sed`的正则表达式有时候需要你在这些模式前添加`\`才能使其具有特殊含义。或者，也可以添加`-E`选项来支持这些匹配。("sed is stupid"说是= =)

<mark>注意:</mark>`*`和`+`在默认情况下是贪婪模式，也就是说它们会尽可能多的匹配文本,可以在其后加一个`?`以转变为非贪婪模式

---

## Other Things

```bash
ssh myserver journalctl
 | grep sshd
 | grep "Disconnected from"
 | sed -E 's/.*Disconnected from (invalid |authenticating )?user (.*) [^ ]+ port [0-9]+( \[preauth\])?$/\2/'
 | sort | uniq -c
 | sort -nk1,1 | tail -n10
 ```

- `sort`会对其输入数据进行排序。`uniq -c`会把连续出现的行折叠为一行并使用出现次数作为前缀。

- `sort -n`会按照数字顺序对输入进行排序（默认情况下是按照字典序排序`-k1,1`则表示“仅基于以空格分割的第一列进行排序”。`n`部分表示“仅排序到第 n 个部分”，默认情况是到行尾。就本例来说，针对整个行进行排序也没有任何问题，我们这里主要是为了学习这一用法！
  
```bash
ssh myserver journalctl
 | grep sshd
 | grep "Disconnected from"
 | sed -E 's/.*Disconnected from (invalid |authenticating )?user (.*) [^ ]+ port [0-9]+( \[preauth\])?$/\2/'
 | sort | uniq -c
 | sort -nk1,1 | tail -n10
 | awk '{print $2}' | paste -sd,
 ```

- 我们可以用`paste`命令来合并行`-s`，并指定一个分隔符来进行分割`-d`

<mark>那么`awk`的作用又是什么呢？</mark>

---

## awk-另外一种编辑器

`awk`其实是一种编程语言，只不过它碰巧非常善于处理文本

首先，`{print $2}`的作用是什么？`awk`程序接受一个模式串（可选），以及一个代码块，指定当模式匹配时应该做何种操作。默认当模式串即匹配所有行（上面命令中当用法）。 在代码块中，`$0`表示整行的内容，`$1`到`$n`为一行中的`n` 个区域，区域的分割基于`awk`的域分隔符（默认是空格，可以通过 `-F` 来修改）。在这个例子中，我们的代码意思是：对于每一行文本，打印其第二个部分，也就是用户名。

让我们康康，还有什么炫酷的操作可以做。让我们统计一下所有以`c`开头，以`e`结尾，并且仅尝试过一次登录的用户。

```bash
 | awk '$1 == 1 && $2 ~ /^c[^ ]*e$/ { print $2 }' | wc -l
```

让我们好好分析一下。首先，注意这次我们为`awk`指定了一个匹配模式串（也就是`{...}`前面的那部分内容）。该匹配要求文本的第一部分需要等于`1`（这部分刚好是`uniq -c`得到的计数值），然后其第二部分必须满足给定的一个正则表达式。代码块中的内容则表示打印用户名。然后我们使用`wc -l`统计输出结果的行数。

不过，既然`awk`是一种编程语言，那么可以这样

```awk
BEGIN { rows = 0 }
$1 == 1 && $2 ~ /^c[^ ]*e$/ { rows += $1 }
END { print rows }
```

`BEGIN`也是一种模式，它会匹配输入的开头（`END`则匹配结尾）。然后，对每一行第一个部分进行累加，最后将结果输出。事实上，我们完全可以抛弃`grep`和`sed`，因为`awk` 就可以**解决所有问题**。

---

## 分析数据

- `bc`是Unix/Linux系统中一个强大的**任意精度计算器工具**,支持整数和浮点数运算，可以通过命令行进行数学计算，甚至能处理复杂的表达式和自定义函数。

```bash
bc -l <<< "scale=3; 22/7"  # 输出 3.142
echo "10^3" | bc           # 输出 1000
```

这样可以将每行的数字加起来:

```bash
 | paste -sd+ | bc -l
```

下面这种更加复杂的表达式也可以:

```bash
echo "2*($(data | paste -sd+))" | bc -l
```

- **浮点数运算**: 默认情况下`bc`做除法会取整，需要通过`scale`变量设置小鼠位数

```bash
scale=2        # 设置保留2位小数
15 / 4         # 输出 3.75
7 / 3          # 输出 2.33
```

- **使用数学函数**:
  
```bash
bash
bc -l          # 加载数学库
sqrt(25)       # 开方，输出 5.0000000000
sin(3.14159/2) # 正弦值（弧度），约等于 1.0000000000
l(10)          # 自然对数，约等于 2.3025850930
```

`bc`适合快速进行命令行下的数学计算，尤其适合需要高精度运算的场景。

- R 也是一种编程语言，它非常适合被用来进行数据分析和**绘制图表**。

```bash
ssh myserver journalctl
 | grep sshd
 | grep "Disconnected from"
 | sed -E 's/.*Disconnected from (invalid |authenticating )?user (.*) [^ ]+ port [0-9]+( \[preauth\])?$/\2/'
 | sort | uniq -c
 | awk '{print $1}' | R --slave -e 'x <- scan(file="stdin", quiet=TRUE); summary(x)'
```

- 如果希望绘制一些简单的图表，`gnuplot`可以帮助:

```bash
ssh myserver journalctl
 | grep sshd
 | grep "Disconnected from"
 | sed -E 's/.*Disconnected from (invalid |authenticating )?user (.*) [^ ]+ port [0-9]+( \[preauth\])?$/\2/'
 | sort | uniq -c
 | sort -nk1,1 | tail -n10
 | gnuplot -p -e 'set boxwidth 0.5; plot "-" using 1:xtic(2) with boxes'
```