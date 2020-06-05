### Indica las ventajas y/o los inconvenientes de claves de búsquedas duplicadas a la hora de montar un índice, y razona las respuestas.

Como __Ventajas__ podemos encontrar que tenemos un indice de poco tamaño, ayudando esto a la búsqueda del primer elemento con esa clave. Nos permite la búsqueda por varias claves que no hace falta que sean la primaria. Tiene utilidad en la búsqueda de un intervalo de valores. 

Como __inconvenientes__ podemos ver la perdida de eficiencia al leer del indice, ya qu el primero es de acceso directo pero el resto son secuenciales. Tampoco se nos garantiza el orden al insertar ya ua que al tener claves repetidas no se sabe si el registro se insertará antes o después de otro con la misma clave.