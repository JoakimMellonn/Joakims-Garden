## Opgave 6.49
**Forklar hvorfor matricen**
$$
\begin{pmatrix}
1 & 4 & 5 \\ 
2 & 5 & 7 \\ 
3 & 6 & 9
\end{pmatrix}
$$
**Ikke er invertibel**

For at finde ud af om matricen er invertibel skal jeg finde determinanten af matricen:
$$
\text{det}
\begin{pmatrix}
1 & 4 & 5 \\ 
2 & 5 & 7 \\ 
3 & 6 & 9
\end{pmatrix}
$$
Ifølge sætning 7.3 har vi at determinanten er
$$
a_{11} \text{det}(A_{11})−⋯+(−1)^{i+1}a_{i1} \text{det}(A_{i1})+⋯+(−1)^{1+n}a_{n1} \text{det}(A_{n1})
$$
Derudfra har vi at i 3x3 matricer er determinanten det følgene
$$
\text{det}
\begin{pmatrix}
a_{11} & a_{12} & a_{13} \\ 
a_{21} & a_{22} & a_{23} \\ 
a_{31} & a_{32} & a_{33}
\end{pmatrix}
$$
$$
=a_{11}(a_{22}a_{33}-a_{32}a_{23})-a_{21}(a_{12}a_{33}-a_{32}a_{13})+a_{31}(a_{12}a_{23}-a_{22}a_{13})
$$
$$
=a_{11}a_{22}a_{33}+a_{12}a_{23}a_{31}+a_{13}a_{21}a_{32}-a_{13}a_{22}a_{31}-a_{12}a_{21}a_{33}-a_{11}a_{23}a_{32}
$$
Nu kan jeg sætte værdierne ind
$$
1\cdot5\cdot9+4\cdot7\cdot3+5\cdot2\cdot6-5\cdot5\cdot3-4\cdot2\cdot9-1\cdot7\cdot6
$$
Så ved jeg at
$$
\text{det}
\begin{pmatrix}
1 & 4 & 5 \\ 
2 & 5 & 7 \\ 
3 & 6 & 9
\end{pmatrix}
=45+84+60-75-72-42=0
$$
Så vi har at determinanten er $0$ og dermed ved vi fra sætning 7.7 at den ikke er invertibel, da en matrix $A$ er invertibel hvis og kun hvis $\text{det}(A) \not = 0$.


## Opgave 6.55
**Gør rede for at en kvadratisk matrix forskellig fra identitetsmatricen bliver nødt til at indeholde en nulrække hvis den er på RREF**

Hvis vi bruger definitionen på RREF (6.29) har vi følgende:
1. Nulrækker er i bunden af matricen.
2. Hvis en række i A ikke er en nulrække, så er den første indgang $\not =0$ i rækken tallet $1$. Denne indgang kaldes et pivotelement.
3. Et pivotelement er længere til højre end pivotelementerne i de foregående rækker.
4. Et pivotelement er den eneste indgang $\not = 0$ i sin søjle (kolonne).

Ifølge den tredje regel i definitionen har vi at pivotelementet i den givne række, altid er længere mod højre end pivotelementerne i de forgående rækker. Med det ved vi at i en kvadratisk matrix skal pivotelementet i første række altid være i første kolonne og i anden række, anden kolonne osv.
Når vi kommer ned til sidste række og har et pivotelement her, så er det en identitetsmatrice, da der ikke er andre muligheder i en kvadratisk matrix. Hvis ikke vi har et pivotelement i sidste række, vil det dermed være en nulrække.

Derfor er en kvadratisk matrix, der er forskellig fra identitetsmatricen, nødt til at indeholde en nulrække hvis den er på RREF.