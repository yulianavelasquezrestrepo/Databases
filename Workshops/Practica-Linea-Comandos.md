# Práctica de Línea de Comandos MySQL

## Objetivo

Aprender a conectarse a MySQL desde la terminal y ejecutar instrucciones SQL básicas.

---

# Conexión a MySQL

## Windows

```cmd 
mysql -u root -p
```

---

## macOS

```bash 
/usr/local/mysql/bin/mysql -u root -p
``` 

---

# Consultar Versión

```sql
SELECT VERSION();
``` 

---

# Consultar Bases de Datos

```sql
SHOW DATABASES;
``` 

---

# Crear Base de Datos

```sql
CREATE DATABASE universidad;
``` 

Verificar:

```sql
SHOW DATABASES;
``` 

---

# Seleccionar Base de Datos

```sql
USE universidad;
``` 

---

# Crear Tabla

```sql
CREATE TABLE estudiantes (     
    id INT AUTO_INCREMENT PRIMARY KEY,     
    nombre VARCHAR(100),     
    correo VARCHAR(100) 
    );
``` 

---

# Consultar Tablas

```sql
SHOW TABLES;
``` 

---

# Ver Estructura de Tabla

```sql
DESCRIBE estudiantes;
``` 

---

# Insertar Datos

```sql
INSERT INTO estudiantes(nombre, correo) VALUES ('Juan Pérez', 'juan@correo.com');
``` 

---

# Consultar Datos

```sql
SELECT * FROM estudiantes;
``` 

---

# Insertar Más Registros

```sql
INSERT INTO estudiantes(nombre, correo) VALUES ('Ana Gómez', 'ana@correo.com'), ('Carlos Ruiz', 'carlos@correo.com');
``` 

---

# Consultar Registros

```sql
SELECT * FROM estudiantes;
``` 

---

# Eliminar Tabla

```sql
DROP TABLE estudiantes;
``` 

Verificar:

```sql
SHOW TABLES;
``` 

---

# Eliminar Base de Datos

```sql
DROP DATABASE universidad;
``` 

Verificar:

```sql
SHOW DATABASES;
``` 

---

# Salir de MySQL

```sql
EXIT; 
```

---

# Actividad

Realizar las siguientes acciones:

1. Crear una base de datos llamada biblioteca.
2. Crear una tabla llamada libros.
3. Insertar tres registros.
4. Consultar los registros.
5. Eliminar la tabla.
6. Eliminar la base de datos.