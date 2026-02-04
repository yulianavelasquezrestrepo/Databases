# Transformación de Relaciones a Tablas

## Objetivo del tema
Comprender cómo transformar correctamente las relaciones del Modelo Entidad-Relación (MER) al modelo relacional, especialmente las relaciones uno a uno (1:1) y uno a muchos (1:N).

---

## Relación entre MER y modelo relacional

En el MER:
- las relaciones describen asociaciones conceptuales entre entidades.

En el modelo relacional:
- estas relaciones se implementan mediante claves foráneas,
- o, en casos específicos, mediante tablas adicionales.

La forma de transformación depende del tipo de relación.

---

## Transformación de relaciones uno a muchos (1:N)

### Regla general

En una relación 1:N:
- la clave primaria de la entidad del lado “uno”
- se agrega como clave foránea en la tabla del lado “muchos”.

---

### Ejemplo

Relación MER:
- Departamento — tiene — Empleado (1:N)

Transformación:
- Departamento (department_id, department_name)
- Empleado (employee_id, employee_name, department_id)

La clave foránea `department_id` en Empleado representa la relación.

---

### Opcionalidad en relaciones 1:N

Si la relación es:
- obligatoria → la clave foránea no debe permitir valores nulos,
- opcional → la clave foránea puede ser nula.

Esta decisión debe basarse en las reglas del negocio.

---

## Transformación de relaciones uno a uno (1:1)

Las relaciones 1:1 requieren análisis adicional.

### Opción 1: clave foránea en una de las tablas

Se elige una de las entidades para almacenar la clave foránea.

Criterios comunes:
- la entidad con participación total,
- la entidad con menos atributos.

---

### Ejemplo

Relación MER:
- Persona — tiene — Pasaporte (1:1)

Transformación:
- Persona (person_id, name)
- Pasaporte (passport_id, person_id)

---

### Opción 2: fusión de entidades

Si ambas entidades:
- tienen participación total,
- tienen sentido conceptual conjunto,

pueden fusionarse en una sola tabla.

Ejemplo:
- Usuario y Perfil.

---

## Relaciones con atributos propios

Si una relación tiene atributos propios:
- se puede convertir en una tabla independiente,
- incluso si es 1:1 o 1:N.

Ejemplo:
- Contrato entre Empleado y Empresa con fecha_inicio.

---

## Error común: crear tablas innecesarias

Ejemplo incorrecto:
- crear una tabla adicional para una relación 1:N sin atributos propios.

Esto:
- complica el diseño,
- no aporta valor.

---

## Error común: colocar la clave foránea en el lado incorrecto

Ejemplo incorrecto:
- colocar la clave foránea en el lado “uno”.

Esto:
- limita la relación,
- viola las reglas del modelo relacional.

---

## Ejemplo comparativo

Relación MER:
- Cliente — realiza — Pedido (1:N)

Transformación correcta:
- Cliente (customer_id, customer_name)
- Pedido (order_id, order_date, customer_id)

Transformación incorrecta:
- Cliente (customer_id, customer_name, order_id)

---

## Reglas prácticas para transformar relaciones

Al transformar relaciones:
- identificar el tipo (1:1, 1:N, N:M),
- colocar la clave foránea en el lado correcto,
- considerar opcionalidad,
- evaluar si la relación tiene atributos propios.

---

## Importancia de la correcta transformación

Una transformación correcta:
- garantiza coherencia del modelo,
- evita redundancia,
- facilita la implementación en SQL,
- asegura consultas correctas.

La transformación de relaciones es el paso final antes de crear tablas reales.

---