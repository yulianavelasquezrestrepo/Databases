# Relaciones entre Entidades

## Objetivo del tema
Comprender qué son las relaciones entre entidades dentro del Modelo Entidad-Relación (MER), cómo se identifican y cómo se representan correctamente en un diseño conceptual de bases de datos.

---

## ¿Qué es una relación?

En el Modelo Entidad-Relación, una **relación** representa la forma en que dos o más entidades están vinculadas entre sí dentro de un contexto del mundo real.

Una relación responde a preguntas como:
- ¿Qué entidades interactúan?
- ¿Cómo se asocian?
- ¿Qué significado tiene esa asociación?

Ejemplo conceptual:
- Un **estudiante** se **inscribe** en un **curso**.
- Un **cliente** realiza un **pedido**.
- Un **empleado** pertenece a un **departamento**.

---

## Componentes de una relación

Toda relación se define por:

1. **Entidades participantes**  
   Las entidades que intervienen en la relación.

2. **Nombre de la relación**  
   Generalmente es un verbo o una frase verbal.

3. **Cardinalidad**  
   Indica cuántas ocurrencias de una entidad pueden relacionarse con la otra.

4. **Opcionalidad (participación)**  
   Indica si la relación es obligatoria u opcional para una entidad.

---

## Tipos de relaciones según el número de entidades

### Relación binaria
Involucra dos entidades.  
Es el tipo de relación más común.

Ejemplo:
- Estudiante — se inscribe en — Curso

### Relación ternaria
Involucra tres entidades.

Ejemplo:
- Proveedor — suministra — Producto — a — Proyecto

En cursos iniciales, la mayoría de diseños trabajan con relaciones binarias.

---

## Relaciones uno a uno (1:1)

Una ocurrencia de una entidad se relaciona con **una y solo una** ocurrencia de la otra entidad.

### Ejemplo conceptual
- Persona — tiene — Pasaporte

Regla:
- Una persona tiene un solo pasaporte.
- Un pasaporte pertenece a una sola persona.

Este tipo de relación es poco frecuente y suele evaluarse si ambas entidades deben realmente existir separadas.

---

## Relaciones uno a muchos (1:N)

Una ocurrencia de una entidad se relaciona con **muchas** ocurrencias de la otra, pero no al contrario.

### Ejemplo conceptual
- Departamento — tiene — Empleados

Regla:
- Un departamento puede tener muchos empleados.
- Un empleado pertenece a un solo departamento.

Este es el tipo de relación **más común** en bases de datos relacionales.

---

## Relaciones muchos a muchos (N:M)

Muchas ocurrencias de una entidad se relacionan con muchas ocurrencias de la otra.

### Ejemplo conceptual
- Estudiante — se inscribe en — Curso

Regla:
- Un estudiante puede inscribirse en varios cursos.
- Un curso puede tener varios estudiantes.

En bases de datos relacionales, este tipo de relación **no se implementa directamente**, sino que se transforma en una entidad intermedia.

---

## Entidad asociativa

Una **entidad asociativa** surge al resolver una relación muchos a muchos (N:M).

### Ejemplo

Relación original:
- Estudiante — Curso

Entidad asociativa:
- Inscripción

Atributos posibles:
- student_id
- course_id
- enrollment_date
- final_grade

La clave primaria suele ser **compuesta** por las claves de las entidades relacionadas.

---

## Relaciones con atributos

Una relación puede tener atributos propios cuando estos describen la asociación y no a las entidades por separado.

Ejemplo:
- Inscripción:
  - fecha_inscripción
  - nota_final

Estos atributos **no pertenecen ni al estudiante ni al curso individualmente**, sino a la relación entre ambos.

---

## Error común: convertir relaciones en atributos

Un error frecuente es:
- convertir una relación en un atributo,
- perdiendo información o generando redundancia.

Ejemplo incorrecto:
- Agregar `course_name` directamente en Estudiante.

Esto rompe el modelo conceptual y genera problemas de normalización.

---

## Participación total y parcial

### Participación total
Toda ocurrencia de la entidad debe participar en la relación.

Ejemplo:
- Todo empleado debe pertenecer a un departamento.

### Participación parcial
No todas las ocurrencias participan en la relación.

Ejemplo:
- Un cliente puede existir sin haber realizado pedidos.

---

## Reglas prácticas para identificar relaciones

Al analizar un problema, pregúntate:
- ¿Una entidad depende conceptualmente de otra?
- ¿Puede existir de forma independiente?
- ¿La relación tiene atributos propios?
- ¿La relación es obligatoria u opcional?

---

## Importancia de las relaciones en el MER

Las relaciones:
- dan significado al modelo,
- conectan las entidades,
- permiten representar reglas del negocio,
- sirven de base para el diseño relacional posterior.

Un MER sin relaciones bien definidas es incompleto y poco útil.

---