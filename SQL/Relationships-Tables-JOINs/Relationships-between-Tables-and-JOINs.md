# Relaciones entre Tablas y JOINs

# Introducción

En las bases de datos relacionales, la información normalmente se encuentra distribuida en múltiples tablas.

Las relaciones entre tablas permiten:

- Evitar redundancia
- Organizar mejor los datos
- Mantener integridad
- Consultar información relacionada

En esta sesión se trabajará principalmente:

- Relaciones entre tablas
- Claves foráneas
- JOINs
- Consultas combinadas
- Interpretación de resultados

---

# Recordatorio: claves primarias y foráneas

## Clave primaria (PRIMARY KEY)

Una clave primaria identifica de forma única cada registro de una tabla.

Ejemplo:

```sql
CREATE TABLE Students (
    students_id INT PRIMARY KEY,
    students_name VARCHAR(100)
);
```

---

## Clave foránea (FOREIGN KEY)

Una clave foránea conecta una tabla con otra.

Ejemplo:

```sql
CREATE TABLE Courses (
    courses_id INT PRIMARY KEY,
    courses_name VARCHAR(100),
    courses_student_id INT,
    FOREIGN KEY (courses_student_id) REFERENCES Students(students_id)
);
```

---

# Relaciones entre tablas

## Relación uno a muchos

Es la relación más común.

Ejemplo:

- Un estudiante puede tener muchos cursos.
- Un curso pertenece a un estudiante.

---

# Base de datos de práctica

## Tabla: Students

| students_id | students_name   | students_city      |
|----|--------|-----------|
| 1  | Sofía  | Manizales |
| 2  | Carlos | Pereira   |
| 3  | Ana    | Armenia   |

---

## Tabla: Courses

| courses_id | courses_name       | courses_student_id |
|----|-------------------|------------|
| 1  | Databases         | 1          |
| 2  | Programming       | 1          |
| 3  | Networks          | 2          |
| 4  | Operating Systems | 3          |

---

# ¿Qué es un JOIN?

Un JOIN permite combinar información de múltiples tablas relacionadas.

Gracias a los JOINs es posible:

- Consultar información distribuida
- Relacionar registros
- Construir reportes
- Obtener datos más completos

---

# INNER JOIN

El INNER JOIN retorna únicamente los registros que tienen coincidencia en ambas tablas.

Sintaxis:

```sql
SELECT registros columnas
FROM tabla1
INNER JOIN tabla2
ON condicion;
```

---

# Primer ejemplo de INNER JOIN

```sql
SELECT ALL Students.students_name,
       Courses.courses_name
FROM Students
INNER JOIN Courses
ON Students.students_id = Courses.courses_student_id;
```

---

# Resultado esperado

| students_name   | courses_name       |
|--------|-------------------|
| Sofía  | Databases         |
| Sofía  | Programming       |
| Carlos | Networks          |
| Ana    | Operating Systems |

---

# Explicación del JOIN

```sql
ON Students.students_id = Courses.courses_student_id
```

Esta condición indica:

- El `students_id` del estudiante
- Debe coincidir con el `courses_student_id` del curso

---

# Uso de alias en tablas

Los alias simplifican consultas largas.

Ejemplo:

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# JOIN con múltiples columnas

```sql
SELECT ALL s.students_name,
       s.students_city,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# Filtrado después de un JOIN

Es posible usar WHERE junto con JOIN.

Ejemplo:

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id
WHERE s.students_city = 'Manizales';
```

---

# Ordenamiento después de un JOIN

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id
ORDER BY s.students_name ASC;
```

---

# LEFT JOIN

El LEFT JOIN retorna:

- Todos los registros de la tabla izquierda
- Y las coincidencias de la tabla derecha

Si no existe coincidencia:

- Se muestran valores NULL

---

# Ejemplo de LEFT JOIN

## Nueva tabla Students

| students_id | students_name   |
|----|--------|
| 1  | Sofía  |
| 2  | Carlos |
| 3  | Ana    |
| 4  | Miguel |

---

## Tabla Courses

| courses_id | courses_name | courses_student_id |
|----|-------------|------------|
| 1  | Databases   | 1          |
| 2  | Programming | 2          |

---

## Consulta

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
LEFT JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# Resultado esperado

| students_name   | courses_name |
|--------|-------------|
| Sofía  | Databases   |
| Carlos | Programming |
| Ana    | NULL        |
| Miguel | NULL        |

---

# RIGHT JOIN

El RIGHT JOIN retorna:

- Todos los registros de la tabla derecha
- Y las coincidencias de la tabla izquierda

Si no existe coincidencia:

- Se muestran valores NULL en las columnas de la tabla izquierda

---

# Ejemplo de RIGHT JOIN

## Tabla Students

| students_id | students_name   |
|----|--------|
| 1  | Sofía  |
| 2  | Carlos |

---

## Tabla Courses

| courses_id | courses_name | courses_student_id |
|----|-------------|------------|
| 1  | Databases   | 1          |
| 2  | Programming | 2          |
| 3  | Networks    | 5          |

---

## Consulta

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
RIGHT JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# Resultado esperado

| students_name   | courses_name |
|--------|-------------|
| Sofía  | Databases   |
| Carlos | Programming |
| NULL   | Networks    |

---

# Explicación del RIGHT JOIN

El curso "Networks" tiene un `courses_student_id = 5`.

Sin embargo:

- No existe un estudiante con id 5 en la tabla Students.

Por esta razón:

- El RIGHT JOIN conserva el registro de la tabla derecha (Courses)
- Y muestra NULL en las columnas de Students

---

# Diferencia entre INNER JOIN, LEFT JOIN y RIGHT JOIN

## INNER JOIN

Muestra únicamente coincidencias entre ambas tablas.

## LEFT JOIN

Muestra todos los registros de la tabla izquierda aunque no tengan coincidencia.

## RIGHT JOIN

Muestra todos los registros de la tabla derecha aunque no tengan coincidencia.

---

# Comparación visual de JOINs

| Tipo de JOIN | Resultado |
|---|---|
| INNER JOIN | Solo coincidencias |
| LEFT JOIN | Todos los registros de la izquierda |
| RIGHT JOIN | Todos los registros de la derecha |

---

# JOINs y modelo relacional

Los JOINs existen gracias a:

- Claves primarias
- Claves foráneas
- Relaciones entre entidades

Por eso el diseño correcto del modelo relacional es fundamental.

---

# Errores comunes en JOINs

## Olvidar condición ON

Incorrecto:

```sql
SELECT ALL *
FROM Students
INNER JOIN Courses;
```

Correcto:

```sql
SELECT ALL *
FROM Students
INNER JOIN Courses
ON Students.id = Courses.student_id;
```

---

## Usar columnas incorrectas

Incorrecto:

```sql
ON Students.students_name = Courses.courses_id
```

Correcto:

```sql
ON Students.students_id = Courses.courses_student_id
```

---

## Ambigüedad de columnas

Incorrecto:

```sql
SELECT ALL students_id
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id;
```

Correcto:

```sql
SELECT s.students_id
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# Consultas prácticas

## Consulta 1

Mostrar estudiantes y sus cursos.

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

## Consulta 2

Mostrar estudiantes de Manizales y sus cursos.

```sql
SELECT ALL s.students_name,
       s.students_city,
       c.courses_name
FROM Students s
INNER JOIN Courses c
ON s.students_id = c.courses_student_id
WHERE s.students_city = 'Manizales';
```

---

## Consulta 3

Mostrar todos los estudiantes incluso si no tienen cursos.

```sql
SELECT ALL s.name,
       c.courses_name
FROM Students s
LEFT JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

## Consulta 4

Mostrar todos los cursos incluso si no tienen estudiante asociado.

```sql
SELECT ALL s.students_name,
       c.courses_name
FROM Students s
RIGHT JOIN Courses c
ON s.students_id = c.courses_student_id;
```

---

# Actividad práctica guiada

## Parte 1

Crear las tablas:

- Students
- Courses

---

## Parte 2

Insertar registros de prueba.

---

## Parte 3

Realizar consultas:

- SELECT básicos
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- WHERE
- ORDER BY

---

# Mini actividad evaluable

## Parte 1

Escribir una consulta que muestre:

- Nombre del estudiante
- Ciudad
- Curso

---

## Parte 2

Explicar en papel:

- Qué hace INNER JOIN
- Qué hace LEFT JOIN
- Qué hace RIGHT JOIN
- Diferencias entre ellos

---

# Buenas prácticas

- Usar alias en tablas
- Indentar consultas
- Nombrar claramente las columnas
- Probar consultas simples antes de complejas
- Verificar relaciones correctamente

---

# Recomendación práctica

En muchos proyectos reales:

- LEFT JOIN es más utilizado que RIGHT JOIN

Sin embargo:

- Es importante comprender ambos
- Porque representan la misma lógica desde perspectivas opuestas

---

# Resumen de la sesión

En esta sesión se trabajó:

- Relaciones entre tablas
- Claves foráneas
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- Filtrado y ordenamiento con JOINs
- Uso de alias
- Interpretación de resultados
- Consultas relacionales