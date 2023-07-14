# LaTeX
## 发展历史
> `Tex`
>   - 字符串替换
>   - 宏语言  

> `LaTex`
>   - 宏命令
>   - 格式语言

## 命令 texdoc
> 文档查看

## 社区交流
> stackoverflow  
> Latex工作室

# 正式部分
## 结构化文档
> 内容

## 文档编写
> 不需要在意格式化

## Markdown 与 LYX

## 文档部件
标题：\title, \author, \date, \maketitle  
摘要/前言：abstract 环境/ \chapter*  
目录：\tableofcontents  
章节：\chapter, \section, ...  
附录：\appendix + \chapter 或 \section, ...  
文献：\bibliography  
索引：\printindex  

## 文档划分
大型文档：\frontmatter，\mainmatter, \backmatter
一般文档：\appendix

### 章节层次
| 层次 | 名称 | 命令 | 说明 |
| - | - | - | - |
| -1 | part | \part | 可选的最高层 |
| 0 | chapter | \chapter | report, book 类最高层 |
| 1 | section | \section | article 类最高层 |
| 2 | subsection | \subsection |  |
| 3 | subsubsection | \subsubsection | report, book 类，默认不编号、不编目录|
| 4 | paragraph | \paragraph | 默认不编号、不编目录 |
| 5 | subparagraph | \subparagraph | 默认不编号、不编目录 |

## 磁盘文件组织
文件目录结构：
- 主文档，给出文档框架结构
- 按内容章节划分不同的文件
- 使用单独的类文件和格式文件设置格式
- 用小文件隔离复杂的图表

相关命令：
- \documentclass；读入文档类文件（.cls）
- \usepackage: 读入一个格式文件——宏包（.sty）
- \include；分页，并读入章节文件（.tex）
- \input：读入任意的文件

文档框架示例
```LaTex
% langage-main.tex  
\documentclass{book}  
\usepackage{makeidx}  
\makeindex  
\title{Languages}  
\author{someone}  
\begin{documet}  
\frontmatter  
\maketitle  
\tableofcontents  
\mainmatter  
\include{intro}  
\include{class}  
\backmatter  
\include{appendix}  
\bibliography{foo}  
\printindex  
\end{document}

% intro.tex
\part{Introduction}
  \chapter{Background}

% class.tex
\part{Classification}
  \chapter{Natural Language}
  \chapter{Computer Languages}
    \section{Machine Languages}
    \section{High Level Languages}
      \subsection{Compiled Language}
      \subsection{Interpretative Language}
      \subsubsection{Lisp}
        \paragraph{Common Lisp}
        \paragraph{Scheme}
      \subsubsection{Perl}

% appendix.tex
\chapter{Appendix}
```

# 填写文档内容
## LaTeX基础
```LaTex
\documentclass{ctexart}  
\begin{document}  
你好！
\end{document}
```
![预览效果](./picture/Hello.png)

```LaTex
\documentclass{article}  
\begin{document}  
Hello World!
\end{document}
```
![预览效果](./picture/World.png)

## 具体编译
> 英文推荐 pdflatex  
> 中文推荐 xelatex

## 语法结构
相对固定的形式
- 命令：参数总在后面花括号表示，用中括号表示可选参数
  ```LaTeX
  \cmd{arg1}{arg2}\\  
  \cmd[opt]{arg1}{arg2}  
  LaTeX的分数1/2 \frac{1}{2}  
  Tex的分数1/2 \over 2
  ```
- 环境 
  ```LaTeX
  \begin{env}  
    ...
  \end{env}
  LaTeX的矩阵 \begin{matrix} ... \\ ... \end{matrix}  
  Tex的矩阵 \matrix{...\cr ...\cr}
  ```

## 命令与环境
**命令**
```LaTeX
\em abc
\emph{abc}
```
**环境**
```LaTeX
\begin{env}
  环境内容
\end{env}
```
例如：
```LaTeX
\begin{flushright}
文字
\end{flushright}
```

## 正文文本
> 空格分开单词

```LaTeX
\documentclass{article}  
\begin{document}  
aa bb cc
dd ee ff
\end{document}
```
![预览结果](./picture/no.png)

```LaTeX
\documentclass{article}  
\begin{document}  
aa bb cc

dd ee ff
\end{document}
```
![预览结果](./picture/yes.png)

## 正文符号
一些符号被 `LaTeX` 宏语言占用，需要以命令形式输入：
```LaTex
\# \$ \% \& \{ \}
\textbacklash
```
键盘上没有的符号用命令输入。
```LaTeX
\S \dag \ddag \P \copyright
\textbullet \textregistered
\texttrademark \pounds
```
更多的符号需要使用符号字体包。（查看 symbols 文档）

## 数学公式
一切数学公式（包括符号）都要在数学模式下输入。