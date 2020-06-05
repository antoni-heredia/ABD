### Sea una relación con n=10^6 tuplas, B=4KB, R=2050B y bloqueo fijo. Calcula el factor de bloqueo así como el desperdicio y el porcentaje de utilización de los bloques.
$$Bfr=\lfloor \frac{B-C}{R}\rfloor=\lfloor\frac{4096-0}{2050}\rfloor=1$$
El desperdicio se calcula:
$$W=\frac{B-Bfr\times R}{B}= \frac{4096-1*2050}{4096}=0.49->49\%$$