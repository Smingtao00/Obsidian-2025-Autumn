约定：字符串下标以 $0$ 起点

### 定义
对于一个长度为 $n$ 的字符串 $s$，定义函数 $z[i]$ 表示 $s$ 和 $s[i, n-1]$ （即以 $s[i]$ 开头的后缀）的最长公共前缀（LCP）的长度，则 $z$ 被称为 $s$ 的 $Z$ 函数。特别地，$z[0] = 0$。

### 线性算法
如同大多数字符串主题所介绍的算法，其关键在于，运用自动机的思想寻找限制条件下的状态转移函数，使得可以借助之前的状态来加速计算新的状态。

在该算法中，我们从 $1$ 到 $n-1$ 顺次计算 $z[i]$ 的值（$z[0] = 0$）。在计算 $z[i]$ 的过程中，我们会利用已经计算好的 $z[0],\dots, z[i-1]$。

对于 $i$，我们称区间 $[i, i + z[i] - 1]$ 是 $i$ 的 **匹配段**，也可以叫 $Z-box$。

算法的过程中我们维护右端点最靠右的匹配段。为了方便，记作 $[l, r]$。根据定义， $s[l, r]$ 是 $s$ 的前缀。在计算 $z[i]$ 时我们保证 $l \leq i$。初始时 $l = r = 0$。

在计算 $z[i]$ 的过程中：

- 如果 $i \leq r$，那么根据 $[l, r]$ 的定义有 $s[i, r]=s[i - l, r - l]$，（$s[0, r - l] = s[l, r]$）因此 $z[i] \geq \min(z[i - l],r - i + 1)$。此时：
	- 若 $z[i - l] < r - i + 1$，则 $z[i] = z[i - l]$。
	- 否则 $z[i - l] \geq r - i + 1$，这时我们令 $z[i] = r - i + 1$，然后暴力枚举下一个字符扩展 $z[i]$ 直到不能扩展为止。
- 如果 $i > r$，那么我们直接按照朴素算法，从 $s[i]$ 开始比较，暴力求出 $z[i]$。
- 在求出 $z[i]$ 后，如果 $i + z[i] - 1 > r$，我们就需要更新 $[l,r]$，即令 $l = i, r = i + z[i] - 1$。

```c++
vector<int> z_function(string s) {
	int n = (int)s.length();
	vector<int> z(n);
	for (int i = 1, l = 0, r = 0; i < n; i++) {
		if (i <= r && z[i - l] < r - i + 1)	{
			z[i] = z[i - l];	
		} else {
			z[i] = max(0, r - i + 1);
			while(i + z[i] < n && s[z[i]] == s[i + z[i]]) ++z[i];
		}
		if (i + z[i] - 1 > r) l = r, r = i + z[i] - 1;
	}
	return z;
}
```

另一种常数大一些的写法：

```c++
vector<int> z_function(string s) {
	int n = (int)s.length();
	vector<int> z(n, 0);
	for (int i = 1, l = 0, r = 0; i < n; i++) {
		if (i <= r) z[i] = min(z[i - l], r - i + 1);
		while (i + z[i] < n && s[z[i]] == s[i + z[i]]) ++z[i];
		if (i + z[i] - 1 > r) l = i, r = i + z[i] - 1;	
	}
}
```

```python
def z_function(s):
	n = len(s)
	z = [0] * n
	l, r = 0, 0
	for i in range(1, n):
		if i <= r and z[i - l] < r - i + 1:
			z[i] = z[i - l]
		else:
			z[i] = max(0, r - i + 1)
			while i + z[i] < n and s[z[i]] == s[i + z[i]]:
				z[i] += 1
		if i + z[i] - 1 > r:
			l = i
			r = i + z[i] - 1;
	return z	
```


### 复杂度分析

对于内层 `while` 循环，每次执行都会使得 $r$ 向后移动至少 $1$ 位，而 $r < n - 1$，所以总共只会执行 $n$ 次。

对于外层循环，只有一遍线性遍历。

总复杂度为 $O(n)$。