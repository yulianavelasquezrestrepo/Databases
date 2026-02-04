# Tablas, Filas y Columnas

## Objetivo del tema
Comprender los elementos básicos del modelo relacional: tablas, filas y columnas, y su correspondencia con los conceptos del Modelo Entidad-Relación (MER).

---

## La tabla como estructura fundamental

En el modelo relacional, una **tabla** es la estructura principal para almacenar información.

Una tabla:
- representa una entidad o una relación del modelo conceptual,
- organiza la información en forma bidimensional,
- tiene un nombre único dentro de la base de datos.

Cada tabla describe un conjunto de objetos del mismo tipo.

---

## Columnas (atributos)

Las **columnas** representan las características o propiedades de la entidad.

Características de las columnas:
- tienen un nombre,
- tienen un tipo de dato asociado,
- representan un único atributo,
- deben contener valores atómicos.

Ejemplo conceptual:
Entidad: Estudiante  
Columnas:
- student_id
- student_name
- birth_date

Cada columna corresponde a un atributo del MER.

---

## Filas (tuplas)

Las **filas** representan ocurrencias concretas de la entidad.

Características de las filas:
- cada fila es un registro único,
- contiene valores para todas las columnas,
- representa una instancia real del objeto modelado.

Ejemplo:
Una fila en la tabla Estudiante representa a un estudiante específico.

---

## Relación entre tabla, fila y columna

| Concepto | Representa |
|--------|------------|
| Tabla  | Conjunto de objetos |
| Fila   | Un objeto específico |
| Columna | Característica del objeto |

Este enfoque permite almacenar múltiples instancias de una entidad de forma estructurada.

---

## Correspondencia con el MER

| MER | Modelo Relacional |
|-----|------------------|
| Entidad | Tabla |
| Atributo | Columna |
| Relación | Clave foránea / Tabla intermedia |
| Ocurrencia | Fila |

Esta correspondencia es fundamental para la transformación de modelos.

---

## Ejemplo práctico

Entidad MER: Curso

Atributos:
- course_id
- course_name
- credits

Tabla relacional: Curso

| course_id | course_name | credits |
|----------|-------------|---------|
| DB101    | Databases I | 4       |
| PR102    | Programming | 3       |

Cada fila representa un curso distinto.

---

## Valores atómicos y la Primera Forma Normal

Las columnas deben contener valores **atómicos**, es decir:
- un solo valor por celda,
- sin listas ni valores compuestos.

Ejemplo incorrecto:
- `phone_numbers`: "12345, 67890"

Ejemplo correcto:
- crear una tabla separada para teléfonos.

Este principio asegura el cumplimiento de la 1FN.

---

## Orden y unicidad de las filas

En el modelo relacional:
- el orden de las filas no tiene significado,
- cada fila debe poder identificarse de forma única.

Por esta razón, toda tabla debe tener una clave primaria.

---

## Error común: usar la tabla como hoja de cálculo

Muchos errores ocurren cuando:
- se piensa la tabla como una hoja de Excel,
- se mezclan datos de diferentes entidades,
- se agregan columnas repetidas.

Las tablas relacionales:
- no están diseñadas para repetición visual,
- están diseñadas para consistencia y consultas.

---

## Importancia de comprender estas estructuras

Entender correctamente tablas, filas y columnas:
- facilita la creación de modelos relacionales,
- evita errores de normalización,
- prepara al estudiante para escribir SQL correctamente,
- mejora la calidad del diseño de la base de datos.

Estos conceptos son la base de toda base de datos relacional.

---