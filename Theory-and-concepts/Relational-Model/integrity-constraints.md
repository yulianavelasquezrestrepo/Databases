# Restricciones de Integridad

## Objetivo del tema
Comprender qué son las restricciones de integridad en el modelo relacional, por qué son necesarias y cómo garantizan la coherencia y calidad de los datos en una base de datos.

---

## ¿Qué son las restricciones de integridad?

Las **restricciones de integridad** son reglas que se aplican a los datos para asegurar que:
- sean correctos,
- sean consistentes,
- representen fielmente las reglas del negocio.

Estas restricciones deben considerarse desde el diseño y aplicarse durante la implementación.

---

## Importancia de las restricciones de integridad

Sin restricciones de integridad:
- los datos pueden ser inconsistentes,
- pueden existir registros inválidos,
- se pierde confianza en la información,
- las consultas producen resultados incorrectos.

El modelo relacional depende de estas reglas para funcionar correctamente.

---

## Tipos principales de restricciones de integridad

### Integridad de entidad

Establece que:
- toda tabla debe tener una clave primaria,
- la clave primaria no puede ser nula,
- la clave primaria debe ser única.

Ejemplo:
- No pueden existir dos estudiantes con el mismo `student_id`.

Esta restricción garantiza la identidad de cada registro.

---

### Integridad referencial

Establece que:
- toda clave foránea debe corresponder a un valor existente en la tabla referenciada,
- no pueden existir referencias inválidas.

Ejemplo:
- Un pedido no puede existir sin un cliente válido.

Esta restricción mantiene coherencia entre tablas relacionadas.

---

### Integridad de dominio

Establece que:
- los valores de un atributo deben pertenecer a un conjunto válido,
- el tipo de dato y las reglas del dominio deben respetarse.

Ejemplo:
- Una calificación debe estar entre 0 y 5.
- Un correo electrónico debe tener un formato válido.

---

## Restricciones implícitas y explícitas

### Restricciones implícitas
Son reglas asumidas por el diseño.

Ejemplo:
- Una fecha no puede ser negativa.
- Un identificador debe ser numérico.

---

### Restricciones explícitas
Son reglas definidas claramente por el diseñador.

Ejemplo:
- Un estudiante debe tener al menos un nombre.
- Un pedido debe tener una fecha válida.

Estas reglas se formalizan en la implementación.

---

## Ejemplo integrado

Tablas:
- Cliente
- Pedido

Restricciones:
- Cliente tiene clave primaria `customer_id`.
- Pedido tiene clave primaria `order_id`.
- Pedido contiene `customer_id` como clave foránea.
- Todo pedido debe pertenecer a un cliente existente.

Este conjunto de restricciones garantiza la coherencia del modelo.

---

## Error común: confiar solo en la aplicación

Un error frecuente es:
- validar reglas solo en el código de la aplicación,
- no definir restricciones en la base de datos.

Problema:
- se pueden insertar datos inválidos directamente en la base.

Las restricciones deben existir **también** en la base de datos.

---

## Restricciones y reglas del negocio

No todas las reglas del negocio se pueden expresar directamente como restricciones, pero:
- deben analizarse desde el diseño,
- deben documentarse claramente,
- deben influir en el modelo.

El diseñador debe decidir qué reglas se implementan en la base y cuáles en la aplicación.

---

## Importancia para el diseño relacional

Definir correctamente las restricciones:
- mejora la calidad del modelo,
- evita errores de implementación,
- facilita el mantenimiento,
- reduce inconsistencias futuras.

Las restricciones de integridad son esenciales para bases de datos confiables.

---