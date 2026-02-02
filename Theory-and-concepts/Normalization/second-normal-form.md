# Segunda Forma Normal (2FN)

## Objetivo del tema
Comprender qué establece la Segunda Forma Normal (2FN), cómo identificar dependencias parciales y cómo corregir estructuras que no cumplen esta forma normal.

---

## ¿Qué es la Segunda Forma Normal?

Una tabla cumple con la **Segunda Forma Normal (2FN)** cuando:

- cumple con la Primera Forma Normal (1FN),
- **todos los atributos no clave dependen completamente de la clave primaria**.

La 2FN busca eliminar **dependencias parciales**.

---

## Dependencia funcional parcial

Existe una **dependencia parcial** cuando:

- la clave primaria es **compuesta**,
- un atributo no clave depende solo de **una parte** de la clave primaria.

Si la clave primaria es simple, **no puede existir dependencia parcial**.

---

## Caso clave: cuándo aplica la 2FN

> La 2FN **solo se evalúa cuando la clave primaria es compuesta**.

Si una tabla tiene clave primaria simple:
- cumple automáticamente 2FN,
- aunque pueda violar 3FN.

---

## Ejemplo 1: inscripción académica (NO cumple 2FN)

Clave primaria compuesta: `(student_id, course_id)`

| student_id | course_id | student_name | course_name |
|------------|-----------|--------------|-------------|
| 101        | DB101     | Ana Pérez    | Databases I |
| 101        | PR102     | Ana Pérez    | Programming |

**Problemas:**
- `student_name` depende solo de `student_id`.
- `course_name` depende solo de `course_id`.

Esto viola la 2FN.

---

### Corrección

**Students**

| student_id | student_name |
|------------|--------------|
| 101        | Ana Pérez    |

**Courses**

| course_id | course_name  |
|-----------|--------------|
| DB101     | Databases I  |

**Enrollments**

| student_id | course_id |
|------------|-----------|
| 101        | DB101     |
| 101        | PR102     |

---

## Ejemplo 2: pedidos y clientes (NO cumple 2FN)

Clave primaria compuesta: `(order_id, product_id)`

| order_id | product_id | order_date | product_name |
|----------|------------|------------|--------------|
| 1        | P01        | 2024-03-10 | Mouse        |
| 1        | P02        | 2024-03-10 | Keyboard     |

**Problemas:**
- `order_date` depende solo de `order_id`.
- `product_name` depende solo de `product_id`.

---

### Corrección

**Orders**

| order_id | order_date |
|----------|------------|
| 1        | 2024-03-10 |

**Products**

| product_id | product_name |
|------------|--------------|
| P01        | Mouse        |

**Order_Details**

| order_id | product_id |
|----------|------------|
| 1        | P01        |
| 1        | P02        |

---

## Ejemplo 3: caso límite (SÍ cumple 2FN)

Clave primaria compuesta: `(student_id, course_id)`

| student_id | course_id | final_grade |
|------------|-----------|-------------|
| 101        | DB101     | 4.5         |
| 101        | PR102     | 4.0         |

**Análisis:**
- `final_grade` depende del estudiante **y** del curso.
- No depende de una sola parte de la clave.

Este diseño **sí cumple 2FN**.

---

## Ejemplo 4: clave primaria simple (SIEMPRE cumple 2FN)

Clave primaria: `employee_id`

| employee_id | employee_name | department_name |
|-------------|---------------|-----------------|
| 1           | Carlos Ruiz   | Systems         |

**Análisis:**
- La clave es simple.
- No puede existir dependencia parcial.

Esta tabla **cumple 2FN**, aunque **no cumple 3FN**.

---

## Error común: confundir 2FN con 3FN

Muchos errores ocurren porque:
- se detecta una dependencia,
- pero no se analiza si es parcial o transitiva.

Regla práctica:
- **¿La clave es compuesta?**  
  - No → no hay problema de 2FN  
  - Sí → revisar dependencias parciales

---

## Regla clave de la Segunda Forma Normal

> En una tabla con clave primaria compuesta, ningún atributo no clave debe depender solo de una parte de la clave.

---

## Importancia de la 2FN

Cumplir la Segunda Forma Normal:
- reduce redundancia,
- mejora la consistencia,
- clarifica responsabilidades de cada tabla,
- prepara el diseño para la 3FN.

La 2FN es un paso intermedio crítico en la normalización.

---