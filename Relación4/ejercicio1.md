### Indica el contenido de la tabla de modificaciones:

La tabla de modificaciones la podemos ver a continuación.

| T_id | Hora | Estado | Operación | Datos | Vantiguo | Vnuevo |
| -- | -- | -- | -- | -- | -- | -- |
| T3 | l1 | start  |  |  |  |  |
| T3 | l2 | | update  | B | 50 | 200 |  
| T3 | l3 | | update  | C | 200 | 150 |  
| T3 | l4 | commit  |  |  |  |  |
| T2 | l5 | start  |  |  |  |  |
| T2 | l6 | | update  | B | 200 | 100 |  
| T2 | l7 | commit  |  |  |  |  |
| T1 | l8 | start  |  |  |  |  |
| T1 | l9 | | update  | A | 100 | 150 |  
| T1 | l10 | commit  |  |  |  |  |



Lee(T4,D),Escribe(T4,D=15),Lee(T3,C),Lee(T2,B),Escribe(T3,C=30,Escribe(T2,B=1)),Lee(T1,A),Escribe(T1,A=30), Escribe(T3,D=12)