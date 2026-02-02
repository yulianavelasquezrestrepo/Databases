# Tercera Forma Normal (3FN)

## Objetivo del tema
Comprender qué establece la Tercera Forma Normal (3FN), identificar dependencias transitivas y aplicar correctamente la descomposición de tablas para eliminarlas.

---

## ¿Qué es la Tercera Forma Normal?

Una tabla cumple con la **Tercera Forma Normal (3FN)** cuando:

- cumple con la Segunda Forma Normal (2FN),
- **no existen dependencias transitivas** entre atributos no clave.

---

## Dependencia funcional transitiva

Existe una **dependencia transitiva** cuando:

- un atributo no clave depende de otro atributo no clave,
- y este segundo atributo depende de la clave primaria.

Forma general:
Clave primaria → Atributo X → Atributo Y

Esto **viola la 3FN**.

---

## Regla fundamental de la 3FN

> Ningún atributo no clave debe depender de otro atributo no clave.

Todos los atributos no clave deben depender **únicamente** de la clave primaria.

---

## Ejemplo 1: empleados y departamentos (NO cumple 3FN)

Clave primaria: `employee_id`

| employee_id | employee_name | department_id | department_name |
|-------------|---------------|---------------|-----------------|
| 1           | Laura Gómez   | D01           | Systems         |
| 2           | Juan Pérez    | D02           | Finance         |

**Análisis de dependencias:**
- `employee_id → department_id`
- `department_id → department_name`

Existe una dependencia transitiva:
employee_id → department_id → department_name

Esto **viola la 3FN**.

---

### Corrección

**Employees**

| employee_id | employee_name | department_id |
|-------------|---------------|---------------|
| 1           | Laura Gómez   | D01           |

**Departments**

| department_id | department_name |
|---------------|-----------------|
| D01           | Systems         |

---

## Ejemplo 2: clientes y ciudades (NO cumple 3FN)

Clave primaria: `customer_id`

| customer_id | customer_name | city_id | city_name |
|-------------|---------------|---------|-----------|
| 10          | Ana López     | C01     | Bogotá    |
| 11          | Luis Torres   | C02     | Medellín  |

**Problema:**
- `city_name` no depende directamente del cliente,
- depende de `city_id`.

Esto es una dependencia transitiva.

---

### Corrección

**Customers**

| customer_id | customer_name | city_id |
|-------------|---------------|---------|
| 10          | Ana López     | C01     |

**Cities**

| city_id | city_name |
|---------|-----------|
| C01     | Bogotá    |

---

## Ejemplo 3: caso límite común (NO cumple 3FN aunque parece correcto)

Clave primaria: `order_id`

| order_id | order_date | customer_id | customer_email |
|----------|------------|-------------|----------------|
| 1001     | 2024-04-10 | 10          | ana@email.com  |

**Error típico del estudiante:**
- piensa que `customer_email` pertenece al pedido.

**Análisis real:**
- `order_id → customer_id`
- `customer_id → customer_email`

Dependencia transitiva presente.

---

### Corrección

**Orders**

| order_id | order_date | customer_id |
|----------|------------|-------------|
| 1001     | 2024-04-10 | 10          |

**Customers**

| customer_id | customer_email |
|-------------|----------------|
| 10          | ana@email.com  |

---

## Ejemplo 4: tabla que SÍ cumple 3FN

Clave primaria: `student_id`

| student_id | student_name | birth_date |
|------------|--------------|------------|
| 1          | Carlos Ruiz  | 2002-06-15 |

**Análisis:**
- Todos los atributos dependen directamente de `student_id`.
- No hay atributos no clave intermedios.

Cumple 3FN.

---

## Ejemplo 5: clave compuesta que SÍ cumple 3FN

Clave primaria compuesta: `(student_id, course_id)`

| student_id | course_id | final_grade |
|------------|-----------|-------------|
| 1          | DB101     | 4.5         |

**Análisis:**
- `final_grade` depende de la combinación estudiante + curso.
- No depende de otro atributo no clave.

Cumple 3FN.

---

## Ejemplo 6: confusión frecuente (NO es problema de 3FN)

Clave primaria: `product_id`

| product_id | product_name | price |
|------------|--------------|-------|
| P01        | Mouse        | 25.00 |

**Análisis:**
- No hay dependencias transitivas.
- Aunque el precio pueda cambiar, **no es un problema de normalización**.

Cumple 3FN.

---

## Diferencia clave entre 2FN y 3FN

| Forma Normal | Problema principal |
|--------------|-------------------|
| 2FN          | Dependencia parcial |
| 3FN          | Dependencia transitiva |

---

## Regla práctica para evaluar 3FN

Pregúntate:
- ¿Algún atributo no clave depende de otro atributo no clave?
  - Sí → NO cumple 3FN
  - No → Cumple 3FN

---

## Importancia de la Tercera Forma Normal

Aplicar la 3FN:
- reduce redundancia semántica,
- mejora la mantenibilidad,
- facilita cambios futuros,
- produce modelos más claros y escalables.

La 3FN es el nivel esperado en la mayoría de sistemas transaccionales.

---