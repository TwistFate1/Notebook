# LaTeX

## ǰ��

### ��չ��ʷ

> `Tex`
>
> - �ַ����滻
> - ������  
>
> `LaTex`
>
> - ������
> - ��ʽ����

### ���� texdoc

> �ĵ��鿴

### ��������

> Stack Overflow  
> LaTeX������

## ��ʽ����

### �ṹ���ĵ�

> ����

### �ĵ���д

> ����Ҫ�����ʽ��

### Markdown �� LYX

### �ĵ�����

���⣺\title, \author, \date, \maketitle  
ժҪ/ǰ�ԣ�abstract ����/ \chapter*  
Ŀ¼��\tableofcontents  
�½ڣ�\chapter, \section, ...  
��¼��\appendix + \chapter �� \section, ...  
���ף�\bibliography  
������\printindex  

### �ĵ�����

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

### �����ļ���֯

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

## ��д�ĵ�����

### LaTeX����

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

### �������

> Ӣ���Ƽ� pdflatex  
> �����Ƽ� xelatex

### �﷨�ṹ

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

### �����뻷��

- **����**

```LaTeX
\em abc
\emph{abc}
```

- **����**

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

### �����ı�

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

### ���ķ���

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

### ��ѧ��ʽ

һ����ѧ��ʽ���������ţ���Ҫ����ѧģʽ�����롣
ʾ����

```LaTeX
\documentclass{article}  
\begin{document}  
text $n=5$

text n=5
\end{document}
```

![Ԥ�����](./picture/formula.png)

- ���ڣ�inline����ʽ��ʹ��һ�Է���$$����ʾ��
- ��ʾ��display����ʽ��
  - �򵥵Ĳ���Ź�ʽ������\\[��\]\��ʾ������Ҫʹ��$$)
  - �����ı�ŵĹ�ʽ��quation����
  - �����ӵĽṹ��ʹ��amsmath����ṩ��ר�ŵ���ѧ����������Ҫʹ��eqnarray������

### ��ѧ�ṹ

- �ϱ���±꣺��^��_��ʾ��
- ���»����뻨���ţ�\overline,\underline,\overbrace,\underbrace
- ��ʽ��\frac{����}{��ĸ}
- ��ʽ��\sqrt[����]{������}
- ����ʹ�� amsmath ����ṩ��ר�ŵľ��󻷾� matrix��pmatrix��bmatrix�ȡ��ر��ӵľ������������ʹ��array������Ϊ��񻭳���

### ��ѧ����

- ��ѧ��ĸa,b,������ѧ����\mathbb��\mathcal��
- ��ͨ���ţ���\infty����angle
- ��Ԫ�������a+b��a-b��
- ��Ԫ��ϵ����a=b��
- ���ţ�\left��\right�Ŵ�
- ��㣺���š��ֺã�\colon��

### �Ƽ�����

- **��Ҫ�ظ�������**

> amsmath �� mathtools  
> siunitx�����ֵ�λ��һ���ӽ������  
> chemformula����д��ѧʽ

### �б���

- enumerate ���
- itemize �����
- description �б���

### �����໷��

- \newtheorem ���嶨���໷�����磺\newtheorem{thm}{����}[section]
- ʹ�ö����໷�����磺

  ```LaTeX
  \begin{thm}
  һ������
  \end{thm}
  ```

### ʫ��������

- verse
- quote
- quotation

### ��¼����

- \verb ����磺

  ```LaTeX
  ���� \verb|#include <iostream>|
  ```

- verbatim

  ```LaTeX
  \begin{verbatim}
  #include <stdio.h>
  int main() {
      puts("Hello World!");
      return 0;
  }
  \end{verbatim}
  ```

### �߼����룺�﷨����

- ʹ�� listings ���
- minted ��������� Pygment��

### �㷨�ṹ

- clrscode ������㷨���ۣ�
- algorithm2e ���
- algorithmicx ����� algpseudocode ��ʽ

### �����

ʹ�� tabular ������

```LaTeX
\begin{tabular}{|rr|}
\hline
���� & ��� \\ \hline
$-2$ & 4 \\
0 & 0 \\
2 & 4 \\ \hline\
\end{tabular}
```

![Ԥ�����](./picture/form.png)

### ���ܸ���ı����

- ��Ԫ����multirow��makecell
- �����longtable��xtab
- ������xtabular
- ���ֿ��ƣ�booktabs�����߱���diagbox��б�߱���arydshln
- ���и�ʽ��array
- �ۺ�Ӧ�ã�tabu

### ��ͼ

ʹ�� graphicx ����ṩ�� \includegraphics ���

```LaTeX
\includegraphics[Width=2cm]{�ļ���}
```

### ���뻭ͼ

�����ⲿ���߻�ͼ���ر��ǿ��ӻ����ߣ�pdf��ʽ������ѧͼ��ʹ��MATLAB�ȡ�  
ʹ�ú��ʵĺ�������� `LaTeX` ���뻭ͼ��

### ������

- figure ����
- table ����
- �������ڿ���ʹ�� float ���
������ı����� \caption ����õ����Զ���š�

### �Զ�������

- Ŀ¼�뽻������
- hyperref��PDF ����������ǩ
- �ο����� BibTeX
- �������׸�ʽ
  - ѡ����ʵ� `.bst` ��ʽ
  - natbib ������-���ʽ
  - ���� custom-bib �������Ƶĸ�ʽ�ļ�
  - biblatex + Biber�����״�����·�ʽ

### ����ĵ���ʽ

### ����ԭ��

~~��ʽ������Ҫ����~~��Ҫ����ϸ��  

### ʹ�ú��

����ʹ�ú����

- ������������
- �����ų�����Ҫ�ĺ��

### ��ʽ���ƹ���

#### �����ֺ�

����

- \rmfamily, \textrm{...}
- \sffamily, \textsf{...}
- \ttfamily, \texttt{...}  
�ֺţ�\Huge, \LARGE, \Large, \large,
\normalsize, \small, \footnotesize,
\scriptsize, \tiny  
�����ֺţ�\zihao{5}, \zihao{-3}

#### ����

\centering, \raggedleft, \raggedright

#### �հ׼��

\hspace{2cm}, \vspace{3cm}

#### ���沼��

geometry �����ֽ�ţ�
fancyhdr ��������棩

#### ��ҳ����

\linebreak, \\  
\pagebreak, \newpage, \clearpage, \cleardoublepage

#### ����

\mbox{����}  
\parbox{4em}{����}, minipage

### ��ʽӦ�����ĵ�

#### ʹ���ڵ������������ø�ʽ

Ԥ�����ʽ��������Ҫ��

- ֱ��������ز�����
- �޸Ĳ�������塣
- ���ù��ߺ��������á�

#### �����Զ�������ͻ���

����ʹ���Զ��������ͻ���ʵ������Ľӿڡ�

#### �½ڱ���

ctex ������ĵ��࣬�� \ctexset ���ơ�
