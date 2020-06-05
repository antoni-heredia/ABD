### Sea R(A, B, C, D) el esquema de una relación. A continuación, se presentan tres planes lógicos de una consulta:
1. $\sigma_{A=a \wedge B=b}(R)$
2. $\mathbf{\sigma}_{A=a}\left(\mathbf{\sigma}_{B=b}(R)\right)$
3. $\sigma_{B=b}\left(\sigma_{A=a}(R)\right)$

El __1__ y el __2__ son equivalentes. Podemos pasar de uno a tro a través de propiedades de la aritmética racional. 

Aun asi, para tomar una elección entre el plan __2__ o el __3__ tendríamos que saber la variabilidad de cada uno. Cojearemos siempre la opción que realice selecciónes con mas variabilidad al principio. Entonces se nos da dos casos:

Si tenemos que $V(R,A)>V(R,B)$ se realizara primero el plan __3__, si $V(R,A)<V(R,B)$ entonces se elegirá el plan __2__.
