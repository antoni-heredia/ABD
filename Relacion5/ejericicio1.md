### ¿En qué orden se ejecutarían las transacciones según el algoritmo de ordenación parcial modificado?

![](img/EJE1.png)

La operación de escritura _Lee (T1, B)_  no afecta, pero tampoco aborta la transacción

La operación _Escribe (T2, B)_ se ignorara, ya que lo que le precede es una escritura. 