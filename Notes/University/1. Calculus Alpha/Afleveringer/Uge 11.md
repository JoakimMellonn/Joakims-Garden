## Opgave 7.22
**Gør rede for alle trin i udregningen af determinanten**
$$
\text{det}
\begin{pmatrix}
1 & x_{0} & x_{0}^{2} & x_{0}^{3} \\ 
1 & x_{1} & x_{1}^{2} & x_{1}^{3} \\ 
1 & x_{2} & x_{2}^{2} & x_{2}^{3} \\ 
1 & x_{3} & x_{3}^{2} & x_{3}^{3}
\end{pmatrix}
$$
**For at nå frem til formen**
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{2}-x_{1})(x_{3}-x_{0})(x_{3}-x_{1})(x_{3}-x_{2})
$$

For at finde determinanten, kan jeg følge rækkeoperationerne på vejen til matricens RREF. Her ved vi at det eneste der ændrer determinanten er multiplikation og ombytning af rækker.

Jeg vil starte med at gøre dette for første række, her kan jeg gange tredje søjle med $x_{0}$ og trække det fra i fjerde søjle, når jeg gør dette får jeg nul i første række i samme søjle:
$$
\text{det}
\begin{pmatrix}
1 & x_{0} & x_{0}^{2} & 0 \\ 
1 & x_{1} & x_{1}^{2} & x_{1}^{3}-(x_{1}^{2}\cdot x_{0}) \\ 
1 & x_{2} & x_{2}^{2} & x_{2}^{3}-(x_{2}^{2}\cdot x_{0}) \\ 
1 & x_{3} & x_{3}^{2} & x_{3}^{3}-(x_{3}^{2}\cdot x_{0})
\end{pmatrix}
$$
Det samme kan jeg gøre med tredje søjle:
$$
\text{det}
\begin{pmatrix}
1 & x_{0} & 0 & 0 \\ 
1 & x_{1} & x_{1}^{2}-(x_{1}\cdot x_{0}) & x_{1}^{3}-(x_{1}^{2}\cdot x_{0}) \\ 
1 & x_{2} & x_{2}^{2}-(x_{2}\cdot x_{0}) & x_{2}^{3}-(x_{2}^{2}\cdot x_{0}) \\ 
1 & x_{3} & x_{3}^{2}-(x_{3}\cdot x_{0}) & x_{3}^{3}-(x_{3}^{2}\cdot x_{0})
\end{pmatrix}
$$
Og så anden søjle:
$$
\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
1 & x_{1}-x_{0} & x_{1}^{2}-(x_{1}\cdot x_{0}) & x_{1}^{3}-(x_{1}^{2}\cdot x_{0}) \\ 
1 & x_{2}-x_{0} & x_{2}^{2}-(x_{2}\cdot x_{0}) & x_{2}^{3}-(x_{2}^{2}\cdot x_{0}) \\ 
1 & x_{3}-x_{0} & x_{3}^{2}-(x_{3}\cdot x_{0}) & x_{3}^{3}-(x_{3}^{2}\cdot x_{0})
\end{pmatrix}
$$
Nu kan jeg så lave rækkeoperationer, så jeg trækker første række fra alle andre rækker:
$$
\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & x_{1}-x_{0} & x_{1}^{2}-(x_{1}\cdot x_{0}) & x_{1}^{3}-(x_{1}^{2}\cdot x_{0}) \\ 
0 & x_{2}-x_{0} & x_{2}^{2}-(x_{2}\cdot x_{0}) & x_{2}^{3}-(x_{2}^{2}\cdot x_{0}) \\ 
0 & x_{3}-x_{0} & x_{3}^{2}-(x_{3}\cdot x_{0}) & x_{3}^{3}-(x_{3}^{2}\cdot x_{0})
\end{pmatrix}
$$
Nu kan jeg så bruge multiplikation af en række med et tal, og rykke hhv. $x_{1}-x_{0}$, $x_{2}-x_{0}$ og $x_{3}-x_{0}$ ud og gange determinanten med det:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & x_{1} & x_{1}^{2} \\ 
0 & 1 & x_{2} & x_{2}^{2} \\ 
0 & 1 & x_{3} & x_{3}^{2}
\end{pmatrix}
$$
Nu kan jeg gøre som tidligere for at få nul i anden række:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & x_{1} & 0 \\ 
0 & 1 & x_{2} & x_{2}^{2}-(x_{2}\cdot x_{1}) \\ 
0 & 1 & x_{3} & x_{3}^{2}-(x_{3}\cdot x_{1})
\end{pmatrix}
$$
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 1 & x_{2}-x_{1} & x_{2}^{2}-(x_{2}\cdot x_{1}) \\ 
0 & 1 & x_{3}-x_{1} & x_{3}^{2}-(x_{3}\cdot x_{1})
\end{pmatrix}
$$
Og så kan jeg trække anden række fra i tredje og fjerde:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 0 & x_{2}-x_{1} & x_{2}^{2}-(x_{2}\cdot x_{1}) \\ 
0 & 0 & x_{3}-x_{1} & x_{3}^{2}-(x_{3}\cdot x_{1})
\end{pmatrix}
$$
Så kan jeg rykke hhv. $x_{2}-x_{1}$ og $x_{3}-x_{1}$ uden for og gange med determinanten:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})(x_{2}-x_{1})(x_{3}-x_{1})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 0 & 1 & x_{2} \\ 
0 & 0 & 1 & x_{3}
\end{pmatrix}
$$
Og så kan jeg trække tredje række fra fjerde:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})(x_{2}-x_{1})(x_{3}-x_{1})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 0 & 1 & 0 \\ 
0 & 0 & 0 & x_{3}-x_{2}
\end{pmatrix}
$$
Og til sidst kan jeg rykke $x_{3}-x_{2}$ ud og gange på determinanten:
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})(x_{2}-x_{1})(x_{3}-x_{1})(x_{3}-x_{2})\cdot\text{det}
\begin{pmatrix}
1 & 0 & 0 & 0 \\ 
0 & 1 & 0 & 0 \\ 
0 & 0 & 1 & 0 \\ 
0 & 0 & 0 & 1
\end{pmatrix}
$$
Så har vi at determinanten har formen
$$
(x_{1}-x_{0})(x_{2}-x_{0})(x_{3}-x_{0})(x_{2}-x_{1})(x_{3}-x_{1})(x_{3}-x_{2})
$$







---
For at finde determinanten af en matrice, kan man bruge Laplace-udvidelsen. Dette gøres ved at vælge en række eller en kolonne, og så udvide produkterne af de elementer, der er i den valgte række eller kolonne med de tilsvarende kofaktorer. Kofaktoren er det tal, der skal multipliceres med elementet, før det skal tilføjes til produktet.

I dette tilfælde kan vi vælge første række og udvide produkterne med de tilsvarende kofaktorer i første række. For det første element i første række, 1, vil kofaktoren være determinanten af matricen, der opstår, når man fjerner første række og første kolonne. Dette giver os følgende:

$$\det \begin{pmatrix} 1 & x_0 & x_0^2 & x_0^3\ 1 & x_1 & x_1^2 & x_1^3\ 1 & x_2 & x_2^2 & x_2^3\ 1 & x_3 & x_3^2 & x_3^3 \end{pmatrix} = 1 \cdot \det \begin{pmatrix} x_1 & x_1^2 & x_1^3\ x_2 & x_2^2 & x_2^3\ x_3 & x_3^2 & x_3^3 \end{pmatrix} - x_0 \cdot \det \begin{pmatrix} 1 & x_1^2 & x_1^3\ 1 & x_2^2 & x_2^3\ 1 & x_3^2 & x_3^3 \end{pmatrix} + x_0^2 \cdot \det \begin{pmatrix} 1 & x_1 & x_1^3\ 1 & x_2 & x_2^3\ 1 & x_3 & x_3^3 \end{pmatrix} - x_0^3 \cdot \det \begin{pmatrix} 1 & x_1 & x_1^2\ 1 & x_2 & x_2^2\ 1 & x_3 & x_3^2 \end{pmatrix}$$

Dernæst kan vi anvende Laplace-udvidelsen på de nye matricer for at udvide produkterne yderligere. Dette giver os følgende:

$$\begin{aligned} \det \begin{pmatrix} 1 & x_0 & x_0^2 & x_0^3\ 1 & x_1 & x_1^2 & x_1^3\ 1 & x_2 & x_2^2 & x_2^3\ 1 & x_3 & x_3^2 & x_3^3 \end{pmatrix} &= 1 \cdot \det \begin{pmatrix}