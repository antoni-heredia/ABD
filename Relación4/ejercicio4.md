### Si no consideramos el uso de concurrencia (sin abortar transacciones) y los valores iniciales de los datos son A=10, B=0, D=8 y E=35, completa la tabla de modificaciones, considerando que se incluye un start cuando comienza una transacción y un commit cuando termina.


| T_id  | Estado | Operación | Datos | Vantiguo | Vnuevo |
| --  | -- | -- | -- | -- | -- |
| T1 |  start  |  |  |  |  |
| T2 |  start  |  |  |  |  |
| T1 |    | update | A | 10 | 20 |
| T1 |  commit  |  |  |  |  |
| T3 |  start  |  |  |  |  |
| T2 |    | update | A | 20 | 30 |
| T3 |    | update | B | 0 | 15 |
| T3 |    | update | D | 8 | 25 |
| T3 |  commit  |  |  |  |  |
| T2 |    | update | E | 35 | 35 |
| T2 |  commit  |  |  |  |  |
