### Si ocurriera un fallo donde se muestra la doble línea de la tabla de modificaciones, ¿qué haría el sistema después de recuperarse con cada una de las transacciones y cuáles serían los valores de los datos después de la recuperación?

Al encontrarse después de un commit y existir un "checkpoint", se realizara un REDO para las transacciones entre el commit y  el checkpoint anterior. Esto es que repetirá esas transacciones.

El valor de las variables sera:

- A = 30
- B = 15
- D = 25
- E = 35