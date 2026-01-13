\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[russian]{babel}
\usepackage{amsmath}
\usepackage{tikz}
\usetikzlibrary{shapes,patterns}

\begin{document}

\section*{Задание}
По заданному десятичному числу 132:
\begin{enumerate}
    \item Перевести его в двоичную форму
    \item Заштриховать на диаграмме Эйлера для трёх взаимно пересекающихся множеств \(A, B, C\) соответствующую область
    \item Записать эту область в виде объединения конституэнт
\end{enumerate}

\section*{Решение}

\subsection*{1. Перевод числа 132 в двоичную систему}
\[
\begin{aligned}
132 \div 2 &= 66, \text{ ост. } 0 \\
66 \div 2 &= 33, \text{ ост. } 0 \\
33 \div 2 &= 16, \text{ ост. } 1 \\
16 \div 2 &= 8, \text{ ост. } 0 \\
8 \div 2 &= 4, \text{ ост. } 0 \\
4 \div 2 &= 2, \text{ ост. } 0 \\
2 \div 2 &= 1, \text{ ост. } 0 \\
1 \div 2 &= 0, \text{ ост. } 1
\end{aligned}
\]

\[
132_{10} = 10000100_2
\]

\subsection*{2. Определение номера области}
Младшие три бита: \(100_2 = 4_{10}\).

Область с кодом \(100\): 
\[
A=1,\ B=0,\ C=0 \quad\Rightarrow\quad A \cap \overline{B} \cap \overline{C}
\]

\subsection*{3. Диаграмма Эйлера}
\begin{center}
\begin{tikzpicture}[scale=0.8]
    \draw[fill=gray!30] (0,0) circle (1.5) node[above] {\(A\)};
    \draw (1.5,0) circle (1.5) node[above] {\(B\)};
    \draw (0.75,-1.3) circle (1.5) node[below] {\(C\)};
    
    \node at (-0.8,0.5) {\(100\)};
    \fill[pattern=north east lines] (0,0) circle (1.5);
    \begin{scope}
        \clip (1.5,0) circle (1.5);
        \clip (0.75,-1.3) circle (1.5);
        \fill[white] (0,0) circle (1.5);
    \end{scope}
    \begin{scope}
        \clip (0,0) circle (1.5);
        \fill[white] (1.5,0) circle (1.5);
    \end{scope}
\end{tikzpicture}
\end{center}

\subsection*{4. Объединение конституэнт}
\[
\boxed{A \cap \overline{B} \cap \overline{C}}
\]

\end{document}
