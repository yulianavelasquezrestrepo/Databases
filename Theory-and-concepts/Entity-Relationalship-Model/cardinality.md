# Cardinalidad

## Objetivo del tema
Comprender el concepto de cardinalidad en el Modelo Entidad-Relación (MER), identificar los distintos tipos de cardinalidad entre entidades y aplicarlos correctamente en el diseño conceptual de bases de datos.

---

## ¿Qué es la cardinalidad?

La **cardinalidad** describe **cuántas ocurrencias de una entidad** pueden o deben asociarse con ocurrencias de otra entidad a través de una relación.

La cardinalidad responde preguntas como:
- ¿Cuántos registros de una entidad pueden relacionarse con otra?
- ¿La relación es única, múltiple u obligatoria?

---

## Cardinalidad vs relación

Aunque están estrechamente relacionadas, no son lo mismo:

- **Relación**: indica que existe una asociación entre entidades.
- **Cardinalidad**: indica la cantidad de ocurrencias permitidas en esa asociación.

Ejemplo:
- Relación: Estudiante — se inscribe en — Curso
- Cardinalidad: Muchos estudiantes pueden inscribirse en muchos cursos (N:M)

---

## Tipos básicos de cardinalidad

### Uno a uno (1:1)

Cada ocurrencia de una entidad se asocia con **una y solo una** ocurrencia de la otra.

Ejemplo:
- Persona — tiene — Pasaporte

Reglas:
- Una persona tiene un solo pasaporte.
- Un pasaporte pertenece a una sola persona.

---

### Uno a muchos (1:N)

Una ocurrencia de una entidad puede asociarse con **muchas** ocurrencias de la otra, pero no al contrario.

Ejemplo:
- Departamento — tiene — Empleados

Reglas:
- Un departamento puede tener muchos empleados.
- Un empleado pertenece a un solo departamento.

---

### Muchos a muchos (N:M)

Muchas ocurrencias de una entidad pueden asociarse con muchas ocurrencias de la otra.

Ejemplo:
- Estudiante — se inscribe en — Curso

Reglas:
- Un estudiante puede inscribirse en varios cursos.
- Un curso puede tener varios estudiantes.

Este tipo de relación debe resolverse mediante una entidad asociativa.

---

## Cardinalidad mínima y máxima

La cardinalidad puede expresarse mediante dos valores:

- **Cardinalidad mínima**: número mínimo de ocurrencias requeridas.
- **Cardinalidad máxima**: número máximo de ocurrencias permitidas.

Ejemplo:
- Un empleado pertenece a **exactamente un** departamento:
  - mínima = 1
  - máxima = 1

---

## Opcionalidad de la relación

La cardinalidad mínima define si la relación es:

### Obligatoria
La entidad debe participar en la relación.

Ejemplo:
- Todo empleado debe pertenecer a un departamento.

### Opcional
La entidad puede existir sin participar en la relación.

Ejemplo:
- Un cliente puede no haber realizado pedidos.

---

## Representación común de la cardinalidad

En diagramas MER, la cardinalidad se representa usualmente como:

- 1 : 1
- 1 : N
- N : M

Algunos modelos usan notaciones más detalladas, como:
- (0,1)
- (1,N)
- (0,N)

Estas indican mínimo y máximo.

---

## Ejemplo completo: cliente y pedido

Relación:
- Cliente — realiza — Pedido

Cardinalidad:
- Un cliente puede realizar cero o muchos pedidos (0,N).
- Un pedido pertenece a un solo cliente (1,1).

---

## Error común: confundir cardinalidad con cantidad de registros

La cardinalidad **no depende de cuántos datos haya en la tabla**, sino de la regla del negocio.

Ejemplo incorrecto:
- “Solo hay un empleado, entonces la relación es 1:1”.

La cardinalidad se define por el **modelo conceptual**, no por los datos actuales.

---

## Cardinalidad y normalización

Una cardinalidad mal definida puede:
- generar redundancia,
- inducir dependencias incorrectas,
- provocar violaciones de 2FN y 3FN.

Por eso, la cardinalidad debe definirse **antes** de pasar al modelo relacional.

---

## Reglas prácticas para definir cardinalidad

Para cada relación, pregúntate:
- ¿Cuántas veces puede ocurrir esta relación?
- ¿Puede existir una entidad sin la otra?
- ¿Existe un límite lógico máximo?

Responder estas preguntas permite definir correctamente la cardinalidad.

---

## Importancia de la cardinalidad

Definir correctamente la cardinalidad:
- mejora la calidad del diseño,
- evita errores en la implementación,
- facilita la creación de claves foráneas,
- asegura que el modelo represente fielmente el negocio.

La cardinalidad es una de las decisiones más importantes del MER.

---