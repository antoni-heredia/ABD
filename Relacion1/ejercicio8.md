### Se tienen registros con un nombre que es un varchar (29), una dirección que es un varchar (255), una fecha que ocupa 10B, un valor para sexo que es un lógico y ocupa 1B, y un tamaño de bloque B=4KB. Calcula el factor de bloqueo y el porcentaje de utilización en caso de tratarse de bloqueo fijo. Si el bloque contiene 10B de cabecera y un directorio de entradas en el bloque.
- A: longitud media de los nombres de atributo
- V: longitud media de los valores de atributo
- a': número medio de atributos
- s: número de separadores por atributo
$$R=a'(A+V +s)=4*(0+\frac{30+256+10+1}{4}+1)=301B$$
$$B=4096$$
$$C=10B$$
Como sabemos que tiene un directorio de entradas en el bloque, tenemos que quitarselo al igual que la cabecera. La M es la marca de separación.
$$Bfr=\lfloor \frac{B-C-30Bfr}{R+M}\rfloor=\lfloor\frac{4096-10-30Bfr}{301+1}\rfloor=$$
$$302Bfr=4086-30Bfr;$$
$$332Bfr=4086;$$
$$Bfr=\lfloor \frac{4086}{332}\rfloor=12;$$
Para calcular el desperdicio:
$$W=\frac{B-Bfr\times R-4\times Bfr}{B}= \frac{4096-12\times301-4\times12}{4096}=\frac{436}{4096}=0.106$$
Por lo tanto el porcentaje de utilización sera:
$$Utilización = 1-W=1-0.106=0.894->89.4\%$$

