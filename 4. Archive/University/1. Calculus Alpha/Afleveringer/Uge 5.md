## Øvelse U19
Lad $f : \mathbb{R}^{2} \to \mathbb{R}$ være funktionen:
$$
f(x,y)=2x^{3}+y^{2}-24x-6y-5
$$

1. **Beregn de partielle afledede af funktionen $f$.**

Først differentierer jeg med hensyn til $x$, så jeg fjerner alle led hvor $x$ ikke er med, så har jeg:
$$
2x^{3}-24x
$$
Det kan så differentieres:
$$
\frac{\partial f}{\partial x}=6x^{2}-24
$$

Nu kan jeg gøre det samme med hensyn til y:
$$
y^{2}-6y
$$
$$
\frac{\partial f}{\partial y}=2y-6
$$


2. **Der er to kritiske punkter $(x_{1}, y_{0})$ og $(x_{2}, y_{0})$ for $f$, og de har samme anden koordinat $y_{0}$. Find $y_{0}$.**

For at finde $y_{0}$ kan jeg sætte den partielle afledede med hensyn til $y$ lig nul. 
$$
y_{0}=\frac{6}{2}=3
$$


3. **Beregn den største kritiske værdi, dvs. den største af de værdier som $f$ antager i de kritiske punkter.**

Ved de kritiske punkter kan $x$ enten være $2$ eller $-2$, så det kan jeg indsætte i funktionen:
$$
f(2,3)=-46
$$
$$
f(-2,3)=18
$$
Så den største kritiske værdi er i punktet $(-2,3)$.


4. **Lad $(x_{1}, y_{0})$ være det kritiske punkt hvori den største kritiske værdi antages. Beregn de dobbelt partielle afledede af $f$ i punktet $(x_{1}, y_{0})$.**

Først skal jeg finde de dobbelt partielle afledede af $f$:
$$
\frac{\partial^{2} f}{\partial x^{2}}=12x
$$
$$
\frac{\partial^{2} f}{\partial y^{2}}=2
$$
Nu kan jeg sætte værdierne fra punktet ind:
$$
\frac{\partial^{2} f}{\partial x^{2}}(-2,3)=-24
$$
$$
\frac{\partial^{2} f}{\partial y^{2}}(-2,3)=2
$$


5. **Udregn teststørrelsen $D$ i andenordenskriteriet for det kritiske punkt $(x_{1}, y_{0})$.**

Til at udregne $D$ kan jeg bruge sætning 3.59:
$$
D=\frac{\partial^{2} f}{\partial x^{2}}(x_{0}, y_{0})\frac{\partial^{2} f}{\partial y^{2}}(x_{0}, y_{0})-(\frac{\partial^{2} f}{\partial x \partial y}(x_{0}, y_{0}))^2
$$
Jeg mangler kun at finde $\frac{\partial^{2} f}{\partial x \partial y}$ og her ved jeg at:
$$
\frac{\partial^{2} f}{\partial x \partial y}= \frac{\partial \frac{\partial f}{\partial x}}{\partial y}
$$
Så hvis jeg differentierer $\frac{\partial f}{\partial x}$ med hensyn til $y$ får jeg:
$$
\frac{\partial^{2} f}{\partial x \partial y}= 0
$$

Så kan jeg udregne $D$ i det kritiske punkt $(-2,-3)$:
$$
D=-24 \cdot 2-0^{2}
$$
$$
D=-48
$$


6. **Om det kritiske punkt $(x_{1}, y_{0})$ gælder et af følgene alternativer. Hvilket?**
	1. Det er et lokalt minimum.
	2. Det er et lokalt maksimum.
	3. Det er et saddelpunkt.
	4. Det er ingen af de tre foregående altså hverken 1, 2 eller 3.

Her kan jeg fortsat benytte sætning 3.59, som siger at hvis $D < 0$ så er det et saddelpunkt.

7. **Bestem det positive tal $a$ som opfylder, at gradienten $\nabla f(a, \frac{5}{2})$ er en enhedsvektor.**

Vi har gradienten:
$$
\nabla f=(6x^{2}-24, 2y-6)
$$
Hvis jeg her indsætter $\frac{5}{2}$ på pladsen i gradienten får jeg:
$$
2 \cdot \frac{5}{2}-6=-1
$$
For at gradienten kan være en enhedsvektor, betyder det at vektoren kun kan bevæge sig $1$, så det vil sige at hvis man indsætter $a$ i gradienten, skal det give $0$.
$$
6a^{2}-24=0
$$
Her kan a både være positivt og negativt, men da vi skal bestemme det positive tal, så vil a være:
$$
a=2
$$

