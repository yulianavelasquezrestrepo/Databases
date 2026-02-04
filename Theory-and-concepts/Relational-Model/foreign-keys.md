# Claves Foráneas (Foreign Keys)

## Objetivo del tema
Comprender qué es una clave foránea, cómo funciona dentro del modelo relacional y por qué es fundamental para representar relaciones entre tablas y garantizar la integridad de los datos.

---

## ¿Qué es una clave foránea?

Una **clave foránea** es un atributo o conjunto de atributos en una tabla que **hace referencia a la clave primaria de otra tabla**.

Su función principal es:
- establecer relaciones entre tablas,
- garantizar coherencia entre los datos relacionados,
- representar las relaciones definidas en el Modelo Entidad-Relación (MER).

---

## Relación entre clave primaria y clave foránea

- La **clave primaria** identifica un registro de forma única.
- La **clave foránea** apunta a ese identificador en otra tabla.

Ejemplo conceptual:
- Tabla Cliente → clave primaria: `customer_id`
- Tabla Pedido → clave foránea: `customer_id`

Esto indica que cada pedido pertenece a un cliente.

---

## Representación de relaciones 1:N

La relación **uno a muchos (1:N)** se implementa colocando la clave foránea en el lado “muchos”.

Ejemplo:
- Cliente (1) — Pedido (N)

Implementación:
- La tabla Pedido contiene `customer_id` como clave foránea.

Esto permite que:
- un cliente tenga muchos pedidos,
- cada pedido pertenezca a un solo cliente.

---

## Claves foráneas y relaciones muchos a muchos (N:M)

Las relaciones **muchos a muchos** no se implementan directamente.

Se resuelven mediante una **tabla intermedia** (entidad asociativa) que contiene:
- la clave primaria de la primera tabla,
- la clave primaria de la segunda tabla.

Ejemplo:
- Estudiante — Curso

Tabla intermedia:
- Inscripción (student_id, course_id)

Ambos atributos son claves foráneas y, juntos, forman la clave primaria.

---

## Claves foráneas y entidades débiles

En entidades débiles:
- la clave foránea hacia la entidad fuerte
- forma parte de la clave primaria.

Ejemplo:
- Pedido → DetallePedido

Clave primaria de DetallePedido:
- (order_id, line_number)

Aquí, `order_id` es clave foránea y parte de la clave primaria.

---

## Integridad referencial

La **integridad referencial** garantiza que:

- una clave foránea debe corresponder a un valor existente en la tabla referenciada,
- no pueden existir referencias a registros inexistentes.

Ejemplo:
- No puede existir un pedido con un `customer_id` que no exista en Cliente.

---

## Acciones sobre claves foráneas

Conceptualmente, al trabajar con claves foráneas se deben definir reglas como:
- qué sucede si se elimina un registro referenciado,
- qué sucede si se actualiza una clave primaria.

Estas reglas se definen en la implementación, pero deben considerarse desde el diseño.

---

## Ejemplo completo

Tablas:

Cliente

| customer_id | customer_name |
|-------------|----------------|
| 1           | Ana López     |

Pedido

| order_id | order_date | customer_id |
|----------|------------|-------------|
| 1001     | 2024-05-10 | 1           |

La clave foránea `customer_id` en Pedido garantiza que el pedido pertenece a un cliente válido.

---

## Error común: usar atributos descriptivos como clave foránea

Ejemplo incorrecto:
- Usar `customer_name` como referencia.

Problemas:
- Los nombres no son únicos.
- Pueden cambiar.

La clave foránea siempre debe apuntar a una **clave primaria**.

---

## Error común: permitir valores nulos sin analizar la relación

Permitir valores nulos en una clave foránea implica:
- que la relación sea opcional,
- que la entidad pueda existir sin estar relacionada.

Esto debe definirse explícitamente según las reglas del negocio.

---

## Importancia de las claves foráneas

Las claves foráneas:
- representan las relaciones del MER,
- mantienen la coherencia entre tablas,
- evitan datos huérfanos,
- permiten consultas relacionales correctas.

Son esenciales para el correcto funcionamiento de una base de datos relacional.

---