# Guía práctica: Creación de una Base de Datos Universitaria usando SQL DDL

## Objetivo

Construir paso a paso una base de datos universitaria utilizando comandos DDL de SQL.

Al finalizar tendremos:

- Una base de datos llamada `university_db`
- Tablas relacionadas mediante claves primarias y foráneas
- Restricciones para garantizar integridad de datos

---

# 1. ¿Qué es DDL?

DDL significa:

**Data Definition Language**

Son comandos utilizados para crear y modificar la estructura de una base de datos.

Los comandos principales son:

- CREATE
- DROP
- ALTER
- TRUNCATE

En esta práctica usaremos principalmente:

- CREATE DATABASE
- CREATE TABLE
- DROP TABLE

---

# 2. Crear la base de datos

Antes de crear tablas necesitamos crear la base de datos.

La instrucción:

```sql
DROP DATABASE IF EXISTS university_db;
```

significa:

"Si existe una base de datos llamada university_db, elimínala"

Esto evita errores cuando ejecutamos nuevamente el script.


Ahora creamos la base de datos:

```sql
CREATE DATABASE university_db;
```


Seleccionamos la base de datos:

```sql
USE university_db;
```


Después de este paso todas las tablas serán creadas dentro de:

```
university_db
```

---

# 3. Eliminación de tablas existentes

Antes de crear tablas nuevas eliminamos las tablas antiguas.

Esto permite ejecutar varias veces el script.


```sql
DROP TABLE IF EXISTS enrollments;
DROP TABLE IF EXISTS classes;
DROP TABLE IF EXISTS subjects;
DROP TABLE IF EXISTS teachers;
DROP TABLE IF EXISTS classrooms;
DROP TABLE IF EXISTS students;
```

¿Por qué este orden?

Porque existen relaciones entre tablas.

Ejemplo:

`enrollments` depende de `students` y `classes`.

Primero se eliminan las tablas hijas y luego las tablas padres.

---

# 4. Crear tabla Students

Esta tabla almacenará la información de los estudiantes.


```sql
CREATE TABLE students (

    id_student INT PRIMARY KEY,

    name_student VARCHAR(50) NOT NULL,

    lastname_student VARCHAR(50) NOT NULL,

    email_student VARCHAR(100) UNIQUE NOT NULL,

    birthday_student DATE NOT NULL,

    city_birth_student VARCHAR(50) NOT NULL

) ENGINE=InnoDB;
```


## Explicación


### Llave primaria

```sql
id_student INT PRIMARY KEY
```

Significa:

- Identifica de forma única cada estudiante
- No puede repetirse
- No puede ser NULL


Ejemplo:

Correcto:

|id|
|-|
|1001|
|1002|


Incorrecto:

|id|
|-|
|1001|
|1001|

---

### Restricción NOT NULL

Ejemplo:

```sql
name_student VARCHAR(50) NOT NULL
```

Obliga a guardar un nombre.

No permite:

```sql
NULL
```

---

### Restricción UNIQUE

```sql
email_student VARCHAR(100) UNIQUE
```

Dos estudiantes no pueden tener el mismo correo.

---

# 5. Crear tabla Classrooms

Representa las aulas.


```sql
CREATE TABLE classrooms (

    id_classroom SMALLINT PRIMARY KEY,

    capacity_classroom INT NOT NULL,

    description_classroom TEXT

) ENGINE=InnoDB;
```


Conceptos:

## SMALLINT

Se usa cuando los números serán pequeños.

Ejemplo:

```
1
2
3
4
```

Es más eficiente que INT.

---

# 6. Crear tabla Teachers

Guarda información de profesores.


```sql
CREATE TABLE teachers (

    id_teacher INT PRIMARY KEY,

    name_teacher VARCHAR(50) NOT NULL,

    lastname_teacher VARCHAR(50) NOT NULL,

    email_teacher VARCHAR(100) UNIQUE NOT NULL,

    specialization_teacher VARCHAR(100) NOT NULL

) ENGINE=InnoDB;
```

---

# 7. Crear tabla Subjects

Representa materias.


```sql
CREATE TABLE subjects (

    id_subject SMALLINT PRIMARY KEY,

    name_subject VARCHAR(100) NOT NULL,

    credits_subject INT NOT NULL

) ENGINE=InnoDB;
```


Ejemplo:

|id|materia|créditos|
|-|-|-|
|1|Bases de Datos|3|
|2|Programación|4|

---

# 8. Crear tabla Classes

Esta tabla representa una clase específica.

Ejemplo:

La materia Bases de Datos puede tener:

- Grupo A
- Grupo B


```sql
CREATE TABLE classes (

    id_class INT NOT NULL,

    id_subject_class SMALLINT NOT NULL,

    id_teacher_class INT,

    id_classroom_class SMALLINT,

    semester_class VARCHAR(20) NOT NULL,


    PRIMARY KEY(id_class,id_subject_class)

);
```


---

# Llave primaria compuesta


```sql
PRIMARY KEY(id_class,id_subject_class)
```


Significa que la combinación debe ser única.


Ejemplo permitido:


|id_class|id_subject|
|-|-|
|1|10|
|2|10|


Pero no:


|id_class|id_subject|
|-|-|
|1|10|
|1|10|

---

# 9. Agregar relaciones con FOREIGN KEY


Relacionamos clases con materias:


```sql
CONSTRAINT fk_class_subject

FOREIGN KEY(id_subject_class)

REFERENCES subjects(id_subject)
```


Significa:

Una clase debe tener una materia existente.


---

# ON DELETE CASCADE


```sql
ON DELETE CASCADE
```


Si eliminamos una materia:

```sql
DELETE FROM subjects
WHERE id_subject=1;
```

También se eliminan sus clases relacionadas.


---

# ON DELETE SET NULL


Ejemplo:

```sql
ON DELETE SET NULL
```


Si eliminamos un profesor:

El profesor desaparece,
pero la clase permanece.


El campo queda:

```
id_teacher_class = NULL
```

---

# 10. Crear tabla Enrollments

Representa la matrícula.


```sql
CREATE TABLE enrollments (

id_student_enrollment INT NOT NULL,

id_class_enrollment INT NOT NULL,

id_subject_enrollment SMALLINT NOT NULL,

date_enrollment DATE NOT NULL,

final_grade_enrollments DECIMAL(4,2)

);
```


---

# Llave primaria compuesta


```sql
PRIMARY KEY(
id_student_enrollment,
id_class_enrollment,
id_subject_enrollment
)
```


Un estudiante no puede matricular dos veces la misma clase.


---

# Relación con estudiantes


```sql
FOREIGN KEY(id_student_enrollment)

REFERENCES students(id_student)
```


Ejemplo:

No se puede matricular:

```text
Estudiante 9999
```

si no existe.

---

# Relación con clases


```sql
FOREIGN KEY(
id_class_enrollment,
id_subject_enrollment
)

REFERENCES classes(
id_class,
id_subject_class
)
```


Es una relación con llave primaria compuesta.

---

# 11. Modelo final de relaciones


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


classes
    |
    |
teachers


classes
    |
    |
classrooms

```

---

# 12. Verificar tablas creadas


Ejecutar:


```sql
SHOW TABLES;
```


Resultado esperado:


```
students
teachers
subjects
classrooms
classes
enrollments
```

---

# 13. Consultar estructura


Para ver una tabla:


```sql
DESCRIBE students;
```


o:


```sql
SHOW CREATE TABLE students;
```


---

# Conceptos aprendidos


|Concepto|Uso|
|-|-|
|CREATE DATABASE|Crear BD|
|CREATE TABLE|Crear tablas|
|DROP TABLE|Eliminar tablas|
|PRIMARY KEY|Identificador único|
|FOREIGN KEY|Relación entre tablas|
|NOT NULL|Campo obligatorio|
|UNIQUE|Valores no repetidos|
|CASCADE|Eliminar relaciones automáticamente|
|SET NULL|Mantener registro pero quitar relación|

---

# Fin de la práctica

La base de datos universitaria queda lista para insertar datos y realizar consultas SQL.