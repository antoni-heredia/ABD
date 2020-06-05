### Sea una relación con n=10 tuplas, B=4KB, R=120^6 B, P=6B y V=8B. Calcula el número de bloques necesarios para almacenar los datos organizados mediante un archivo secuencial indexado en caso de tratarse de:
1. un índice denso
2. un índice no denso


#### 1
Los del maestro seran:
$$Bfr=\lfloor\frac{B-C}{R}\rfloor=\lfloor\frac{4096-0}{120}=34\rfloor$$
$$Bloques = \lceil\frac{10^6}{34}\rceil=29412 bloques$$
Los demas los calculamos:
$$N_{Denso}=N$$
$$Bfr_{Denso}=\lfloor\frac{B-C}{P+V}\rfloor=\lfloor\frac{4096}{6+8}\rfloor=292$$
$$Bloques_{Denso}=\lceil\frac{N_{Denso}}{Bfr_{Denso}}\rceil=\lceil\frac{N}{292}\rceil=3425 bloques $$
El total seria:
$$ Total = 29412+3425=32837$$

#### 2
Como hay una entrada por cada entrada del maestrotenemos que:
$$Bloques del Maestro=29412$$ 
$$Bfr_{No\_denso}=\lceil\f| T3 | l1 | start  |  |  |  |  |rac{N_{No\_denso}}{Bfr_{No\_denso}}\rceil=\lceil\frac{Bloques del Maestro}{292}\rceil=101 bloques $$
El total seria:
$$ Total = 101+29412= 29513$$
