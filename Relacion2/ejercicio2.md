### Explica qué elementos del nivel interno de Oracle se crearían y cuánto ocuparía la tabla recién creada si se ejecuta la consulta:
```
create table prueba(nombre varchar2(40) primary key, DNI
varchar2(8)) tablespace users
storage (initial 40k next 20k maxextents 10);
```

Se creara un indice para la clave primaria. Ademas se crearan un bloque, un segmento y una extensión

Como solo se creara una extensión inicial de 40k. 