# Ejecución de Scripts SQL desde la Línea de Comandos

## Objetivo

Ejecutar archivos .sql desde Windows y macOS utilizando MySQL.

---

# Crear Archivo SQL

Crear archivo:

```cmd
setup.sql
``` 

Contenido:

```sql
CREATE DATABASE empresa;  

USE empresa;  

CREATE TABLE empleados (     
    id_empleado INT AUTO_INCREMENT PRIMARY KEY,     
    nombre_empleado VARCHAR(100),     
    cargo_empleado VARCHAR(100) 
    );  
    
INSERT INTO empleados(nombre_empleado, cargo_empleado) VALUES ('Laura Díaz', 'Gerente'), ('Pedro Torres', 'Analista');  
    
SELECT * FROM empleados;
```

```cmd
Guardar el archivo.
```

---

# Ejecutar Script desde MySQL

## Windows

Conectarse:

cmd:

```cmd
mysql -u root -p
``` 

Ejecutar:

```cmd
SOURCE C:/Users/usuario/Documents/setup.sql;
``` 

---

## macOS

Conectarse:

```bash
/usr/local/mysql/bin/mysql -u root -p
``` 

Ejecutar:

```bash
SOURCE /Users/usuario/Documents/setup.sql; 
```

---

# Ejecutar Script directamente desde la Terminal

## Windows

```cmd
mysql -u root -p < C:\Users\usuario\Documents\setup.sql
``` 

Si MySQL no está en el PATH:

```cmd
"C:\Program Files\MySQL\MySQL Server 9.0\bin\mysql.exe" -u root -p < C:\Users\usuario\Documents\setup.sql
``` 

---

## macOS

```bash 
/usr/local/mysql/bin/mysql -u root -p < /Users/usuario/Documents/setup.sql
``` 

---

# Ejecutar script desde la carpeta actual

Suponga que:

```cmd
setup.sql
``` 

está en la carpeta actual.

---

## Windows

```cmd
mysql -u root -p < setup.sql
``` 

---

## macOS

```bash
/usr/local/mysql/bin/mysql -u root -p < setup.sql
``` 

---

# Verificar Resultados

Conectarse nuevamente:

```cmd
mysql -u root -p
``` 

o

```bash
/usr/local/mysql/bin/mysql -u root -p
``` 

Consultar:

```sql
SHOW DATABASES;  

USE empresa;

SHOW TABLES;  

SELECT * FROM empleados;
``` 

---

