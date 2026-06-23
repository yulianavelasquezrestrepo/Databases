# Actividad Práctica DQL
# Consultas SQL Básicas e INNER JOIN

## Objetivo

Practicar consultas SQL utilizando los modelos relacionales previamente creados.

Los estudiantes deberán realizar consultas utilizando:

- SELECT
- WHERE
- ORDER BY
- INNER JOIN

---

# Caso 1 — Sistema de Biblioteca

## Consultas básicas

### Consulta 1

Mostrar todos los usuarios registrados.

---

### Consulta 2

Mostrar únicamente el nombre y correo de los usuarios.

---

### Consulta 3

Consultar los libros publicados después del año 2020.

---

### Consulta 4

Mostrar los libros ordenados alfabéticamente por título.

---

### Consulta 5

Consultar los préstamos realizados.

Mostrar:

- fecha préstamo
- fecha devolución

---

## INNER JOIN

### Consulta 6

Mostrar los préstamos junto con el nombre del usuario.

Resultado esperado:

| Usuario | Fecha préstamo |
|---|---|

---

### Consulta 7

Mostrar los préstamos junto con el título del libro.

Resultado esperado:

| Libro | Fecha préstamo |
|---|---|

---

### Consulta 8

Mostrar:

- usuario
- libro
- fecha préstamo

---

---

# Caso 2 — Sistema de Clínica Médica

## Consultas básicas

### Consulta 1

Mostrar todos los pacientes.

---

### Consulta 2

Mostrar pacientes que viven en una ciudad específica.

---

### Consulta 3

Mostrar médicos registrados.

---

### Consulta 4

Consultar las citas ordenadas por fecha.

---

### Consulta 5

Mostrar medicamentos disponibles.

---

## INNER JOIN

### Consulta 6

Mostrar las citas con el nombre del paciente.

Resultado:

| Paciente | Fecha | Motivo |
|---|---|---|

---

### Consulta 7

Mostrar las citas con el médico asignado.

Resultado:

| Médico | Fecha |
|---|---|

---

### Consulta 8

Mostrar:

- paciente
- médico
- fecha de cita

---

### Consulta 9

Mostrar pacientes junto con sus medicamentos asignados.

---

---

# Caso 3 — Sistema de Restaurante

## Consultas básicas

### Consulta 1

Mostrar todos los clientes.

---

### Consulta 2

Mostrar platos con precio mayor a un valor definido.

---

### Consulta 3

Mostrar todos los meseros.

---

### Consulta 4

Consultar pedidos realizados.

---

### Consulta 5

Mostrar platos ordenados por precio descendente.

---

## INNER JOIN

### Consulta 6

Mostrar pedidos junto con el cliente que realizó la compra.

Resultado:

| Cliente | Fecha |
|---|---|

---

### Consulta 7

Mostrar los platos pertenecientes a cada categoría.

Resultado:

| Plato | Categoría |
|---|---|

---

### Consulta 8

Mostrar:

- cliente
- pedido
- fecha
- valor total

---

### Consulta 9

Mostrar los pedidos con el mesero encargado.

---

---

# Caso 4 — Sistema de Hotel

## Consultas básicas

### Consulta 1

Mostrar todos los huéspedes.

---

### Consulta 2

Mostrar habitaciones disponibles.

---

### Consulta 3

Mostrar habitaciones ordenadas por precio.

---

### Consulta 4

Consultar reservas realizadas.

---

### Consulta 5

Mostrar servicios del hotel.

---

## INNER JOIN

### Consulta 6

Mostrar reservas junto con el huésped.

Resultado:

| Huésped | Fecha inicio | Fecha fin |
|---|---|---|

---

### Consulta 7

Mostrar habitaciones con su tipo.

Resultado:

| Habitación | Tipo |
|---|---|

---

### Consulta 8

Mostrar:

- huésped
- habitación
- fechas de reserva

---

### Consulta 9

Mostrar reservas junto con empleado encargado.

---

---

# Caso 5 — Sistema de Gimnasio

## Consultas básicas

### Consulta 1

Mostrar todos los clientes.

---

### Consulta 2

Mostrar entrenadores registrados.

---

### Consulta 3

Consultar clases disponibles.

---

### Consulta 4

Mostrar rutinas creadas.

---

### Consulta 5

Mostrar pagos realizados.

---

## INNER JOIN

### Consulta 6

Mostrar clases junto con el entrenador.

Resultado:

| Clase | Entrenador |
|---|---|

---

### Consulta 7

Mostrar clientes inscritos en clases.

Resultado:

| Cliente | Clase |
|---|---|

---

### Consulta 8

Mostrar:

- cliente
- rutina
- entrenador

---

### Consulta 9

Mostrar pagos con el cliente asociado.

---

# Entregable

Cada grupo debe entregar:

- archivo SQL con las consultas.
- capturas de resultados.
- explicación breve de cada INNER JOIN realizado.

---

# Recomendaciones

Antes de escribir una consulta:

1. Identificar la tabla principal.
2. Revisar qué información se necesita mostrar.
3. Identificar la relación entre tablas.
4. Encontrar la PK y FK que permiten unirlas.