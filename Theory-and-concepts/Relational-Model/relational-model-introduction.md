# Introducción al Modelo Relacional

## Objetivo del tema
Comprender qué es el modelo relacional, por qué se utiliza en los sistemas de bases de datos actuales y cómo se relaciona con el Modelo Entidad-Relación (MER) como paso previo a la implementación.

---

## ¿Qué es el modelo relacional?

El **modelo relacional** es un modelo lógico de bases de datos que representa la información mediante **relaciones**, las cuales se implementan como **tablas**.

Cada tabla:
- representa una entidad o una relación del mundo real,
- está compuesta por filas y columnas,
- tiene reglas estrictas sobre cómo se organizan y relacionan los datos.

Este modelo fue propuesto por **Edgar F. Codd** y es la base de los sistemas de bases de datos relacionales modernos.

---

## Relación entre MER y modelo relacional

El Modelo Entidad-Relación es un **modelo conceptual**:
- describe el problema,
- es independiente de la tecnología,
- se usa para analizar el dominio.

El modelo relacional es un **modelo lógico**:
- prepara el diseño para la implementación,
- transforma entidades y relaciones en tablas,
- define claves y restricciones.

El MER **no se implementa directamente**; primero debe transformarse al modelo relacional.

---

## Conceptos fundamentales del modelo relacional

El modelo relacional se basa en los siguientes conceptos:

- **Relación**: una tabla.
- **Atributo**: una columna de la tabla.
- **Tupla**: una fila de la tabla.
- **Dominio**: conjunto de valores válidos para un atributo.

Estos conceptos permiten organizar la información de forma estructurada y consistente.

---

## Características del modelo relacional

El modelo relacional se caracteriza por:

- estructura tabular clara,
- uso de claves para identificar registros,
- soporte para integridad referencial,
- independencia entre estructura y datos,
- facilidad para realizar consultas complejas.

Estas características lo hacen ideal para sistemas transaccionales.

---

## Claves en el modelo relacional

Las **claves** son fundamentales para el funcionamiento del modelo relacional.

Tipos principales:
- **Clave primaria**: identifica de forma única cada fila.
- **Clave foránea**: establece relaciones entre tablas.
- **Clave candidata**: atributo o conjunto de atributos que pueden identificar de forma única una fila.

Las claves permiten mantener la coherencia y las relaciones entre tablas.

---

## Restricciones de integridad

El modelo relacional impone reglas que garantizan la calidad de los datos:

- **Integridad de entidad**: cada tabla debe tener una clave primaria válida.
- **Integridad referencial**: las claves foráneas deben corresponder a valores existentes.
- **Integridad de dominio**: los valores deben pertenecer al dominio definido.

Estas restricciones previenen inconsistencias.

---

## Ejemplo conceptual

A partir de un MER con las entidades:
- Estudiante
- Curso

Y la relación:
- Inscripción

El modelo relacional resultante será:
- Estudiante (student_id, name)
- Curso (course_id, name)
- Inscripción (student_id, course_id)

Cada entidad se transforma en una tabla, y la relación N:M se resuelve mediante una tabla intermedia.

---

## Diferencias entre modelo conceptual y modelo relacional

| Modelo conceptual (MER) | Modelo relacional |
|-------------------------|-------------------|
| Orientado al análisis   | Orientado a implementación |
| Usa diagramas           | Usa tablas |
| No define tipos de datos| Define dominios |
| No depende del DBMS     | Compatible con DBMS |

---

## Importancia del modelo relacional

Aplicar correctamente el modelo relacional:
- facilita la creación de bases de datos,
- asegura integridad de los datos,
- permite consultas eficientes,
- prepara el sistema para crecer.

El éxito de una base de datos depende en gran medida de un buen modelo relacional.

---