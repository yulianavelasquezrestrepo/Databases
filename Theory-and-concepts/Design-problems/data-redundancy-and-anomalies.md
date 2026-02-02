# Redundancia de datos y anomalías

## Objetivo del tema
Comprender qué es la redundancia de datos, por qué ocurre y cuáles son las anomalías que se generan cuando los datos no están correctamente organizados.

---

## ¿Qué es la redundancia de datos?

La **redundancia de datos** ocurre cuando la misma información se almacena repetidamente en diferentes filas o registros dentro de una estructura de datos.

Aunque a simple vista puede parecer inofensiva, la redundancia incrementa el riesgo de:
- inconsistencias,
- errores humanos,
- pérdida de información,
- dificultades en el mantenimiento de los datos.

---

## Ejemplo de redundancia

Supongamos la siguiente tabla que registra inscripciones a cursos:

| student_id | student_name | program              | course_code | course_name        |
|------------|--------------|----------------------|-------------|--------------------|
| 101        | Ana Pérez    | Systems Technology   | DB101       | Databases I        |
| 101        | Ana Pérez    | Systems Technology   | PR102       | Programming I      |
| 102        | Luis Gómez   | Systems Technology   | DB101       | Databases I        |

En esta tabla:
- la información del estudiante se repite,
- la información del programa se repite,
- la información del curso se repite.

Esto es un claro ejemplo de redundancia.

---

## Problemas causados por la redundancia

La redundancia da origen a **anomalías**, que son situaciones problemáticas al manipular los datos.

Existen tres tipos principales de anomalías.

---

## Anomalía de inserción

La **anomalía de inserción** ocurre cuando no es posible registrar un dato sin que otro dato esté presente.

### Ejemplo
Si se desea registrar un nuevo curso que aún no tiene estudiantes inscritos, no se puede hacer porque la tabla requiere datos del estudiante.

Esto limita el registro de información independiente.

---

## Anomalía de actualización

La **anomalía de actualización** ocurre cuando un mismo dato debe ser modificado en múltiples filas.

### Ejemplo
Si el nombre del programa cambia, es necesario actualizarlo en todas las filas donde aparece.

Si se actualiza solo en algunas filas, la información queda inconsistente.

---

## Anomalía de eliminación

La **anomalía de eliminación** ocurre cuando al eliminar un dato se pierde información adicional que aún es relevante.

### Ejemplo
Si se elimina la única inscripción de un curso, también se pierde la información del curso.

Esto provoca pérdida de información que no debería desaparecer.

---

## Relación entre redundancia y diseño

La redundancia no es un problema del software, sino del **diseño de los datos**.

Cuando los datos no están correctamente organizados:
- se mezclan diferentes conceptos en una misma tabla,
- se repite información innecesariamente,
- se dificulta el mantenimiento del sistema.

---

## Importancia de identificar redundancia

Detectar redundancia permite:
- mejorar la calidad de los datos,
- reducir errores,
- facilitar cambios futuros,
- preparar el camino para un diseño adecuado.

Este análisis es el primer paso antes de aplicar técnicas de normalización.

---

## Conexión con la normalización

La **normalización** es el proceso que permite:
- dividir una tabla en estructuras más simples,
- eliminar redundancia,
- reducir anomalías.

---
