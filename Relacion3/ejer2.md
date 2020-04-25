## Ejercicio 2
___
#### Determina el número de operaciones de E/S (plan físico) para el plan lógico del __Ejercicio 1__.

Primero vamos a ver cuantos bloques son necesarios transferir en cada una de las operaciones. 

Calcularemos primero los bloques de R para relizar el JOIN. 

\
$L(R)=20+30+100=150$

\
$Bfr(R)=\lfloor\frac{B-C}{L(R)}\rfloor=\lfloor\frac{4096-40}{150}\rfloor=27$

\
$B(R)= \lceil\frac{N(R)}{Bfr(R)}\rceil=\lceil\frac{1000}{27}\rceil=38$

Ahora calculamos el numero de bloques para que S realice el JOIN.

\
$L(S)=30+20+40=90$

\
$Bfr(S)=\lfloor\frac{B-C}{L(S)}\rfloor=\lfloor\frac{4096-40}{90}\rfloor=45$

\
$B(S)=\lceil\frac{N(S)}{Bfr(S)}\rceil=\lceil\frac{5000}{45}\rceil=112$

También tenemos que realizar un "mergesort" para ordenar datos. Llamaré __O(X)__ a la ordenación de X a partir de cualquiera de sus atributos, en este caso sera b, ya que es por el cual queremos hacer el JOIN. 

\
$O(R)=\lceil B(R)\times log_2(B(R)) \rceil=\lceil199.42\rceil=200$

\
$O(S)=\lceil B(S)\times log_2(B(S)) \rceil=\lceil762.423\rceil=763$

Como necesitaremos ller todos registros de R y S una sola vez tendremos $B(R)+B(S)=150$  lecturas. 

Ademas necesitamos suficientes bloques para los registros que salen de realizar el JOIN. 

\
$N(JOIN)=\frac{N(R)\times N(S)}{max[V(R,b),V(S,b)]}=\frac{1000*5000}{500}=10000$

\
$L(LOIN)=L(R)+L(S)-tamaño(b)=150+90-30$

\
$Bfr(JOIN)=\lfloor\frac{B-C}{L(JOIN)}\rfloor=\lfloor\frac{4096-40}{210}\rfloor=19$

\
$B(JOIN)=\lceil\frac{N(JOIN)}{Bfr(JOIN)}\rceil=\lceil\frac{10000}{Bfr(19)}\rceil=527$

Por ultimo nos queda ver cuantos bloques debe leer de la operacion anterior y cuantos bloques debe escribir la operación $\Pi_{a,e}$. 

\
$L(\Pi_{a,e})=20+40=60$

\
$Bfr(\Pi_{a,e})=\lceil\frac{B-C}{L(\Pi_{a,e})}\rceil=\lceil\frac{4096-40}{60)}\rceil=67$

\
$B(\Pi_{a,e})=\lfloor\frac{N(\Pi_{a,e})}{Bfr(\Pi_{a,e})}\rfloor=\lfloor\frac{10000}{67}\rfloor=150$

Lo ultimo que nos queda es ver la operación de selección. 
Primero tenemos  que calcular:

\
$N\left(\sigma_{e=e_{1}}\right)=\frac{N(\Pi_{a,e})}{V(S,e)}*=\frac{10000}{40}=250$.

Por lo tanto tendremos que:

\
$B(\sigma_{e=e_{1}})=\lceil\frac{N(\sigma_{e=e_{1}})}{67}\rceil=4$

\
Haciendo balance de la cantidad de bloques quedaria algo asi:

 - $O(R) = 200$ y $O(S)=763$
 - En el JOIN -> Leemos 150 y escribimos 527 
 - En la proyección -> Leemos 527 y escribimos 150
 - En la selección leemos 150 y escribimos 4

\
Si sumamos todas las operaciones tenemos un total de 2471.