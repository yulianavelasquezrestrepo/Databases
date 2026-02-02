# Primera Forma Normal (1FN)

## Objetivo del tema
Comprender qué establece la Primera Forma Normal (1FN), cómo identificar estructuras que no la cumplen y cómo transformar una tabla para que cumpla con esta forma normal.

---

## ¿Qué es la Primera Forma Normal?

Una tabla cumple con la **Primera Forma Normal (1FN)** cuando:

- todos los atributos contienen **valores atómicos**,
- no existen grupos repetidos,
- cada intersección fila–columna almacena un único valor.

La 1FN es el primer paso del proceso de normalización y es **obligatoria** para avanzar a formas normales superiores.

---

## Valores atómicos

Un valor es **atómico** cuando:
- representa una sola unidad de información,
- no puede dividirse en partes más pequeñas con significado propio.

Ejemplos:
- Atómico: `3001234567`
- No atómico: `3001234567, 3109876543`

---

## Ejemplo 1: atributo multivaluado (NO cumple 1FN)

| student_id | name       | phones                    |
|------------|------------|---------------------------|
| 101        | Ana Pérez  | 3001234567, 3109876543    |

**Problemas:**
- El atributo `phones` contiene múltiples valores.
- No se pueden consultar teléfonos individualmente.
- Viola el principio de atomicidad.

### Corrección (SÍ cumple 1FN)

| student_id | name       | phone        |
|------------|------------|--------------|
| 101        | Ana Pérez  | 3001234567   |
| 101        | Ana Pérez  | 3109876543   |

Cada fila almacena un solo valor por atributo.

---

## Ejemplo 2: columnas repetidas (NO cumple 1FN)

| student_id | name       | phone1      | phone2      |
|------------|------------|-------------|-------------|
| 102        | Luis Gómez | 3001111111  | 3102222222 |

**Problemas:**
- Las columnas `phone1` y `phone2` representan el mismo tipo de información.
- El número de teléfonos no es flexible.
- El diseño no escala.

### Corrección (SÍ cumple 1FN)

| student_id | name       | phone        |
|------------|------------|--------------|
| 102        | Luis Gómez | 3001111111   |
| 102        | Luis Gómez | 3102222222   |

---

## Ejemplo 3: atributo compuesto (NO cumple 1FN)

| employee_id | full_name        |
|-------------|------------------|
| 1           | Carlos Ruiz     |

**Problema:**
- `full_name` contiene más de un dato (nombre y apellido).
- No se pueden consultar o ordenar por apellido.

### Corrección (SÍ cumple 1FN)

| employee_id | first_name | last_name |
|-------------|------------|-----------|
| 1           | Carlos     | Ruiz      |

---

## Ejemplo 4: múltiples conceptos en un atributo (NO cumple 1FN)

| order_id | product_info           |
|----------|------------------------|
| 5001     | Mouse - $50            |

**Problema:**
- `product_info` mezcla nombre y precio.
- No se puede calcular el total de ventas correctamente.

### Corrección (SÍ cumple 1FN)

| order_id | product_name | product_price |
|----------|--------------|---------------|
| 5001     | Mouse        | 50            |

---

## Ejemplo 5: lista de valores en texto (NO cumple 1FN)

| course_id | course_name   | prerequisites        |
|-----------|---------------|----------------------|
| DB201     | Databases II  | DB101, PR102         |

**Problema:**
- `prerequisites` almacena múltiples valores.
- Dificulta consultas y validaciones.

### Corrección (SÍ cumple 1FN)

| course_id | course_name   | prerequisite |
|-----------|---------------|--------------|
| DB201     | Databases II  | DB101       |
| DB201     | Databases II  | PR102       |

---

## Regla clave de la Primera Forma Normal

> Una tabla está en Primera Forma Normal si cada atributo contiene valores atómicos y no existen grupos repetidos ni atributos multivaluados.

---

## Errores comunes relacionados con la 1FN

- Usar listas separadas por comas.
- Crear columnas numeradas (`item1`, `item2`, `item3`).
- Combinar información diferente en un solo atributo.
- Pensar que la 1FN depende de la clave primaria (no es así).

---

## Importancia de la 1FN

Cumplir la Primera Forma Normal:
- mejora la claridad del diseño,
- facilita las consultas,
- reduce errores tempranos,
- es la base para aplicar la 2FN y la 3FN.

Sin 1FN, no es posible una normalización correcta.

---