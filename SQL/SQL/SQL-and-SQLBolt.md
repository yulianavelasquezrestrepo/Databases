# Introducción a Consultas SQL y SQLBolt

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
SELECT * FROM Students;
```

---

# La instrucción SELECT

La instrucción SELECT permite consultar información almacenada en una tabla.

Sintaxis básica:

```sql
SELECT columnas
FROM tabla;
```

---

## Consultar todas las columnas

```sql
SELECT * FROM Students;
```

El símbolo `*` representa todas las columnas.

---

## Consultar columnas específicas

```sql
SELECT students_name, students_city
FROM Students;
```

---

# Base de datos de práctica

Durante la sesión se trabajará con tablas sencillas.

## Tabla: Students

| id | name   | city      | age |
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
SELECT columnas
FROM tabla
WHERE condicion;
```

---

## Ejemplo 1

```sql
SELECT *
FROM Students
WHERE students_city = 'Manizales';
```

---

## Ejemplo 2

```sql
SELECT students_name, students_age
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
SELECT *
FROM Students
WHERE students_city = 'Manizales'
AND students_age > 20;
```

---

## OR

Al menos una condición debe cumplirse.

```sql
SELECT *
FROM Students
WHERE students_city = 'Pereira'
OR students_city = 'Armenia';
```

---

# Ordenamiento de resultados

## ORDER BY ASC

Orden ascendente.

```sql
SELECT *
FROM Students
ORDER BY students_age ASC;
```

---

## ORDER BY DESC

Orden descendente.

```sql
SELECT *
FROM Students
ORDER BY students_age DESC;
```

---

# Limitar resultados

## LIMIT

Permite limitar la cantidad de registros mostrados.

```sql
SELECT *
FROM Students
LIMIT 2;
```

---

# Alias de columnas

Los alias permiten cambiar temporalmente el nombre mostrado.

```sql
SELECT student_name AS studentName,
       student_city AS studentCity
FROM Students;
```

---

# Consultas combinadas

Ejemplo completo:

```sql
SELECT students_name, students_city, students_age
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
SELECT * FROM Students
```

Correcto:

```sql
SELECT * FROM Students;
```

---

## Escribir mal nombres de columnas

Incorrecto:

```sql
SELECT student_name FROM Students;
```

Correcto:

```sql
SELECT students_name FROM Students;
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
SELECT * FROM Students;
```

---

## Ejercicio 2

Consultar únicamente nombre y ciudad.

```sql
SELECT students_name, students_city
FROM Students;
```

---

## Ejercicio 3

Consultar estudiantes mayores de 20 años.

```sql
SELECT *
FROM Students
WHERE students_age > 20;
```

---

## Ejercicio 4

Consultar estudiantes de Manizales ordenados por edad.

```sql
SELECT *
FROM Students
WHERE students_city = 'Manizales'
ORDER BY students_age ASC;
```

---

## Ejercicio 5

Mostrar únicamente dos registros.

```sql
SELECT *
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

# Resumen de la sesión

En esta sesión se trabajó:

- Introducción a SQL
- Consultas básicas con SELECT
- Filtrado con WHERE
- Ordenamiento con ORDER BY
- Uso de LIMIT
- Uso de alias
- Práctica guiada en SQLBolt
- Interpretación de resultados