## Ejercicio 3
___
#### Propón un plan lógico cuyo plan físico mejore el del Ejercicio 2, justificando numéricamente la mejora.

En principio parece que seria una mejora realizar realizar las selecciones  y proyecciones  al principio. De esta manera evitamos que haya menos bloques en el JOIN. 

La primero es la selección de la S donde $e=e_k$. Luego podremos realizar la proyección  de R para hacer el JOIN y volver a realizar una proyección final. El plan lógico resultante quedaría algo tal que asi:
\
![](img/ejercicio3.png)

Primero vamos a calcular la operación de selección en S. Esta selección es la clave para reducir el numero de operaciones __E/S__.

\
$N(\sigma_{e=e_k})=\frac{N(S)}{V(S,e)}=\frac{5000}{40}=125$
\
$B(\sigma_{e=e_k})=\lceil\frac{N(\sigma_{e=e_k})}{Bfr(\sigma_{e=e_k})}=\lceil\frac{N(\sigma_{e=e_k})}{45}\rceil=3$
\
*Bfr(S) Calculado en el ejercicio anterior

\
También calculamos la proyección sobre esta selección:
\
$L(\Pi_{b,e})=30+40$
\
$Bfr(\Pi_{b,e})=\lfloor\frac{4096-40}{70}\rfloor=57$
\
$B(\Pi_{b,e})=\lceil\frac{N(\Pi_{b,e})}{Bfr(\Pi_{b,e})}\rceil=\lceil\frac{125}{57}\rceil=3$

\
Ahora calculamos la proyección $\Pi{a,b}$ sobre R. 
\
$L(\Pi{a,b})=20+30=50$
\
$Bfr(\Pi{a,b})=\lfloor\frac{4096-40}{L(\Pi{a,b})}\rfloor=\lfloor\frac{4056}{50}\rfloor=81$
\
$B(\Pi{a,b})=\lceil\frac{N(R)}{Bfr(\Pi{a,b})}\rceil=\lceil\frac{1000}{81}\rceil=13$

\
Ahora como en el ejercicio anterior, al no estar ordenados por __b__ ni R ni S. Tenemos que realizar un "mergesort". Llamare __O(X)__ a la cantidad de bloques necesarios para el ordenamiento de X:
\
$O(\Pi_{b,e})=\lceil B(\Pi_{b,e})*Log_2(B(\Pi_{b,e}))\rceil=49$
$O(\Pi_{a,b})=\lceil B(\Pi_{a,b})*Log_2(B(\Pi_{a,b}))\rceil=5$

\
Ahora debemos realizar un JOIN de esas dos proyecciones. 
\
$L(JOIN))=L(\Pi_{b,e})+L(\Pi_{a,b})-tamaño(b)=50+70-30=90$
\
$Bfr(JOIN)=\lfloor \frac{4096-40}{L(JOIN)}\rfloor=\lfloor\frac{4056}{90}\rfloor=45$
\
$N(JOIN)=\frac{N(\Pi_{b,e})\times\Pi_{a,b}}{max[V(\Pi_{a,b},b),V(\Pi_{b,e},b)]}=\frac{1000\times125}{500}=250$
\
$B(JOIN)=\lceil\frac{N(JOIN)}{Bfr(JOIN)}\rceil=\lceil\frac{250}{45}\rceil=6$

\
Por ultimo nos queda la proyección $\Pi_{a,e}$ sobre el JOIN. 

\
$L(\Pi_{a,e}))20+40=60$
\
$Bfr(\Pi_{a,e})=\lfloor\frac{4096-40}{L(\Pi_{a,e})}\rfloor=\lfloor\frac{4056}{60}\rfloor=67$
\
$B(\Pi_{a,e})=\lceil\frac{N(\Pi_{a,e})}{Bfr(\Pi_{a,e})}\rfloor=\lfloor\frac{250}{67}\rfloor=4$

\
Como hice en el ejercicio anterior realizamos un resumen de todos las operaciones que tenemos y luego sumaremos para ver el total:
- Seleción $\sigma_{e=e_k}$: Lee 112 ($B(S)$) y escribe 3
- Proyección $\Pi_{b,e}$: Lee 3 y esccribe 3
- Proyección $\Pi_{a,b}$: Lee 38 y esccribe 13
- JOIN: Lee $B(\Pi_{b,e})+B(\Pi{a,b})=16$ y escribe 6
- Proyección $\Pi_{a,e}$: Lee 6 y escribe 4
- Ademas tenemos que tener en cuenta las operaciones de ordenamiento: $O(\Pi_{b,e})+O(\Pi_{a,b})=49+5=54$

\
La suma total de operaciones E/S es de __258__.

