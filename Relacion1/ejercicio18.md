###  Suponiendo que se tiene la relación prof (NRP, nombre, categoría, dpto) y se tienen dos índices I1 (sobre NRP) e I2 (sobre categoría), y dada la consulta:
```
SELECT dpto, categoría, NRP FROM prof WHERE categoría='AS1';
```

#### Algún plan lógico

![](eje18.png)

#### Un plan de ejecución que podría generar el optimizador de consultas

![](eje18_MEJORA.png)