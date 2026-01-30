# Modelo de Datos Relacional

## ¿Qué es el modelo relacional?
El modelo relacional es un modelo de datos que organiza la información en **tablas** compuestas por filas y columnas.

Cada tabla representa una entidad del mundo real y cada fila representa un registro único.

---

## Elementos del modelo relacional

### Tabla
Estructura que almacena datos relacionados entre sí.

### Fila (Tupla)
Representa un registro único dentro de una tabla.

### Columna (Atributo)
Representa una característica de la entidad.

### Dominio
Conjunto de valores válidos que puede tomar un atributo.

---

## Llave primaria (Primary Key)
Es un atributo o conjunto de atributos que:
- Identifica de manera única cada registro
- No permite valores nulos
- No se repite

Ejemplos:
- Número de identificación
- Código de estudiante
- ID autoincremental

---

## Llave foránea (Foreign Key)
Es un atributo que establece una relación entre dos tablas.

Características:
- Apunta a una llave primaria de otra tabla
- Garantiza la relación entre los datos
- Permite mantener la integridad referencial

---

## Relaciones entre tablas
Las tablas pueden relacionarse de diferentes formas:
- Uno a uno (1:1)
- Uno a muchos (1:N)
- Muchos a muchos (N:M)

Estas relaciones permiten modelar escenarios reales de manera estructurada.

---

## Integridad de los datos

### Integridad de entidad
Garantiza que cada tabla tenga una llave primaria válida.

### Integridad referencial
Garantiza que las relaciones entre tablas sean consistentes, evitando referencias a registros inexistentes.

---

## Ventajas del modelo relacional
- Organización clara de la información
- Facilidad para consultar datos
- Reducción de redundancia
- Base para el uso del lenguaje SQL
