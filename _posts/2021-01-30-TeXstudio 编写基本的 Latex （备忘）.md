---
layout: post
title: TeXstudio 编写基本的 Latex （备忘）
categories: [备忘]
description: 编写基本的 Latex 
keywords: TeXstudio, LaTeX
---

# 0. TeXstudio设置
- 保证为**UTF-8**
- 在选项卡 选项 中设置编译器为 **XeLaTeX**



# 1. 基本页面
## 简单的一个例子
```bash
\documentclass{ctexart}  %使用中文版的article文档类型排版
\begin{document}
	hello,world
	
	 你好，世界
\end{document}
```
## 来点章节

```bash
\documentclass{ctexart}  %使用中文版的article文档类型排版
\begin{document}
	\section{一级标题}
		hello,world
	 \subsection{二级标题}
	 你好，世界
	 \subsubsection{三级标题}
	 你好，世界
\end{document}
```
- 效果
![在这里插入图片描述](../images/blog/2021-01-30-TeXstudio%20%E7%BC%96%E5%86%99%E5%9F%BA%E6%9C%AC%E7%9A%84%20Latex%20%EF%BC%88%E5%A4%87%E5%BF%98%EF%BC%89/20200320154723745.png)
## 再加个简单封皮
- 代码
	

```bash
\documentclass{ctexart}  %使用中文版的article文档类型排版

\title{标题}
\author{作者}
\date{\today}%\today表示今天的日期

\begin{document}


	\maketitle%让前面的title，author，date生效
	\newpage%分页


	\section{一级标题}
		hello,world
	 \subsection{二级标题}
	 你好，世界
	 \subsubsection{三级标题}
	 你好，世界
\end{document}
```
- 封皮效果
	![在这里插入图片描述](../images/blog/2021-01-30-TeXstudio%20%E7%BC%96%E5%86%99%E5%9F%BA%E6%9C%AC%E7%9A%84%20Latex%20%EF%BC%88%E5%A4%87%E5%BF%98%EF%BC%89/20200320155742759.png)
	
	## 加个目录
有了分级标题就可以来生成目录了
	
	

> 		\tableofcontents

- 代码
	

```bash
\documentclass{ctexart}  %使用中文版的article文档类型排版

\title{标题}
\author{作者}
\date{\today}%\today表示今天的日期

\begin{document}
	\maketitle
	\newpage
	
	\tableofcontents%目录
	\newpage
	
	\section{一级标题}
		hello,world
	 \subsection{二级标题}
	 你好，世界
	 \subsubsection{三级标题}
	 你好，世界
\end{document}
```
- 效果
	![在这里插入图片描述](../images/blog/2021-01-30-TeXstudio%20%E7%BC%96%E5%86%99%E5%9F%BA%E6%9C%AC%E7%9A%84%20Latex%20%EF%BC%88%E5%A4%87%E5%BF%98%EF%BC%89/20200320160510245.png)
	
	# 小细节
	- `\\` 换行
	- 两个句子之间空一行就相当于分段了