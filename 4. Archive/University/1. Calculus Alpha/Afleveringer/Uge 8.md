
## Opgave U27

1. **Find den fuldstændige løsning til differentialligningen**
$$
y''-6y'-7y=0
$$

Når vi har en differentialligning
$$
ay''+by'+cy=0
$$
skal vi finde diskriminanten $D$
$$
D=b^{2}-4ac
$$
$$
D=(-6)^{2}-(4 \cdot -7)=64
$$
da $D > 0$ ved vi at den fuldstændige løsning er
$$
y(x)=Ae^{r_{1}x}+Be^{r_{2}x}
$$
hvor $r_{1}=\frac{-b+\sqrt{D}}{2a}$ og $r_{1}=\frac{-b-\sqrt{D}}{2a}$

Så hvis jeg sætter værdierne ind får vi
$$
r_{1}= \frac{-(-6)+\sqrt{64}}{2}=\frac{6+8}{2}=7
$$
$$
r_{2}=\frac{-(-6)-\sqrt{64}}{2}=\frac{6-8}{2}=-1
$$
Så derfor har vi at den fuldstændige løsning er
$$
y(x)=Ae^{7x}+Be^{-x}
$$

2. **Find den løsning $y$ til differentialligningen, der opfylder $y(0)=0$ og $y'(0)=8$**

Først kan jeg finde ud af hvad $A$ og $B$ skal være for at $y(0)=0$.
Da $e^{0}=1$ ved jeg at
$$
y(0)=A+B=0
$$
Nu skal jeg finde $y'(x)$
$$
y'(x)=7Ae^{7x}-Be^{-x}
$$
Herfra kan jeg finde $y'(0)=8$, så jeg nu har to ligninger med to ubekendte
$$
y'(0)=7A-B=8
$$
$$
y(0)=A+B=0
$$
Så kan jeg isolere $B$
$$
B=-A
$$
Så har vi at
$$
7A+A=8
$$
Her kan jeg regne ud at $A=1$ og jeg kan dermed finde $B$
$$
B=-1
$$

3. **Find den løsning $y$ til differentialligningen, der opfylder at $e^{x}y(x)=2$ for alle $x \in \mathbb{R}$.**

Vi kan sætte tallene ind og få
$$
e^{x}\cdot (Ae^{7x}+Be^{-x})=2
$$
$$
A\cdot 7e^{8x}-B=2
$$
Hvis vi sætter $A=0$ har vi at
$$
-B=2
$$
$$
B=-2
$$

## Opgave U28

1. **Find den løsning $y$ til den logistiske differentialligning**
$$
y'=y-2y^{2}
$$
**Som opfylder $y(0)=1$.**

Først skal jeg finde $y(x)$
Vi ved at når vi har en logistisk differentialligning
$$
y'(x)=by(x)-ay(x)^{2}
$$
Så er løsningen til ligningen ifølge Sætning 9.25
$$
y(x)=\frac{\frac{b}{a}}{1+Ae^{-bx}}
$$
Derfor har vi
$$
y(x)=\frac{\frac{1}{-2}}{1+Ae^{-x}}
$$
Nu skal jeg finde $A$
$$
y(0)=\frac{\frac{1}{-2}}{1+A}=1
$$
$$
\frac{1}{-2}=1+A
$$
$$
A=\frac{3}{-2}
$$

2. Lad $y$ være løsningen fra a(1). Find grænseværdien $\lim_{x \to \infty}y(x)$.

Vi ved at når vi lader $e^{-x}$ gå mod $-\infty$, får vi $0$.
Derfor kan vi fjerne leddet med $e^{-x}$
$$
\frac{\frac{1}{-2}}{1}=-\frac{1}{2}
$$
Derfor er
$$
\lim_{x \to \infty} y(x)=- \frac{1}{2}
$$
