### Si ocurriera un fallo antes de la sentencia Escribe (T3, C), indica cómo se recuperaría el sistema en función del contenido de la tabla de modificaciones, considerando todas las posibilidades respecto de que el fallo ocurra antes o después de una operación commit, si fuera el caso.

Si el fallo ocurriera __antes__ del commit, simplemente se borrarian de la tabla todas las operaciones realizando un UNDOT$(T_3)$. No habría que realizar nada mas.

En cambio si fuera __despues__ del commit no bastaría con borrar la tabla, ya que pueden no haberse ejecutado (o si), entonces habría que rehacer la transacción completa volviendo a escribir los valores nuevos. 

Si hubiera un fallo antes de la sentencia Escribe(T1,C=10), como se recuperaría el sistema a partir de la tabla de modificaciones, teniendo en cuenta de que ocurra antes o después de una operación commit. 

Lee(T1,A),Lee(T3,C),Lee(T4,D),Escribe(T1,D=15,Lee(T2,B),Escribe(T2,B=30), Escribe(T3,D=12),Escribe(T1,C=10),Escribe(T4,D=30)