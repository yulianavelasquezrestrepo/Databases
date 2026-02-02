# Introducción a la normalización

## Objetivo del tema
Comprender qué es la normalización, cuál es su propósito y por qué es un proceso fundamental en el diseño de bases de datos relacionales.

---

## ¿Qué es la normalización?

La **normalización** es un proceso de diseño de bases de datos que consiste en **organizar los datos de manera estructurada**, con el fin de:
- reducir la redundancia,
- evitar inconsistencias,
- y eliminar anomalías en la manipulación de datos.

Este proceso se basa en dividir estructuras de datos grandes y desorganizadas en estructuras más pequeñas y coherentes.

---

## ¿Por qué es necesaria la normalización?

Cuando los datos se almacenan sin un diseño adecuado, se presentan problemas como:
- repetición innecesaria de información,
- dificultad para actualizar datos,
- pérdida de información relevante,
- errores en la consistencia de los datos.

La normalización surge como una solución sistemática para resolver estos problemas desde el diseño.

---

## Normalización y diseño de bases de datos

La normalización no es una tarea técnica aislada, sino una **actividad de diseño**.

Antes de crear tablas en un DBMS, es necesario:
- analizar la información,
- identificar entidades y atributos,
- comprender las relaciones entre los datos.

La normalización permite transformar una estructura inicial en un diseño lógico correcto.

---

## Ejemplo conceptual

Supongamos una tabla que registra pedidos de clientes:

| order_id | customer_name | customer_email | product_name | product_price |
|----------|---------------|----------------|--------------|---------------|
| 1        | Carlos Ruiz   | c.ruiz@mail.com| Mouse        | 50            |
| 2        | Carlos Ruiz   | c.ruiz@mail.com| Keyboard     | 120           |

En esta tabla:
- la información del cliente se repite,
- la información del producto se repite,
- cualquier cambio debe hacerse en múltiples filas.

La normalización permite separar esta información en tablas independientes y relacionadas.

---

## Objetivos principales de la normalización

La normalización busca:

- eliminar redundancia de datos,
- prevenir anomalías de inserción, actualización y eliminación,
- mejorar la integridad de la información,
- facilitar el mantenimiento de la base de datos.

---

## Formas normales

La normalización se aplica a través de una serie de reglas conocidas como **formas normales**.

Las más utilizadas en bases de datos relacionales son:

- **Primera Forma Normal (1FN)**  
- **Segunda Forma Normal (2FN)**  
- **Tercera Forma Normal (3FN)**  

Cada forma normal establece condiciones específicas que una estructura de datos debe cumplir.

Estas formas se aplican de manera progresiva, es decir, una tabla debe cumplir la 1FN antes de avanzar a la 2FN, y así sucesivamente.

---

## Normalización no significa más tablas sin sentido

Un error común es pensar que normalizar implica crear muchas tablas innecesarias.

La normalización busca:
- coherencia lógica,
- claridad en los datos,
- estructuras que representen correctamente la realidad.

Un diseño normalizado bien hecho es más fácil de entender y mantener.

---

## Relación entre normalización y modelo entidad–relación

El proceso de normalización está estrechamente relacionado con el **Modelo Entidad–Relación (MER)**.

- La normalización ayuda a identificar entidades.
- El MER permite representar gráficamente esas entidades y sus relaciones.
- Ambos procesos se complementan en el diseño de bases de datos.

---

## Preparación para las formas normales

Antes de estudiar cada forma normal en detalle, es importante comprender:
- qué problemas se desean resolver,
- por qué no basta con una sola tabla,
- y cómo el diseño impacta directamente la calidad de los datos.

---
