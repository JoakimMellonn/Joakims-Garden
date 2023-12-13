## I denne opgave betragtes funktionen
$$
f(x,y)=4x^{2}y+5xy^{2}+x^{3}
$$

1. **Beregn den partielle afledte $f_y$ af funktionen $f$ med hensyn til $y$.**
$$
f_{y}=4x^{2}+10xy
$$


2. **Beregn gradienten $\nabla f(x,y)$ af funktionen $f$**

For at finde gradient, skal jeg også bruge den partielle afledte af $f$ med hensyn til $x$.
$$
f_{x}=3x^{2}+8xy+5y^{2}
$$
Nu kan jeg så finde gradienten.
$$
\nabla f(x,y)=(3x^{2}+8xy+5y^{2},4x^{2}+10xy)
$$


3. **Angiv enhedsvektoren $\overline{u}$ i retningen givet ved vektoren $(8,-6)$.**

Med bemærkning 3.7 ved vi at enhedsvektoren for en vektor findes ved:
$$
\overline{u}=\frac{1}{\sqrt{a^{2}+b^{2}}}(a,b)=(\frac{a}{\sqrt{a^{2}+b^{2}}}, \frac{b}{\sqrt{a^{2}+b^{2}}})
$$
Herfra kan jeg sætte den give vektor ind:
$$
\overline{u}=(\frac{8}{\sqrt{8^{2}+(-6)^{2}}}, \frac{-6}{\sqrt{8^{2}+(-6)^{2}}})
$$
$$
\overline{u}=(\frac{8}{\sqrt{100}},\frac{-6}{\sqrt{100}})
$$
$$
\overline{u}=(\frac{4}{5},\frac{-3}{5})
$$


4. **Udregn den retningsafledede af $f$ i punktet $(2,1)$ i retningen af enhedsvektoren $\overline{u}$ fundet i delspørgsmål c (3).**

Ved brug af sætning 3.10 ved vi at:
$$
D_{\overline{u}}f(x,y)=\frac{\partial f}{\partial x}a+\frac{\partial f}{\partial y}b
$$
Nu kan jeg sætte værdierne ind:
$$
D_{\overline{u}}f(x,y)=(3x^{2}+8xy+5y^{2})\cdot \frac{4}{5}+(4x^{2}+10xy)\cdot \frac{-3}{5}
$$
Nu kan jeg finde det for det givne punkt:
$$
D_{\overline{u}}f(2,1)=(12+16+5)\cdot \frac{4}{5}+(16+20)\cdot \frac{-3}{5}
$$
$$
D_{\overline{u}}f(2,1)=\frac{132}{5}+\frac{-108}{5}
$$
$$
D_{\overline{u}}f(2,1)=\frac{24}{5}
$$


5. **Angiv den enhedsvektor $\overline{v}$, der giver den største retningsafledede af $f$ i punktet $(2,1)$.**

Først finder jeg gradienten i det givne punkt:
$$
\nabla f(2,1)=(33,36)
$$
Nu kan jeg finde enhedsvektoren for denne:
$$
\overline{v}=(\frac{33}{\sqrt{33^{2}+36^{2}}}, \frac{36}{\sqrt{33^{2}+36^{2}}})
$$
$$
\overline{v}=(\frac{11}{\sqrt{265}},\frac{12}{\sqrt{265}})
$$



6. **Angiv værdien af den største retningsafledede af $f$ i punktet $(2,1)$.**

Ved brug af sætning 3.10 (igen) ved vi at:
$$
D_{\overline{u}}f(x,y)=\frac{\partial f}{\partial x}a+\frac{\partial f}{\partial y}b
$$
Nu kan jeg sætte værdierne ind:
$$
D_{\overline{u}}f(2,1)=33\cdot \frac{11}{\sqrt{265}}+36\cdot \frac{12}{\sqrt{265}}
$$
$$
D_{\overline{u}}f(2,1)=3 \sqrt{265}\approx 48.84
$$
