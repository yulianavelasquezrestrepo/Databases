# Claves Primarias (Primary Keys)

## Objetivo del tema
Comprender qué es una clave primaria, por qué es necesaria en el modelo relacional y cómo se define correctamente para garantizar la identificación única de los registros.

---

## ¿Qué es una clave primaria?

Una **clave primaria** es un atributo o conjunto de atributos que **identifica de forma única cada fila** dentro de una tabla.

Su propósito principal es:
- diferenciar un registro de todos los demás,
- permitir el acceso preciso a la información,
- servir como punto de referencia para relaciones con otras tablas.

---

## Características de una clave primaria

Una clave primaria debe cumplir las siguientes reglas:

- **Unicidad**: no pueden existir dos filas con el mismo valor.
- **No nula**: no puede tener valores nulos.
- **Estabilidad**: su valor no debería cambiar en el tiempo.
- **Minimalidad**: no debe contener atributos innecesarios.

Si un atributo no cumple estas reglas, **no es una buena clave primaria**.

---

## Tipos de claves primarias

### Clave primaria simple

Está compuesta por **un solo atributo**.

Ejemplo:
- student_id
- employee_id
- product_code

Es el tipo más común y recomendado cuando es posible.

---

### Clave primaria compuesta

Está formada por **dos o más atributos**.

Ejemplo:
- (student_id, course_id) en una tabla de inscripciones.

Se utiliza generalmente en:
- entidades asociativas,
- resolución de relaciones muchos a muchos (N:M).

---

## Claves primarias y entidades

### Entidades fuertes
- Tienen una clave primaria propia.
- Pueden existir de forma independiente.

Ejemplo:
- Estudiante
- Cliente
- Producto

---

### Entidades débiles
- Dependen de otra entidad para existir.
- Su clave primaria incluye la clave de la entidad fuerte.

Ejemplo:
- DetallePedido depende de Pedido.
- Clave primaria: (order_id, line_number)

---

## Ejemplo práctico

Tabla: Estudiante

| student_id | student_name | email |
|------------|--------------|-------|
| 1          | Ana López    | ana@mail.com |
| 2          | Juan Pérez   | juan@mail.com |

En este caso:
- `student_id` identifica de forma única a cada estudiante.
- Es una clave primaria adecuada.

---

## Ejemplo incorrecto de clave primaria

Usar atributos no adecuados como clave primaria:

| student_name | birth_date |
|--------------|------------|
| Ana López    | 2002-05-10 |

**Problemas:**
- Los nombres se repiten.
- La fecha de nacimiento puede cambiar o coincidir.

Este diseño es incorrecto.

---

## Claves naturales vs claves artificiales

### Clave natural
- Tiene significado en el mundo real.
- Ejemplo: número de documento, código de producto.

Ventaja:
- Es comprensible.

Desventaja:
- Puede cambiar o tener restricciones externas.

---

### Clave artificial (surrogada)

- No tiene significado en el negocio.
- Generalmente es un número autoincremental.

Ejemplo:
- id = 1, 2, 3...

Ventaja:
- Es estable y simple.

Por esta razón, es la más utilizada en sistemas reales.

---

## Relación entre clave primaria y normalización

Una clave primaria mal definida puede:
- ocultar dependencias funcionales,
- provocar violaciones de 2FN o 3FN,
- generar redundancia.

Definir correctamente la clave primaria es esencial para un diseño normalizado.

---

## Error común: no definir clave primaria

Una tabla sin clave primaria:
- no puede garantizar unicidad,
- dificulta las relaciones,
- genera inconsistencias.

Toda tabla en el modelo relacional **debe tener una clave primaria**.

---

## Importancia de la clave primaria

La clave primaria:
- asegura la integridad de los datos,
- permite relacionar tablas,
- es la base de la integridad referencial,
- facilita las consultas y actualizaciones.

Sin claves primarias, el modelo relacional no funciona correctamente.

---