## Opgave 5.21
**Nedenstående diagram angiver et vejnet med ensrettede veje og 66 knudepunkter. Hver vej indeholder et tal, som angiver det gennemsnitlige antal biler per time på vejen. Nogle af disse tal $f_{1}, \ldots, f_{7}$ er dog angivet som ubekendte. Opstil et ligningssystem til at finde $f_{1}, \ldots, f_{7}$.**

![[Pasted image 20221028130248.png]]

**Find det gennemsnitlige antal biler per time på de ubekendte veje $f_1$, $f_2$, $f_3$, $f_4$, $f_5$, $f_6$ under forudsætning af at $f_1=200$ og $f_7=100$.**

For at opstille et ligningssystem til at finde $f_{1}, \ldots, f_{7}$ bruger jeg krydsene i vejsystemet.
$$
\begin{equation}
    \begin{cases}
300=f_{1}+f_{3} \\
f_{1}+300=f_{2}+f_{4} \\
f_{2}+f_{5}=600 \\
f_{3}+f_{6}=400 \\
f_{4}+f_{7}=f_{6}+200 \\
600=f_{5}+f_{7}
    \end{cases}
\end{equation}
$$
Herfra ved vi så at
$$
\begin{equation}
    \begin{cases}
f_{1}=200 \\
f_{2}=500-f_{4} \\
f_{3}=300-f_{1} \\
f_{4}=f_{6}+200-f_{7} \\
f_{5}=600-f_{2} \\
f_{6}=400-f_{3} \\
f_{7}=100
    \end{cases}
\end{equation}
$$
Og så kan jeg begynde at sætte værdierne ind
$$
\begin{equation}
    \begin{cases}
f_{1}=200 \\
f_{2}=500-f_{4}=100 \\
f_{3}=300-f_{1}=100 \\
f_{4}=f_{6}+200-f_{7}=400 \\
f_{5}=600-f_{2}=500 \\
f_{6}=400-f_{3}=300 \\
f_{7}=100
    \end{cases}
\end{equation}
$$
Og dermed har vi at de gennemsnitlige antal biler på de ubekendte veje $f_{1}, \ldots, f_{7}$ er
$$
\begin{equation}
    \begin{cases}
f_{1}=200 \\
f_{2}=100 \\
f_{3}=100 \\
f_{4}=400 \\
f_{5}=500 \\
f_{6}=300 \\
f_{7}=100
    \end{cases}
\end{equation}
$$
