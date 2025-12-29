# 环境 Environments

\| $\begin{matrix}
a & b \\
c & d
\end{matrix}$                 | `\begin{matrix} 
  a & b \\ 
  c & d 
\end{matrix}`        | $\begin{array}{cc}
   a & b \\
   c & d
\end{array}$                                                                           | `\begin{array}{cc}
  a & b \\
  c & d
\end{array}`                                                                        |
\| ------------------------------------------------------------ | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
\| $\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}$               | `\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}`         | $\begin{bmatrix}
   a & b \\
   c & d
\end{bmatrix}$                                                                           | `\begin{bmatrix}
  a & b \\
  c & d
\end{bmatrix}`                                                                        |
\| $\begin{vmatrix}
   a & b \\
   c & d
\end{vmatrix}$         | `\begin{vmatrix}
  a & b \\
  c & d
\end{vmatrix}`         | $\begin{Vmatrix}
   a & b \\
   c & d
\end{Vmatrix}$                                                                           | `\begin{Vmatrix}
  a & b \\
  c & d
\end{Vmatrix}`                                                                        |
\| $\begin{Bmatrix}
   a & b \\
   c & d
\end{Bmatrix}$         | `\begin{Bmatrix}
  a & b \\
  c & d
\end{Bmatrix}`         | $\def\arraystretch{1.5}
   \begin{array}{c:c:c}
   a & b & c \\ \hline
   d & e & f \\
   \hdashline
   g & h & i
\end{array}$ | `\def\arraystretch{1.5}
  \begin{array}{c:c:c}
  a & b & c \\ \hline
  d & e & f \\
  \hdashline
  g & h & i
\end{array}` |
\| $\begin{aligned}
   a&=b+c \\
   d+e&=f
\end{aligned}$       | `\begin{aligned}
  a&=b+c \\
  d+e&=f
\end{aligned}`       | $\begin{alignedat}{2}
   10&x+ &3&y = 2 \\
   3&x+&13&y = 4
\end{alignedat}$                                                   | `\begin{alignedat}{2}
  10&x+ &3&y = 2 \\
  3&x+&13&y = 4
\end{alignedat}`                                                |
\| $\begin{gathered}
   a=b \\
   e=b+c
\end{gathered}$         | `\begin{gathered}
  a=b \\
  e=b+c
\end{gathered}`         | $x = \begin{cases}
   a &\text{if } b \\
   c &\text{if } d
\end{cases}$                                                       | `x = \begin{cases}
  a &\text{if } b \\
  c &\text{if } d
\end{cases}`                                                    |
\| $\begin{smallmatrix}
   a & b \\
   c & d
\end{smallmatrix}$ | `\begin{smallmatrix}
  a & b \\
  c & d
\end{smallmatrix}` | $\begin{rcases}
   a &\text{if } b \\
   c &\text{if } d
\end{rcases}⇒…$                                                       | `\begin{rcases}
  a &\text{if } b \\
  c &\text{if } d
\end{rcases}⇒…`                                                    |


KaTeX 也支持 `darray`, `dcases`以及 `drcases`。

可用的行分隔符包括: `\`, `\cr`, `\[distance]`, 以及`\cr[distance]`。其中`Distance` 可与任意KaTeX单位联用。

`{array}` 支持`|`及 `:` 垂直分隔符，但目前不支持 `\cline`或者 `\multicolumn`。

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NTg3ODQwOTFdfQ==
-->