
## Funktioner af en variabel

$f(x)=e^{x}ln(x)$

### Find $f'$ og $f''$

$f'$:
```
D[e^x*ln(x),x]
```

$f''$:
```
D[e^x*ln(x),{x,2}]
```

### Find ligningen for den tangent til grafen for funktionen der går gennem punktet

**Input:**
$f(x)=ln(x^{2}-3)$
$p=[2,0]$

**Mellemregning**

a:
```
D[f(p[0]),p[0]]
```

```
p[0]=2
```
