# Introducción a Consultas SQL

## Conceptos fundamentales de SQL

SQL (Structured Query Language) es el lenguaje utilizado para comunicarse con una base de datos relacional.

Con SQL es posible:

- Consultar información
- Insertar registros
- Modificar datos
- Eliminar información
- Crear tablas
- Definir relaciones

En esta sesión el enfoque principal será:

- Consultas básicas
- Lectura de datos
- Filtrado
- Ordenamiento
- Comprensión de resultados

---

# Tipos de instrucciones SQL

SQL se divide en varios grupos de instrucciones.

## DDL (Data Definition Language)

Permite definir estructuras.

Ejemplos:

- CREATE
- ALTER
- DROP

## Ejemplo CREATE:

```sql
CREATE TABLE Students (
    students_id INT PRIMARY KEY,
    students_name VARCHAR(100),
    students_age INT,
    students_city VARCHAR(100)
);
```

## Ejemplo ALTER (Para añadir una columna a una tabla):

```sql
ALTER TABLE Students
ADD students_email VARCHAR(255);
```

## Ejemplo ALTER (Para eliminar una columna de una tabla):

```sql
ALTER TABLE Students
DROP COLUMN students_email;
```

## Ejemplo ALTER (Para cambiar el nombre de una columna de una tabla):

```sql
ALTER TABLE Students
RENAME COLUMN students_email to students_correo;
```

## Ejemplo ALTER (Para cambiar el tipo de dato de una columna de una tabla):

```sql
ALTER TABLE Students
MODIFY students_email VARCHAR(100) NOT NULL;
```

## Ejemplo ALTER (Para cambiar el nombre de una tabla):

```sql
ALTER TABLE Students
RENAME TO Student;
```

## Ejemplo DROP:

```sql
DROP TABLE IF EXISTS Students;
```

---

## DML (Data Manipulation Language)

Permite manipular información.

Ejemplos:

- INSERT
- UPDATE
- DELETE

## Ejemplo INSERT:

```sql
INSERT INTO Students (students_id, students_name, students_age, students_city)
VALUES (1, 'Sofía', 20, 'Manizales');
```

## Ejemplo UPDATE:

```sql
UPDATE Students
SET students_name = 'María Sofía'
WHERE students_id = 1;
```

## Ejemplo DELETE:

```sql
DELETE FROM Students 
WHERE students_id = 4;
```
---

## DQL (Data Query Language)

Permite consultar información.

Principal instrucción:

- SELECT

Ejemplo:

```sql
SELECT ALL * FROM Students;
```

---

# La instrucción SELECT

La instrucción SELECT permite consultar información almacenada en una tabla.

Sintaxis básica:

```sql
SELECT registros columnas
FROM tabla;
```

---

## Consultar todas las columnas

```sql
SELECT ALL * FROM Students;
```

El símbolo `*` representa todas las columnas.

---

## Consultar columnas específicas

```sql
SELECT ALL students_name, students_city
FROM Students;
```

---

# Base de datos de práctica

Durante la sesión se trabajará con tablas sencillas.

## Tabla: Students

| students_id | students_name   | students_city      | students_age |
|----|--------|-----------|-----|
| 1  | Sofía  | Manizales | 20  |
| 2  | Carlos | Pereira   | 22  |
| 3  | Ana    | Armenia   | 19  |
| 4  | David  | Manizales | 21  |

---

# Filtrado de información con WHERE

La cláusula WHERE permite filtrar registros.

Sintaxis:

```sql
SELECT registros columnas
FROM tabla
WHERE condicion;
```

---

## Ejemplo 1

```sql
SELECT ALL *
FROM Students
WHERE students_city = 'Manizales';
```

---

## Ejemplo 2

```sql
SELECT ALL students_name, students_age
FROM Students
WHERE students_age > 20;
```

---

# Operadores de comparación

## Igualdad

```sql
WHERE students_city = 'Pereira'
```

---

## Diferente

```sql
WHERE students_city != 'Pereira'
```

---

## Mayor que

```sql
WHERE students_age > 20
```

---

## Menor que

```sql
WHERE students_age < 20
```

---

## Mayor o igual

```sql
WHERE students_age >= 21
```

---

## Menor o igual

```sql
WHERE students_age <= 19
```

---

# Operadores lógicos

## AND

Ambas condiciones deben cumplirse.

```sql
SELECT ALL *
FROM Students
WHERE students_city = 'Manizales'
AND students_age > 20;
```

---

## OR

Al menos una condición debe cumplirse.

```sql
SELECT ALL *
FROM Students
WHERE students_city = 'Pereira'
OR students_city = 'Armenia';
```

---

# Ordenamiento de resultados

## ORDER BY ASC

Orden ascendente.

```sql
SELECT ALL *
FROM Students
ORDER BY students_age ASC;
```

---

## ORDER BY DESC

Orden descendente.

```sql
SELECT ALL *
FROM Students
ORDER BY students_age DESC;
```

---

# Limitar resultados

## LIMIT

Permite limitar la cantidad de registros mostrados.

```sql
SELECT ALL *
FROM Students
LIMIT 2;
```

---

# Alias de columnas

Los alias permiten cambiar temporalmente el nombre mostrado.

```sql
SELECT ALL student_name AS studentName,
       student_city AS studentCity
FROM Students;
```

---

# Consultas combinadas

Ejemplo completo:

```sql
SELECT ALL students_name, students_city, students_age
FROM Students
WHERE students_city = 'Manizales'
AND students_age >= 20
ORDER BY students_age DESC;
```

---

# Errores comunes en SQL

## Olvidar punto y coma

Incorrecto:

```sql
SELECT ALL * FROM Students
```

Correcto:

```sql
SELECT ALL * FROM Students;
```

---

## Escribir mal nombres de columnas

Incorrecto:

```sql
SELECT ALL student_name FROM Students;
```

Correcto:

```sql
SELECT ALL students_name FROM Students;
```

---

## Usar comillas incorrectamente

Incorrecto:

```sql
WHERE students_city = Manizales
```

Correcto:

```sql
WHERE students_city = 'Manizales'
```

---
# Guía práctica de consultas SQL
Esta guía explica las funciones y operadores SQL más utilizados para realizar consultas en una base de datos.
---
# Tabla de contenido
1. COUNT()
2. GROUP BY
3. AVG()
4. MAX()
5. MIN()
6. SUM()
7. LIMIT
8. OFFSET
9. BETWEEN
10. NOT BETWEEN
11. IN
12. NOT IN
13. LIKE
14. NOT LIKE

---
# Tabla de ejemplo

Trabajaremos con una tabla llamada empleados:

```sql
CREATE TABLE empleados (
    id INT,
    nombre VARCHAR(50),
    edad INT,
    salario DECIMAL(10,2),
    ciudad VARCHAR(50)
);
```

Datos:

|id	|nombre	|edad|salario|ciudad|
|-----|-----|-----|-----|-------|
|1	Ana|	    25|	2500|	Bogotá|
|2	Carlos|	35	|5000	|Medellín|
|3	Laura	|28	|3500	|Cali|
|4	Pedro	|45	|8000	|Bogotá|
|5	María	|30	|4500	|Pereira|

---

1. COUNT()

# ¿Para qué sirve?

COUNT permite contar registros.

Se usa cuando la pregunta dice:

* ¿Cuántos?
* Total de registros
* Cantidad de elementos

Ejemplo

- Pregunta:

¿Cuántos empleados existen?

```sql
SELECT COUNT(*) AS cantidad_empleados
FROM empleados;
```

Resultado:

|cantidad_empleados|
|---|
|5|

---

2. GROUP BY

# ¿Para qué sirve?

Agrupa registros que tienen un mismo valor.

Se usa cuando la pregunta dice:

* Por cada
* Agrupado por
* Según

Ejemplo

- Pregunta:

¿Cuántos empleados hay por ciudad?

```sql
SELECT ciudad, COUNT(*) AS cantidad
FROM empleados
GROUP BY ciudad;
```

Resultado:

|ciudad|	cantidad|
|----|----|
|Bogotá|	2|
|Medellín|	1|
|Cali|	1|
|Pereira|	1|

---

3. AVG()

# ¿Para qué sirve?

Calcula el promedio de una columna.

Se usa cuando preguntan:

* Promedio
* Media

Ejemplo

- Pregunta:

¿Cuál es el salario promedio?

```sql
SELECT AVG(salario) AS promedio
FROM empleados;
```

Resultado:

|promedio|
|----|
|4700|

⸻

4. MAX()

# ¿Para qué sirve?

Obtiene el valor más alto.

Se usa cuando preguntan:

* Mayor
* Máximo
* Más alto

Ejemplo

- Pregunta:

¿Cuál es el salario más alto?

```sql
SELECT MAX(salario) AS salario_maximo
FROM empleados;
```

Resultado:

|salario_maximo|
|-----|
|8000|

⸻

5. MIN()

# ¿Para qué sirve?

Obtiene el valor más pequeño.

Se usa cuando preguntan:

* Menor
* Mínimo
* Más bajo

Ejemplo

```sql
SELECT MIN(salario) AS salario_minimo
FROM empleados;
```

Resultado:

|salario_minimo|
|----|
|2500|

⸻

6. SUM()

# ¿Para qué sirve?

Suma valores numéricos.

Se usa cuando preguntan:

* Total
* Suma
* Acumulado

Ejemplo

Pregunta:

- ¿Cuánto dinero se paga en salarios?

```sql
SELECT SUM(salario) AS total_salarios
FROM empleados;
```

Resultado:

|total_salarios|
|------|
|23500|

⸻

7. LIMIT

# ¿Para qué sirve?

Limita la cantidad de registros mostrados.

Se usa cuando preguntan:

* Primeros
* Top
* Solo mostrar N registros

Ejemplo

- Pregunta:

Mostrar los 3 empleados con mayor salario.

```sql
SELECT *
FROM empleados
ORDER BY salario DESC
LIMIT 3;
```

Resultado:

|nombre|	salario|
|----|----|
|Pedro|	8000|
|Carlos|	5000|
|María|	4500|

⸻

8. OFFSET

# ¿Para qué sirve?

Permite saltar registros.

Se usa para:

* Paginación
* Empezar desde cierta posición

Ejemplo

Mostrar registros desde el cuarto empleado:

```sql
SELECT *
FROM empleados
OFFSET 3;
```

El primer registro tiene posición 0:

Ana     posición 0
Carlos  posición 1
Laura   posición 2
Pedro   posición 3

---

LIMIT + OFFSET

Ejemplo:

Mostrar página 2 con 2 registros por página.

```sql
SELECT *
FROM empleados
LIMIT 2
OFFSET 2;
```

Resultado:

|nombre|
|---|
|Laura|
|Pedro|

---

9. BETWEEN

# ¿Para qué sirve?

Busca valores dentro de un rango.

La palabra clave es:

“entre”

Ejemplo

Empleados con edad entre 25 y 35:

```sql
SELECT *
FROM empleados
WHERE edad BETWEEN 25 AND 35;
```

Incluye:

25 y 35

---

10. NOT BETWEEN

# ¿Para qué sirve?

Busca valores fuera de un rango.

Ejemplo

Empleados con edad que NO esté entre 25 y 35:

```sql
SELECT *
FROM empleados
WHERE edad NOT BETWEEN 25 AND 35;
```

Resultado:

|nombre|	edad|
|----|----|
|Pedro|	45|

---

11. IN

# ¿Para qué sirve?

Busca coincidencias dentro de una lista.

Se usa cuando hay varias opciones.

Ejemplo

Empleados de Bogotá o Cali:

```sql
SELECT *
FROM empleados
WHERE ciudad IN ('Bogotá','Cali');
```

Resultado:

|---|
|Ana|
|Laura|
|Pedro|

---

12. NOT IN

# ¿Para qué sirve?

Excluye valores de una lista.

Ejemplo

Empleados que no son de Bogotá ni Cali:

```sql
SELECT *
FROM empleados
WHERE ciudad NOT IN ('Bogotá','Cali');
```

Resultado:

|---|
|Carlos|
|María|

---

13. LIKE

¿Para qué sirve?

Busca patrones en textos.

Usa comodines:

Símbolo	Significado
%	cualquier cantidad de caracteres
_	un carácter

---

Ejemplo 1

Nombres que empiezan con A:

```sql
SELECT *
FROM empleados
WHERE nombre LIKE 'A%';
```

Resultado:

|---|
|Ana|

---

Ejemplo 2

Nombres que terminan en a:

```sql
SELECT *
FROM empleados
WHERE nombre LIKE '%a';
```

Resultado:

|---|
|Ana|
|Laura|
|María|

---

Ejemplo 3

Nombres que contienen “ar”:

```sql
SELECT *
FROM empleados
WHERE nombre LIKE '%ar%';
```

----

14. NOT LIKE

# ¿Para qué sirve?

Busca textos que NO cumplen un patrón.

Ejemplo

Nombres que no empiezan con A:

```sql
SELECT *
FROM empleados
WHERE nombre NOT LIKE 'A%';
```

Resultado:

|---|
|Carlos|
|Laura|
|Pedro|
|María|

---

Ejemplo completo combinando operadores

- Pregunta:

Mostrar los 3 empleados de Bogotá o Cali,
con salario entre 3000 y 8000,
ordenados por salario mayor.

```sql
SELECT nombre, salario, ciudad
FROM empleados
WHERE ciudad IN ('Bogotá','Cali')
AND salario BETWEEN 3000 AND 8000
ORDER BY salario DESC
LIMIT 3;
```

---

Orden mental para resolver consultas

Primero pensar:

¿Qué me están pidiendo?

|Pregunta|	Usar|
|----|----|
|¿Cuántos?|	COUNT|
|¿Por cada?|	GROUP BY|
|¿Promedio?	|AVG|
|¿Mayor?	|MAX|
|¿Menor?	|MIN|
|¿Total?	|SUM|
|¿Primeros?	|LIMIT|
|¿Saltar?	|OFFSET|
|¿Entre valores?|	BETWEEN|
|¿Lista de opciones?|	IN|
|¿Texto parecido?|	LIKE|

---

Regla rápida:

- COUNT = contar

- GROUP BY = agrupar

- AVG = promedio

- MAX = mayor

- MIN = menor

- SUM = sumar

- LIMIT = cantidad

- OFFSET = saltar

- BETWEEN = rango

- IN = lista

- LIKE = patrón de texto

---

# Introducción a SQLBolt

SQLBolt es una plataforma interactiva para practicar SQL desde el navegador.

Permite:

- Ejecutar consultas
- Ver resultados inmediatos
- Resolver ejercicios guiados
- Practicar sintaxis SQL

---

# Actividad práctica en SQLBolt

Lecciones sugeridas:

- Lesson 1: SELECT queries
- Lesson 2: Queries with constraints
- Lesson 3: Queries with constraints
- Lesson 4: Filtering and sorting

---

# Ejercicios propuestos

## Ejercicio 1

Consultar todos los registros.

```sql
SELECT ALL * FROM Students;
```

---

## Ejercicio 2

Consultar únicamente nombre y ciudad.

```sql
SELECT ALL students_name, students_city
FROM Students;
```

---

## Ejercicio 3

Consultar estudiantes mayores de 20 años.

```sql
SELECT ALL *
FROM Students
WHERE students_age > 20;
```

---

## Ejercicio 4

Consultar estudiantes de Manizales ordenados por edad.

```sql
SELECT ALL *
FROM Students
WHERE students_city = 'Manizales'
ORDER BY students_age ASC;
```

---

## Ejercicio 5

Mostrar únicamente dos registros.

```sql
SELECT ALL *
FROM Students
LIMIT 2;
```

---

# Mini actividad evaluable

## Parte 1

Escribir una consulta que:

- Muestre nombre y ciudad
- Filtre estudiantes mayores de 19 años
- Ordene por nombre

---

## Parte 2

Explicar en papel:

- Qué hace SELECT
- Qué hace WHERE
- Qué hace ORDER BY

---

# Recomendaciones para escribir SQL

- Escribir palabras reservadas en mayúscula
- Mantener indentación clara
- Consultar primero todas las columnas
- Probar consultas simples antes de complejas
- Leer cuidadosamente los errores

---
