# Funciones Agregadas, GROUP BY y HAVING en SQL

# 1. Introducción

En bases de datos es muy común necesitar:

- Contar registros.
- Calcular promedios.
- Obtener valores máximos y mínimos.
- Realizar reportes agrupados.
- Analizar ventas, usuarios, productos o calificaciones.

SQL permite realizar este tipo de análisis mediante:

- Funciones agregadas.
- GROUP BY.
- HAVING.

Estas herramientas son fundamentales para reportes y análisis de información.

---

# 2. ¿Qué son las Funciones Agregadas?

Las funciones agregadas realizan operaciones sobre un conjunto de registros y devuelven un único resultado.

Las más utilizadas son:

| Función | Descripción |
|---|---|
| COUNT() | Cuenta registros |
| SUM() | Suma valores |
| AVG() | Calcula promedio |
| MIN() | Obtiene el valor mínimo |
| MAX() | Obtiene el valor máximo |

---

# 3. Base de Datos de Ejemplo

Usaremos la tabla:

```sql
CREATE TABLE ventas (
    ventas_id INT PRIMARY KEY AUTO_INCREMENT,
    ventas_vendedor VARCHAR(50),
    ventas_producto VARCHAR(50),
    ventas_ciudad VARCHAR(50),
    ventas_cantidad INT,
    ventas_precio DECIMAL(10,2)
);
```

---

# 4. Datos de Ejemplo

```sql
INSERT INTO ventas (ventas_vendedor, ventas_producto, ventas_ciudad, ventas_cantidad, ventas_precio)
VALUES
('Ana', 'Laptop', 'Bogotá', 2, 2500),
('Ana', 'Mouse', 'Bogotá', 5, 80),
('Carlos', 'Teclado', 'Medellín', 3, 150),
('Carlos', 'Monitor', 'Medellín', 1, 900),
('Marta', 'Laptop', 'Cali', 1, 2600),
('Marta', 'Mouse', 'Cali', 4, 85),
('Pedro', 'Monitor', 'Bogotá', 2, 950);
```

---

# 5. COUNT()

COUNT() permite contar registros.

## Contar todos los registros

```sql
SELECT COUNT(*) AS total_ventas
FROM ventas;
```

Resultado esperado:

| total_ventas |
|---|
| 7 |

---

## Contar registros específicos

```sql
SELECT COUNT(ventas_producto) AS productos
FROM ventas;
```

---

# 6. SUM()

SUM() permite sumar valores numéricos.

## Sumar cantidades vendidas

```sql
SELECT SUM(ventas_cantidad) AS total_productos
FROM ventas;
```

---

## Sumar ingresos

```sql
SELECT SUM(ventas_cantidad * ventas_precio) AS total_ingresos
FROM ventas;
```

---

# 7. AVG()

AVG() calcula promedios.

## Promedio de precios

```sql
SELECT AVG(ventas_precio) AS promedio_precio
FROM ventas;
```

---

## Promedio de cantidades

```sql
SELECT AVG(ventas_cantidad) AS promedio_cantidad
FROM ventas;
```

---

# 8. MIN()

MIN() obtiene el valor mínimo.

## Precio más bajo

```sql
SELECT MIN(ventas_precio) AS precio_minimo
FROM ventas;
```

---

# 9. MAX()

MAX() obtiene el valor máximo.

## Precio más alto

```sql
SELECT MAX(ventas_precio) AS precio_maximo
FROM ventas;
```

---

# 10. Uso de Alias con AS

AS permite renombrar columnas.

```sql
SELECT AVG(ventas_precio) AS promedio
FROM ventas;
```

Sin alias:

```sql
AVG(ventas_precio)
```

Con alias:

```sql
promedio
```

---

# 11. GROUP BY

GROUP BY permite agrupar registros.

## Sintaxis

```sql
SELECT columna, funcion_agregada()
FROM tabla
GROUP BY columna;
```

---

# 12. Ejemplo Básico de GROUP BY

## Total vendido por vendedor

```sql
SELECT ventas_vendedor, SUM(ventas_cantidad) AS total_vendido
FROM ventas
GROUP BY ventas_vendedor;
```

Resultado esperado:

| ventas_vendedor | total_vendido |
|---|---|
| Ana | 7 |
| Carlos | 4 |
| Laura | 5 |
| Pedro | 2 |

---

# 13. GROUP BY con Varias Columnas

```sql
SELECT ventas_ciudad, ventas_producto, SUM(ventas_cantidad) AS total
FROM ventas
GROUP BY ventas_ciudad, ventas_producto;
```

---

# 14. GROUP BY y COUNT()

## Cantidad de ventas por ciudad

```sql
SELECT ventas_ciudad, COUNT(*) AS total_ventas
FROM ventas
GROUP BY ventas_ciudad;
```

---

# 15. GROUP BY y AVG()

## Precio promedio por ciudad

```sql
SELECT ventas_ciudad, AVG(ventas_precio) AS promedio
FROM ventas
GROUP BY ventas_ciudad;
```

---

# 16. GROUP BY y MAX()

## Venta más costosa por vendedor

```sql
SELECT ventas_vendedor, MAX(ventas_precio) AS venta_mayor
FROM ventas
GROUP BY ventas_vendedor;
```

---

# 17. HAVING

HAVING permite filtrar grupos.

WHERE filtra registros individuales.

HAVING filtra resultados agrupados.

---

# 18. Diferencia entre WHERE y HAVING

| WHERE | HAVING |
|---|---|
| Filtra filas | Filtra grupos |
| Se usa antes del GROUP BY | Se usa después del GROUP BY |
| No usa funciones agregadas normalmente | Sí usa funciones agregadas |

---

# 19. Ejemplo de HAVING

## Mostrar vendedores con ventas mayores a 5 productos

```sql
SELECT ventas_vendedor, SUM(ventas_cantidad) AS total
FROM ventas
GROUP BY ventas_vendedor
HAVING SUM(ventas_cantidad) > 5;
```

Resultado esperado:

| ventas_vendedor | total |
|---|---|
| Ana | 7 |

---

# 20. WHERE + GROUP BY + HAVING

## Ventas de Bogotá agrupadas por vendedor

```sql
SELECT ventas_vendedor, SUM(ventas_cantidad) AS total
FROM ventas
WHERE ventas_ciudad = 'Bogotá'
GROUP BY ventas_vendedor
HAVING SUM(ventas_cantidad) > 1;
```

---

# 21. Orden Correcto de una Consulta SQL

```sql
SELECT
FROM
WHERE
GROUP BY
HAVING
ORDER BY
```

---

# 22. Ejemplo Completo

```sql
SELECT ventas_vendedor,
       SUM(ventas_cantidad * ventas_precio) AS ingresos
FROM ventas
WHERE ventas_precio > 100
GROUP BY ventas_vendedor
HAVING ventas_ingresos > 1000
ORDER BY ventas_ingresos DESC;
```

---

# 23. Errores Comunes

## Error 1: Usar HAVING sin GROUP BY

Incorrecto:

```sql
SELECT ventas_vendedor
FROM ventas
HAVING ventas_vendedor = 'Ana';
```

Correcto:

```sql
SELECT ventas_vendedor
FROM ventas
WHERE ventas_vendedor = 'Ana';
```

---

## Error 2: Columnas no agrupadas

Incorrecto:

```sql
SELECT ventas_vendedor, ventas_ciudad, SUM(ventas_cantidad)
FROM ventas
GROUP BY ventas_vendedor;
```

Correcto:

```sql
SELECT ventas_vendedor, ventas_ciudad, SUM(ventas_cantidad)
FROM ventas
GROUP BY ventas_vendedor, ventas_ciudad;
```

---

# 24. Buenas Prácticas

- Usar alias claros.
- Nombrar correctamente los cálculos.
- Aplicar WHERE antes de GROUP BY.
- Usar HAVING únicamente para grupos.
- Organizar consultas en múltiples líneas.

---

# 25. Taller Práctico en Clase

## Crear tabla

```sql
CREATE TABLE estudiantes (
    estudiantes_id INT PRIMARY KEY AUTO_INCREMENT,
    estudiantes_nombre VARCHAR(50),
    estudiantes_curso VARCHAR(50),
    estudiantes_nota DECIMAL(4,2)
);
```

---

## Insertar datos

```sql
INSERT INTO estudiantes(estudiantes_nombre, estudiantes_curso, estudiantes_nota)
VALUES
('Laura', 'Bases de Datos', 4.5),
('Carlos', 'Bases de Datos', 3.8),
('Ana', 'Programación', 4.9),
('Pedro', 'Programación', 2.8),
('Luisa', 'Bases de Datos', 4.2),
('Mario', 'Programación', 3.5);
```

---

# 26. Ejercicios Guiados

## 1. Contar estudiantes

```sql
SELECT COUNT(*) AS total_estudiantes
FROM estudiantes;
```

---

## 2. Promedio de notas

```sql
SELECT AVG(estudiantes_nota) AS promedio
FROM estudiantes;
```

---

## 3. Nota más alta

```sql
SELECT MAX(estudiantes_nota) AS nota_maxima
FROM estudiantes;
```

---

## 4. Promedio por curso

```sql
SELECT estudiantes_curso, AVG(estudiantes_nota) AS promedio
FROM estudiantes
GROUP BY estudiantes_curso;
```

---

## 5. Cursos con promedio mayor a 4

```sql
SELECT estudiantes_curso, AVG(estudiantes_nota) AS promedio
FROM estudiantes
GROUP BY estudiantes_curso
HAVING AVG(estudiantes_nota) > 4;
```

---

# 27. Actividad Individual

Realizar las siguientes consultas:

1. Mostrar la cantidad total de estudiantes.
2. Mostrar la nota mínima.
3. Mostrar la nota máxima.
4. Mostrar el promedio por curso.
5. Mostrar cursos con promedio mayor a 3.5.
6. Mostrar cuántos estudiantes hay por curso.
7. Mostrar cursos con más de 2 estudiantes.

---

# 28. Ejercicio de Análisis

Responder:

1. ¿Cuál es la diferencia entre WHERE y HAVING?
2. ¿Cuándo se debe usar GROUP BY?
3. ¿Para qué sirven las funciones agregadas?
4. ¿Qué sucede si una columna no está agrupada?
5. ¿Cuál es la diferencia entre COUNT(*) y COUNT(columna)?

---

# 29. Reto en Clase

Crear una tabla llamada productos con:

- nombre
- categoría
- precio
- stock

Luego realizar:

- SUM()
- AVG()
- MAX()
- MIN()
- GROUP BY
- HAVING

---

# 30. Resumen de la Sesión

En esta sesión aprendimos:

- Qué son las funciones agregadas.
- Cómo usar COUNT, SUM, AVG, MIN y MAX.
- Cómo agrupar datos con GROUP BY.
- Cómo filtrar grupos con HAVING.
- Diferencias entre WHERE y HAVING.
- Cómo generar reportes básicos en SQL.

Estas herramientas son esenciales para análisis de datos y reportes empresariales.