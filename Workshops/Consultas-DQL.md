# Guía práctica DQL - Consultas SQL

## Objetivo

Aprender a consultar información almacenada en una base de datos utilizando comandos DQL.

DQL significa:

**Data Query Language**

Su principal comando es:

```sql
SELECT
```

Permite:

- Consultar registros
- Filtrar información
- Ordenar resultados
- Aplicar funciones de agrupación
- Obtener estadísticas


---

# Base de datos utilizada

Esta práctica utiliza una base de datos universitaria con las siguientes tablas:

```
students
teachers
classrooms
subjects
classes
enrollments
```


Relación general:


```
students
    |
    |
enrollments
    |
    |
classes
    |
    |
subjects

teachers
    |
    |
classes

classrooms
    |
    |
classes
```

---

# 1. Consultar todos los registros

## Objetivo

Mostrar toda la información de una tabla.


Sintaxis:

```sql
SELECT *
FROM tabla;
```


Ejemplo:

```sql
SELECT *
FROM students;
```


Resultado:

Muestra todos los estudiantes.


---

# 2. Consultar columnas específicas

No siempre necesitamos todos los datos.

Podemos seleccionar solamente algunas columnas.


Ejemplo:

Mostrar nombre y apellido del estudiante.


```sql
SELECT 
name_student,
lastname_student
FROM students;
```


Resultado:

|nombre|apellido|
|-|-|
|Ana|Lopez|
|Carlos|Perez|


---

# 3. Filtrar información usando WHERE


## ¿Para qué sirve?

WHERE permite colocar condiciones.


Sintaxis:


```sql
SELECT columnas
FROM tabla
WHERE condición;
```


---

Ejemplo:

Buscar estudiantes nacidos después del año 2007:


```sql
SELECT 
name_student,
lastname_student,
birthday_student
FROM students
WHERE birthday_student >= '2007-01-01';
```


---

# 4. Ordenar resultados con ORDER BY


## ¿Para qué sirve?

Organiza los resultados.


Tipos:

ASC

Ascendente


DESC

Descendente


---

Ejemplo:


Ordenar estudiantes por nombre:


```sql
SELECT *
FROM students
ORDER BY name_student ASC;
```


---

Ejemplo:

Ordenar por fecha de nacimiento del más reciente al más antiguo:


```sql
SELECT *
FROM students
ORDER BY birthday_student DESC;
```


---

# 5. ORDER BY con varias columnas


Podemos ordenar utilizando más de una columna.


Ejemplo:


```sql
SELECT 
name_student,
lastname_student,
birthday_student
FROM students
WHERE birthday_student >= '2007-01-01'
ORDER BY 
name_student ASC,
birthday_student DESC;
```


Primero ordena por:

Nombre

Luego por:

Fecha de nacimiento


---

# 6. BETWEEN


## ¿Para qué sirve?

Busca valores dentro de un rango.


Ejemplo:

Estudiantes nacidos durante el año 2007.


```sql
SELECT *
FROM students
WHERE birthday_student 
BETWEEN '2007-01-01'
AND '2007-12-31';
```


Es equivalente a:


```sql
WHERE birthday_student >= '2007-01-01'
AND birthday_student <= '2007-12-31'
```


---

# 7. LIKE


## ¿Para qué sirve?

Buscar patrones de texto.


Símbolos:


|Símbolo|Significado|
|-|-|
|%|cualquier cantidad de caracteres|
|_|un solo carácter|


---

Ejemplo:

Buscar estudiantes cuyo nombre empieza por A y tiene 6 caracteres:


```sql
SELECT *
FROM students
WHERE name_student LIKE 'A_____';
```


Explicación:


```
A + 5 caracteres
```


Ejemplo:

```
Anaaa
Andres
```

---

# 8. IN


## ¿Para qué sirve?

Buscar valores dentro de una lista.


Ejemplo:


Buscar estudiantes nacidos en Manizales o Bogotá.


```sql
SELECT *
FROM students
WHERE city_birth_student IN
(
'Manizales',
'Bogota'
);
```


Equivale a:


```sql
WHERE city_birth_student='Manizales'
OR city_birth_student='Bogota'
```

---

# 9. Combinar WHERE + BETWEEN + LIKE + IN


Esta es una consulta más completa.


Ejemplo:


```sql
SELECT *
FROM students

WHERE birthday_student
BETWEEN '2007-01-01'
AND '2007-12-31'

AND name_student LIKE 'A_____'

AND city_birth_student IN
(
'Manizales',
'Bogota'
)

ORDER BY birthday_student DESC;
```


Aquí aplicamos:

- rango de fechas
- patrón de texto
- lista de valores
- ordenamiento


---

# 10. Contar registros con COUNT()


## ¿Para qué sirve?

Cuenta filas.


Pregunta:

¿Cuántos estudiantes existen?


```sql
SELECT COUNT(*) AS Total_Students
FROM students;
```


Resultado:

|Total_Students|
|-|
|100|

---

# 11. LIMIT


## ¿Para qué sirve?

Limita la cantidad de resultados.


Ejemplo:


Mostrar los 5 estudiantes más recientes:


```sql
SELECT *
FROM students
ORDER BY birthday_student DESC
LIMIT 5;
```


---

# 12. Consultar profesores


Mostrar todos los profesores:


```sql
SELECT *
FROM teachers;
```


---

# 13. Filtrar profesores usando IN


Pregunta:

Mostrar profesores de:

- Ingeniería de Sistemas
- Ciberseguridad


```sql
SELECT *
FROM teachers

WHERE specialization_teacher IN
(
'Ingenieria de Sistemas',
'Ciberseguridad'
);
```


---

# 14. Consultar aulas


```sql
SELECT *
FROM classrooms;
```


---

# 15. Consultar materias


```sql
SELECT *
FROM subjects;
```


---

# 16. Buscar una materia específica


Ejemplo:


Buscar la materia con id 38:


```sql
SELECT name_subject
FROM subjects
WHERE id_subject = 38;
```


---

# 17. Consultar clases


```sql
SELECT *
FROM classes;
```


---

# 18. Consultar matrículas


```sql
SELECT *
FROM enrollments;
```


---

# 19. Contar estudiantes inscritos en una materia


Pregunta:

¿Cuántos estudiantes están matriculados en la materia 38?


```sql
SELECT COUNT(id_subject_enrollment)
FROM enrollments
WHERE id_subject_enrollment = 38;
```


---

# 20. Obtener promedio de notas


Función:

AVG()


Ejemplo:


Promedio de notas de la materia 38:


```sql
SELECT AVG(final_grade_enrollments)
FROM enrollments

WHERE id_subject_enrollment = 38;
```


---

# 21. Obtener nota mínima


Función:

MIN()


Ejemplo:


```sql
SELECT MIN(final_grade_enrollments)

FROM enrollments

WHERE id_subject_enrollment = 38;
```


Resultado:

La nota más baja.


---

# 22. Obtener nota máxima


Función:

MAX()


Ejemplo:


```sql
SELECT MAX(final_grade_enrollments)

FROM enrollments

WHERE id_subject_enrollment = 38;
```


Resultado:

La nota más alta.


---

# 23. Obtener mejores estudiantes de una materia


Ordenamos de mayor a menor:


```sql
SELECT *

FROM enrollments

WHERE id_subject_enrollment = 38

ORDER BY final_grade_enrollments DESC

LIMIT 5;
```


Obtiene:

Los 5 mejores resultados.


---

# Resumen de comandos DQL


|Comando|Uso|
|-|-|
|SELECT|Consultar datos|
|FROM|Indicar tabla|
|WHERE|Filtrar|
|ORDER BY|Ordenar|
|ASC|Ascendente|
|DESC|Descendente|
|BETWEEN|Buscar rangos|
|LIKE|Buscar patrones|
|IN|Buscar listas|
|COUNT|Contar|
|AVG|Promedio|
|MIN|Mínimo|
|MAX|Máximo|
|LIMIT|Limitar resultados|

---

# Orden mental para construir consultas


Siempre piensa:


```
SELECT
      ↓
FROM
      ↓
WHERE
      ↓
ORDER BY
      ↓
LIMIT
```


Ejemplo:

"Muéstrame los 5 mejores estudiantes"


Pensamiento:

1. Mostrar → SELECT
2. Tabla → FROM
3. Mejor nota → ORDER BY DESC
4. Solo 5 → LIMIT


---

# Fin de la práctica

Con estas consultas puedes resolver la mayoría de ejercicios iniciales de SQL DQL.