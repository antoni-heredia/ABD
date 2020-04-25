## Ejercicio 5
___
#### Indica qué ocurre cuando se añaden los registros con valores de clave 6, 4, 8, 9 y 1, tanto en el fichero maestro como en el fichero de índice.

En el maestro crearan dos bloques nuevos, uno para los cuatro primeros $(6,4,8,9)$ y otro en el que solo se añadirá el $1$, suponiendo que no tiene area de desbordamiento. Si la tuviera se insertara en el área de desbordamiento. 

En el de indice se insertaran los indices de todos los valores. (Suponiendo que es un indice denso).