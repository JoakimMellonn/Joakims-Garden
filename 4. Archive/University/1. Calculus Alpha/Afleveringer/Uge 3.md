## Opskriv det generelle differentiale for de følgende funktioner og angiv differentialet i punktet (1, 2)

1. $f(x,y)=xy^{2}$ 

Først finder jeg de partielt afledte funktioner for $x$ og $y$:
$$
\frac{\partial f}{\partial x}=y^{2}
$$
$$
\frac{\partial f}{\partial y}=2xy
$$
Nu kan jeg så opskrive det generelle differentiale for $f$:
$$
\partial f=y^{2}*dx+2xy*dy
$$
Nu kan jeg bruge det generelle differentiale til at finde differentialet i punktet (1, 2):
$$
\partial f=4dx+4dy
$$



2. $f(x,y)=x^{2}\sin(\pi y^2)$ 

Som i a (1), finder jeg først de partielt afledte funktioner:
$$
\frac{\partial f}{\partial x}=2x*\sin(\pi y^{2})
$$
$$
\frac{\partial f}{\partial y}=x^{2}*2\pi*y*\cos(\pi*y^2)
$$
Til at finde $\frac{\partial f}{\partial y}$ skulle jeg bruge kædereglen.

Så kan jeg opskrive det generelle differentiale:
$$
\partial f=2x*\sin(\pi y^{2})dx+x^2*2\pi*y*\cos(\pi*y^{2})dy
$$
Til sidst kan vi finde differentialet i punktet (1,2):
$$
\partial f=2\sin(4\pi)dx+4\pi*\cos(4\pi)dy
$$
Da $\sin(4\pi)=0$ og $\cos(4\pi)=1$ kan vi også skrive det som:
$$
\partial f=4\pi dy=0
$$
