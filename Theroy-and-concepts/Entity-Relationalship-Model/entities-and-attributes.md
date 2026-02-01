# Entidades y atributos

## Objetivo del tema
Comprender qué son las entidades y los atributos dentro del Modelo Entidad–Relación, así como su importancia en el diseño conceptual de bases de datos.

---

## ¿Qué es una entidad?

Una **entidad** es un objeto, concepto o elemento del mundo real sobre el cual se desea almacenar información en una base de datos.

Las entidades representan aquello que es relevante para el sistema que se está diseñando y que puede ser identificado de manera independiente.

Ejemplos de entidades:
- Estudiante
- Curso
- Producto
- Cliente
- Empleado

---

## Características de una entidad

Una entidad se caracteriza por:
- tener existencia propia dentro del contexto del sistema,
- poseer atributos que la describen,
- poder diferenciarse de otras entidades similares.

Cada entidad representa una clase de objetos, no un objeto individual.

---

## Ejemplo de entidad

En un sistema académico, **Estudiante** es una entidad, ya que:
- representa a una persona real,
- se necesita almacenar información sobre ella,
- puede distinguirse de otros estudiantes.

---

## ¿Qué es un atributo?

Un **atributo** es una característica o propiedad que describe a una entidad.

Los atributos permiten almacenar información específica sobre cada entidad.

Ejemplos de atributos:
- nombre
- identificación
- correo electrónico
- fecha de nacimiento

---

## Relación entre entidad y atributo

Una entidad sin atributos no aporta información útil.

Por ejemplo:
- Entidad: Estudiante  
- Atributos: código, nombre, correo, programa

Los atributos permiten describir completamente a cada entidad.

---

## Tipos de atributos

### Atributos simples
Son aquellos que no pueden dividirse en partes más pequeñas.

Ejemplo:
- edad
- salario

---

### Atributos compuestos
Son aquellos que pueden descomponerse en subcomponentes.

Ejemplo:
- nombre completo (nombre, apellido)
- dirección (calle, ciudad, país)

---

### Atributos multivaluados
Son aquellos que pueden tener más de un valor para una misma entidad.

Ejemplo:
- números de teléfono
- correos electrónicos

---

### Atributos derivados
Son atributos cuyo valor se obtiene a partir de otros atributos.

Ejemplo:
- edad (derivada de la fecha de nacimiento)
- total de una factura

---

## Identificación de entidades y atributos

Para identificar entidades y atributos es importante:
- analizar el problema o sistema,
- identificar sustantivos relevantes (posibles entidades),
- identificar características asociadas (atributos),
- evitar confundir atributos con entidades.

---

## Errores comunes al definir entidades y atributos

Algunos errores frecuentes son:
- definir atributos como entidades sin justificación,
- definir entidades que no tienen atributos relevantes,
- incluir información redundante como atributos,
- confundir relaciones con atributos.

---

## Representación en el Modelo Entidad–Relación

En un diagrama MER:
- las **entidades** se representan mediante rectángulos,
- los **atributos** se representan mediante óvalos,
- los atributos se conectan a su entidad correspondiente.

Esta representación gráfica facilita la comprensión del diseño.

---

## Importancia de una correcta definición

Una correcta definición de entidades y atributos:
- mejora la claridad del modelo,
- reduce errores de diseño,
- facilita la normalización,
- simplifica la implementación en el modelo relacional.

---

## Preparación para los siguientes temas

Una vez definidas las entidades y atributos, el siguiente paso es:
- identificar las relaciones entre las entidades,
- definir la cardinalidad de dichas relaciones.

Estos conceptos se desarrollarán en los siguientes temas.

---