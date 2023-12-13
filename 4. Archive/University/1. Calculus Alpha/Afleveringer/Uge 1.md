For fisk, der vandrer langt for at gyde, gælder det om at have så mange energireserver tilbage som muligt, når de når frem. Derfor er det vigtigt at minimere det samlede energiforbrug under vandringen. Energiforbruget pr. tid, og derved også iltoptagelseshastigheden ($V_{O_2}$), kan med god tilnærmelse anses for at være eksponentielt afhængende af svømmehastigheden:
$$
V_{O_{2}}=a*e^{kv}
$$

Her er $v$ svømmehastigheden og $a$ og $k$ er positive konstanter. Brutto (den totale omkostning) og netto (det der går til selve svømningen) ‘Cost of Transport’ ($bCOT$ og $nCOT$) er defineret som energiforbruget eller iltforbruget pr. distance og beregnes som:
$$bCOT=\frac{V_{O_2}}{v}$$
$$nCOT=\frac{V_{O_2}-V_{O_2}(0)}{v}$$
hvor $V{O_2}(0)$ er iltforbruget ved hastigheden 0.

1. **Find hastigheden $v$ hvor $bCOT$ opnår sit minimum samt den tilhørende minimums-værdi.**

For at finde minimum samt minimums-værdien, skal vi først have $bCOT'$.  Til at finde $bCOT'$ kan vi bruge kædereglen:
$$
bCOT'=\frac{V_{O_2}'*v-V_{O_2}*v'}{v^{2}}
$$
Hertil skal vi bruge $V_{O_2}'$:
$$
(V_{O_2})'=k*a*e^{kv}
$$
Nu kan vi sætte de kendte værdier ind og finde $bCOT'=0$:
$$
bCOT'=\frac{(k*a*e^{kv})*v-(a*e^{kv})*1}{v^{2}}
$$
$$
bCOT'=\frac{k*a*e^{kv}*v}{v^{2}}-\frac{a*e^{kv}}{v^{2}}
$$
$$
bCOT'=\frac{k*e^{kv}}{v}-\frac{a*e^{kv}}{v^{2}}
$$
$$
\frac{a*e^{kv}}{v^{2}}=\frac{k*e^{kv}}{v}
$$
Nu kan vi bruge reglen der siger at
$$
\frac{a}{b}=\frac{c}{d}
$$
Kan laves om til
$$
<=> a*d=b*c
$$
Så vi kan sætte værdierne ind og forkorte den mere, til vi har den til at være lig 0.
$$
v*a*e^{kv}=v^2*k*a*e^{kv}
$$
$$
a*e^{kv}=v*k*a*e^{kv}
$$
$$
e^{kv}=v*k*e^{kv}
$$
Nu vi har den til at være lig 0, har vi minimumsværdien
$$
min=\frac{1}{k}=v
$$
Nu kan vi bruge minimum til at finde minimumsværdien:
$$
bCOT(\frac{1}{k})=\frac{a*e^{k*\frac{1}{k}}}{\frac{1}{k}}
$$
$$
min. værdi=\frac{a*e}{\frac{1}{k}}
$$



2. **Find grænseværdien af $nCOT$ når hastigheden $v$ går mod 0.**

For at finde grænseværdien af $nCOT$ når $v$ går mod 0, kan vi i dette tilfælde bruge reglen der siger at:
$$
f'(x_{0})=\displaystyle \lim_{x \to x_0}\frac{f(x)-f(x_0)}{x-x_{0}}
$$
Vi kan så sætte vores værdier ind:
$$
V_{O_{2}}'(0)=\displaystyle \lim_{v \to 0}\frac{V_{O_2}-V_{O_2}(0)}{v-0}
$$
Vi kender allerede $V_{O_2}'$ så vi kan udregne hvad den er når $v=0$:
$$
V_{O_2}'(0)=k*a*e^{k*0}
$$
$$
V_{O_2}'(0)=k*a
$$
$$
\displaystyle \lim_{v \to 0}\frac{V_{O_2}-V_{O_2}(0)}{v}=a*k
$$
Nu ved vi at $nCOT$ når $v$ går mod 0 er:
$$
\lim_{v \to 0}nCOT=a*k
$$
