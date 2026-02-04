# Transformación de Entidades a Tablas

## Objetivo del tema
Comprender cómo transformar correctamente las entidades del Modelo Entidad-Relación (MER) en tablas del modelo relacional, identificando atributos, claves primarias y reglas básicas de diseño.

---

## Relación entre entidad y tabla

En el proceso de diseño de bases de datos:
- cada **entidad** del MER se transforma en una **tabla**,
- los **atributos** de la entidad se convierten en **columnas**,
- las **ocurrencias** de la entidad se representan como **filas**.

Esta transformación es directa, pero debe hacerse respetando ciertas reglas.

---

## Regla básica de transformación

Para cada entidad del MER:

- se crea una tabla con el mismo significado,
- se definen columnas para cada atributo,
- se elige una clave primaria adecuada.

El nombre de la tabla debe representar claramente la entidad.

---

## Identificación de la clave primaria

Cada entidad debe tener una clave primaria que:
- identifique de forma única cada registro,
- no tenga valores nulos,
- sea estable en el tiempo.

Ejemplo:
Entidad MER: Estudiante  
Clave primaria: `student_id`

Tabla relacional:
- Estudiante (student_id, student_name, birth_date)

---

## Transformación de atributos simples

Los atributos simples:
- se convierten directamente en columnas,
- deben almacenar valores atómicos,
- deben tener un dominio definido.

Ejemplo:
- nombre
- fecha_nacimiento
- correo_electrónico

---

## Transformación de atributos compuestos

Los atributos compuestos:
- deben descomponerse en atributos simples,
- no se implementan como un solo campo.

Ejemplo MER:
- Dirección (calle, ciudad, país)

Transformación:
- street
- city
- country

---

## Transformación de atributos multivaluados

Los atributos multivaluados:
- no se almacenan directamente en una tabla,
- requieren una tabla adicional.

Ejemplo MER:
- Cliente tiene múltiples teléfonos.

Transformación:
- Tabla Cliente
- Tabla TelefonoCliente (customer_id, phone_number)

---

## Transformación de atributos derivados

Los atributos derivados:
- no se almacenan físicamente,
- se calculan a partir de otros datos.

Ejemplo:
- edad derivada de fecha de nacimiento.

En el modelo relacional, estos atributos suelen omitirse.

---

## Entidades fuertes

Las **entidades fuertes**:
- tienen existencia independiente,
- poseen su propia clave primaria.

Ejemplos:
- Cliente
- Producto
- Empleado

Cada entidad fuerte se transforma en una tabla independiente.

---

## Entidades débiles

Las **entidades débiles**:
- dependen de una entidad fuerte para existir,
- no tienen clave primaria propia completa.

Transformación:
- la clave primaria incluye la clave de la entidad fuerte,
- se agrega un discriminador.

Ejemplo:
Entidad fuerte: Pedido  
Entidad débil: DetallePedido  

Clave primaria de DetallePedido:
- (order_id, line_number)

---

## Ejemplo completo

Entidad MER: Curso

Atributos:
- course_id
- course_name
- credits

Tabla relacional:
- Curso (course_id, course_name, credits)

Esta transformación es directa y cumple con el modelo relacional.

---

## Error común: incluir atributos de otras entidades

Ejemplo incorrecto:
- incluir `department_name` en Empleado.

Problema:
- ese atributo pertenece a Departamento.

Solución:
- crear una relación y usar una clave foránea.

---

## Reglas prácticas de transformación

Al transformar entidades:
- cada entidad se convierte en una tabla,
- cada atributo en una columna,
- cada tabla tiene una clave primaria,
- los atributos multivaluados generan tablas nuevas,
- los atributos derivados no se almacenan.

---

## Importancia de una correcta transformación

Transformar correctamente entidades a tablas:
- asegura un modelo limpio,
- evita redundancia,
- facilita la implementación en SQL,
- prepara el sistema para crecer.

Este paso es fundamental para una base de datos bien diseñada.

---