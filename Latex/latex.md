# LaTeX
## ��չ��ʷ
> `Tex`
>   - �ַ����滻
>   - ������  

> `LaTex`
>   - ������
>   - ��ʽ����

## ���� texdoc
> �ĵ��鿴

## ��������
> stackoverflow  
> Latex������

# ��ʽ����
## �ṹ���ĵ�
> ����

## �ĵ���д
> ����Ҫ�����ʽ��

## Markdown �� LYX

## �ĵ�����
���⣺\title, \author, \date, \maketitle  
ժҪ/ǰ�ԣ�abstract ����/ \chapter*  
Ŀ¼��\tableofcontents  
�½ڣ�\chapter, \section, ...  
��¼��\appendix + \chapter �� \section, ...  
���ף�\bibliography  
������\printindex  

## �ĵ�����
�����ĵ���\frontmatter��\mainmatter, \backmatter
һ���ĵ���\appendix

### �½ڲ��
| ��� | ���� | ���� | ˵�� |
| - | - | - | - |
| -1 | part | \part | ��ѡ����߲� |
| 0 | chapter | \chapter | report, book ����߲� |
| 1 | section | \section | article ����߲� |
| 2 | subsection | \subsection |  |
| 3 | subsubsection | \subsubsection | report, book �࣬Ĭ�ϲ���š�����Ŀ¼|
| 4 | paragraph | \paragraph | Ĭ�ϲ���š�����Ŀ¼ |
| 5 | subparagraph | \subparagraph | Ĭ�ϲ���š�����Ŀ¼ |

## �����ļ���֯
�ļ�Ŀ¼�ṹ��
- ���ĵ��������ĵ���ܽṹ
- �������½ڻ��ֲ�ͬ���ļ�
- ʹ�õ��������ļ��͸�ʽ�ļ����ø�ʽ
- ��С�ļ����븴�ӵ�ͼ��

������
- \documentclass�������ĵ����ļ���.cls��
- \usepackage: ����һ����ʽ�ļ����������.sty��
- \include����ҳ���������½��ļ���.tex��
- \input������������ļ�

�ĵ����ʾ��
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

# ��д�ĵ�����
## LaTeX����
```LaTex
\documentclass{ctexart}  
\begin{document}  
��ã�
\end{document}
```
![Ԥ��Ч��](./picture/Hello.png)

```LaTex
\documentclass{article}  
\begin{document}  
Hello World!
\end{document}
```
![Ԥ��Ч��](./picture/World.png)

## �������
> Ӣ���Ƽ� pdflatex  
> �����Ƽ� xelatex

## �﷨�ṹ
��Թ̶�����ʽ
- ����������ں��滨���ű�ʾ���������ű�ʾ��ѡ����
  ```LaTeX
  \cmd{arg1}{arg2}\\  
  \cmd[opt]{arg1}{arg2}  
  LaTeX�ķ���1/2 \frac{1}{2}  
  Tex�ķ���1/2 \over 2
  ```
- ���� 
  ```LaTeX
  \begin{env}  
    ...
  \end{env}
  LaTeX�ľ��� \begin{matrix} ... \\ ... \end{matrix}  
  Tex�ľ��� \matrix{...\cr ...\cr}
  ```

## �����뻷��
**����**
```LaTeX
\em abc
\emph{abc}
```
**����**
```LaTeX
\begin{env}
  ��������
\end{env}
```
���磺
```LaTeX
\begin{flushright}
����
\end{flushright}
```

## �����ı�
> �ո�ֿ�����

```LaTeX
\documentclass{article}  
\begin{document}  
aa bb cc
dd ee ff
\end{document}
```
![Ԥ�����](./picture/no.png)

```LaTeX
\documentclass{article}  
\begin{document}  
aa bb cc

dd ee ff
\end{document}
```
![Ԥ�����](./picture/yes.png)

## ���ķ���
һЩ���ű� `LaTeX` ������ռ�ã���Ҫ��������ʽ���룺
```LaTex
\# \$ \% \& \{ \}
\textbacklash
```
������û�еķ������������롣
```LaTeX
\S \dag \ddag \P \copyright
\textbullet \textregistered
\texttrademark \pounds
```
����ķ�����Ҫʹ�÷�������������鿴 symbols �ĵ���

## ��ѧ��ʽ
һ����ѧ��ʽ���������ţ���Ҫ����ѧģʽ�����롣