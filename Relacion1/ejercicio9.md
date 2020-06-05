###  Se tienen registros con: char (215), integer -2B-, fecha -10B-, real -8B-, R=235B, B=4KB.Supuesta la estructura de longitud variable, una cabecera con 2 punteros -de 4B- más un carácter, calcula el factor de bloqueo para:
1. bloqueo fijo
2. bloqueo encadenado

#### 1.

$$Bfr=\lfloor\frac{B-C}{R}\rfloor=\lfloor\frac{4096-(2*4+1)}{235}\rfloor=17$$

#### 2.

$$Bfr=\lfloor\frac{B-C}{R+M}\rfloor=\lfloor\frac{4096-9}{(| T3 | l1 | start  |  |  |  |  |235+4)+1}\rfloor=17$$
