# Actividad Práctica 3
# Transformación de un MER al Modelo Relacional

## Integrantes

Grupo de 3 estudiantes

---

# Objetivo

Transformar un Modelo Entidad Relación (MER) en un modelo relacional identificando correctamente:

- tablas,
- atributos,
- claves primarias,
- claves foráneas,
- relaciones entre tablas.

---

# Instrucciones Generales

Cada grupo debe trabajar sobre el caso de estudio previamente desarrollado en la Actividad 2.

A partir del MER elaborado anteriormente, el grupo deberá construir el modelo relacional correspondiente.

---

# Requerimientos

El grupo debe:

1. Identificar las entidades del MER.

2. Convertir cada entidad en una tabla del modelo relacional.

3. Definir atributos para cada tabla.

4. Identificar la clave primaria (PK) de cada tabla.

5. Identificar las claves foráneas (FK) necesarias para representar las relaciones.

6. Representar correctamente las relaciones entre tablas.

7. Explicar cómo se transformaron las cardinalidades del MER al modelo relacional.

---

# Reglas importantes

- Cada tabla debe tener una clave primaria.
- Las relaciones entre entidades deben reflejarse mediante claves foráneas.
- Deben mantenerse las cardinalidades definidas en el MER original.
- No se requiere crear código SQL todavía.
- El trabajo debe enfocarse únicamente en el diseño del modelo relacional.

---

# Entregable

El grupo debe entregar:

- Modelo relacional completo.
- Explicación breve de las relaciones.
- Identificación clara de PK y FK.
- Conclusiones del ejercicio.

---

# Caso Grupo 1 — Sistema de Biblioteca

## Modelo Entidad Relación Base

Entidades:

- Libro
- Usuario
- Prestamo

Relaciones:

- Usuario realiza Préstamo
- Libro participa en Préstamo

Cardinalidades:

- Usuario 1:N Prestamo
- Libro 1:N Prestamo

---

# Actividad del Grupo

Construir el modelo relacional correspondiente al sistema de biblioteca.

Debe incluir:

- tablas,
- atributos,
- PK,
- FK,
- relaciones.

---

# Caso Grupo 2 — Sistema de Clínica

## Modelo Entidad Relación Base

Entidades:

- Paciente
- Medico
- Cita

Relaciones:

- Paciente agenda Cita
- Medico atiende Cita

Cardinalidades:

- Paciente 1:N Cita
- Medico 1:N Cita

---

# Actividad del Grupo

Construir el modelo relacional correspondiente al sistema de clínica.

Debe incluir:

- tablas,
- atributos,
- PK,
- FK,
- relaciones.

---

# Caso Grupo 3 — Sistema de Restaurante

## Modelo Entidad Relación Base

Entidades:

- Cliente
- Pedido
- Plato

Relaciones:

- Cliente realiza Pedido
- Pedido contiene Plato

Cardinalidades:

- Cliente 1:N Pedido
- Pedido N:M Plato

---

# Actividad del Grupo

Construir el modelo relacional correspondiente al sistema de restaurante.

Debe incluir:

- tablas,
- atributos,
- PK,
- FK,
- relaciones.

---

# Caso Grupo 4 — Sistema de Hotel

## Modelo Entidad Relación Base

Entidades:

- Huesped
- Habitacion
- Reserva

Relaciones:

- Huesped realiza Reserva
- Habitacion participa en Reserva

Cardinalidades:

- Huesped 1:N Reserva
- Habitacion 1:N Reserva

---

# Actividad del Grupo

Construir el modelo relacional correspondiente al sistema de hotel.

Debe incluir:

- tablas,
- atributos,
- PK,
- FK,
- relaciones.

---

# Caso Grupo 5 — Sistema de Gimnasio

## Modelo Entidad Relación Base

Entidades:

- Cliente
- Entrenador
- Clase

Relaciones:

- Cliente se inscribe en Clase
- Entrenador dirige Clase

Cardinalidades:

- Cliente N:M Clase
- Entrenador 1:N Clase

---

# Actividad del Grupo

Construir el modelo relacional correspondiente al sistema de gimnasio.

Debe incluir:

- tablas,
- atributos,
- PK,
- FK,
- relaciones.

---

# Recomendaciones

- Revisar cuidadosamente las cardinalidades.
- Verificar qué relaciones requieren tablas intermedias.
- Mantener nombres claros y consistentes.
- Diferenciar correctamente PK y FK.
- Pensar cómo se almacenaría realmente la información en una base de datos.