# Introducción al DDL en MySQL

## Objetivo del tema
Comprender qué es el DDL (Data Definition Language) y aprender a crear bases de datos y tablas básicas en MySQL utilizando instrucciones SQL fundamentales.

---

# ¿Qué es DDL?

DDL significa:

> Data Definition Language  
> Lenguaje de Definición de Datos

Es el conjunto de instrucciones SQL utilizado para:
- crear estructuras,
- modificar estructuras,
- eliminar estructuras dentro de una base de datos.

DDL trabaja sobre:
- bases de datos,
- tablas,
- columnas,
- restricciones.

---

# Principales comandos DDL

| Comando | Función |
|---|---|
| CREATE | Crear objetos |
| ALTER | Modificar estructuras |
| DROP | Eliminar objetos |
| TRUNCATE | Vaciar tablas |
| RENAME | Renombrar objetos |

---

# CREATE DATABASE

## ¿Para qué sirve?

Permite crear una nueva base de datos.

---

## Sintaxis

```sql
CREATE DATABASE nombre_base_datos;
```

---

## Ejemplo

```sql
CREATE DATABASE university_db;
```

# Buenas prácticas

Se recomienda:

* usar nombres claros,
* evitar espacios,
* utilizar minúsculas y guiones bajos.

## Ejemplos Correctos

```sql
CREATE DATABASE library_db;

CREATE DATABASE sales_system;
```

## Ejemplos Incorrectos
```sql
CREATE DATABASE Base de Datos;

CREATE DATABASE 123test;
```

---

# USE

¿Para qué sirve?

Selecciona la base de datos con la que se trabajará.

## Sintaxis

```sql
USE nombre_base_datos;
```

## Ejemplo

```sql
USE university_db;
```

---

# CREATE TABLE

¿Para qué sirve?

Permite crear tablas dentro de una base de datos.

## Sintaxis Básica

```sql
CREATE TABLE nombre_tabla (
    columna tipo_dato,
    columna tipo_dato
);
```

## Tipos de datos básicos

|Tipo|Descripción|
|---|---|
|INT|Números Enteros|
|VARCHAR(n)|Texto corto|
|DATE|Fechas|
|DECIMAL|Números decimales|
|BOOLEAN|Verdadero/Falso|

## Ejemplo Simple de tabla

```sql
CREATE TABLE students (
    student_id INT,
    student_first_name VARCHAR(50),
    student_last_name VARCHAR(50),
    student_age INT
);
```

# Clave primaria (PRIMARY KEY)

¿Qué es?

Es un atributo que:

* identifica de forma única cada registro,
* no puede repetirse,
* no puede ser nulo.

## Ejemplo

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    student_first_name VARCHAR(50),
    student_last_name VARCHAR(50)
);
```

# Restricción NOT NULL

¿Qué hace?

Obliga a que una columna tenga valor.

## Ejemplo

```sql
CREATE TABLE teachers (
    teacher_id INT PRIMARY KEY,
    teacher_name VARCHAR(100) NOT NULL
);
```

# Clave foránea (FOREIGN KEY)

¿Qué es?

Es una columna que:

* conecta una tabla con otra,
* representa relaciones entre entidades.

⸻

## Ejemplo de relación

Tabla departamentos:

```sql
CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);
```

Tabla Empleados:

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    employee_department_id INT,
    FOREIGN KEY (employee_department_id)
        REFERENCES departments(department_id)
);
```

---

# DROP DATABASE

¿Qué hace?

Elimina completamente una base de datos.

## Sintaxis

```sql
DROP DATABASE nombre_db;
```

## Ejemplo

```sql
DROP DATABASE company_db;
```

---

# DROP TABLE

¿Qué hace?

Elimina una tabla.

## Ejemplo

```sql
DROP TABLE employees;
```

# ALTER TABLE

¿Qué hace?

Modifica la estructura de una tabla existente.

## Ejemplo: Agregar una nueva columna a la tabla

```sql
ALTER TABLE users 
ADD telephone_user VARCHAR(20);
```

## Ejemplo: Borrar una columna existente en una tabla

```sql
ALTER TABLE users 
DROP COLUMN telephone_user;
```

## Ejemplo: Modificar tamaño o tipo de dato de una columna existente en una tabla

```sql
ALTER TABLE users 
MODIFY COLUMN name_users VARCHAR(100);
```

## Ejemplo: Modificar el nombre de una columna existente en una tabla

```sql
ALTER TABLE users 
RENAME COLUMN correo_user TO email_user;
```

# TRUNCATE TABLE

¿Qué hace?

Elimina los todos los datos que tiene una tabla.

## Ejemplo

```sql
TRUNCATE TABLE users;
```

# RENAME TABLE

¿Qué hace?

Renombra o cambia el nombre de una tabla.

## Ejemplo

```sql
RENAME TABLE users TO clients;
```

## Recomendaciones para trabajar en DDL

Durante las prácticas:

* escribir manualmente las instrucciones,
* ejecutar paso a paso,
* revisar errores antes de continuar,
* usar nombres claros y consistentes.

