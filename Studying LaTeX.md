```Tex
\documentclass[UTF8]{ctexart}

\title{文章的标题}
\author{emt} 
\data{} 

\begin{document}

\maketitle

你好

\end{document}
```

- `\documentclass{}` 指定文档类型
	- `article` 普通文章
	- `book`
	- `ctexbook`
	- `report`
	- `beamer` 幻灯片
	- `ctexart` 中英文混排
- `\documentclass[UTF8]{ctexart}` 指定文档的编码类型
- 所有位于 `\begin{document}` 之前的内容都被称作是前言（preamble），像是 html 中的 head 标签
	- 可以在这里设置文档的格式
	- 页面的尺寸
	- 需要导入的宏包
- 介于 `\begin{document}` 和 `\end{document}` 之间的内容称为文档的正文
- `\title{}` 添加标题
- `\author{}` 作者署名
- `\data{\today}` 自动生成当天的日期
- 要显示这些东西还要在正文加上 `\maketitle`



- `\textbf{}` 加粗文字（bf：bold font）
- `\textit{}` 设置斜体字（it：italic）
- `\underline{}` 下划线
- 设置新段落：添加两个换行（一个换行只会编译成空格）
- `\part{}` 部
- `\chapter{}` 章
- `\section{}` 节
	- `subsection{}` 二级章节
		- `subsubsection{}` 三级章节



- `\usepackage{graphicx}` 图片
- `\includegraphics{width = 0.5\textwidth}{head}` head 是图片文件的名字
- 加标题

```tex
\begin{figure}
\centering \\居中显示
\includegraphics{width = 0.5\textwidth}{head}
\caption{ ... } \\标题名
\end{figure}
```


**无序列表**

```tex
\begin{itemize}
\item 列表项1
\item 列表项2
\item 列表项3
\end{itemize}
```

**有序列表**

```tex
\begin{enumerate}
\item
\end{enumerate}
```

**数学公式**

```tex
\begin{equation}
E = mc^2
\end{equation}


\[
E = mc^2
\]
```


**表格**

```tex
\begin{table}
\center
\begin{tabular}{|p{2 cm }|c|c|} \\居中对齐
\hline
1 & 2 & 3 \\
\hline
4 & 5 & 6 \\
\hline
7 & 8 & 9
\hline
\end{tabular}
\caption{标题}
\end{table}
```