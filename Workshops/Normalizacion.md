# Actividad Práctica 5

# Ampliación y Normalización del Modelo Relacional

---

# Objetivo

El objetivo de esta actividad es que los estudiantes fortalezcan sus conocimientos en:

* Diseño de bases de datos relacionales.
* Ampliación de modelos relacionales existentes.
* Aplicación de relaciones entre tablas.
* Proceso de normalización.
* Aplicación de la Primera, Segunda y Tercera Forma Normal.

---

# Instrucciones Generales

Basados en los modelos relacionales construidos en la Actividad Práctica 3, deberán:

1. Agregar 4 nuevas tablas al modelo relacional asignado.
2. Definir:
    * atributos,
    * claves primarias,
    * claves foráneas,
    * relaciones entre tablas.
3. Explicar cómo se relacionan las nuevas tablas con el modelo original.
4. Aplicar correctamente:
    * Primera Forma Normal (1FN),
    * Segunda Forma Normal (2FN),
    * Tercera Forma Normal (3FN).
5. Mostrar el modelo relacional final normalizado.

---

# Caso 1 — Sistema de Biblioteca

# Modelo Base

Tablas existentes:

* Usuario
* Libro
* Prestamo

---

# Actividad

Agregar las siguientes 4 tablas:

* Autor
* Categoria
* Multa
* Biblioteca

---

# Requerimientos

# Relaciones sugeridas

* Un Libro pertenece a una Categoria.
* Un Libro puede tener uno o varios Autores.
* Un Prestamo puede generar una Multa.
* Una Biblioteca almacena muchos Libros.

---

# Deben realizar

1. Diseño relacional

Definir:

* atributos,
* PK,
* FK,
* relaciones.

---

2. Normalización

# Aplicar:

Primera Forma Normal (1FN)

* Eliminar atributos multivaluados.
* Garantizar atomicidad.

Segunda Forma Normal (2FN)

* Eliminar dependencias parciales.

Tercera Forma Normal (3FN)

* Eliminar dependencias transitivas.

---

# Caso 2 — Sistema de Clínica Médica

# Modelo Base

Tablas existentes:

* Paciente
* Medico
* Cita

---

# Actividad

Agregar las siguientes 4 tablas:

* Especialidad
* Consultorio
* Factura
* Medicamento

---

# Requerimientos

# Relaciones sugeridas

* Un Médico pertenece a una Especialidad.
* Una Cita se realiza en un Consultorio.
* Una Cita genera una Factura.
* Un Paciente puede recibir Medicamentos.

---

# Deben realizar

1. Diseño relacional

Definir:

* atributos,
* PK,
* FK,
* relaciones.

---

2. Normalización

Aplicar:

Primera Forma Normal (1FN)

* Evitar datos repetidos.
* Garantizar campos atómicos.

Segunda Forma Normal (2FN)

* Eliminar dependencias parciales.

Tercera Forma Normal (3FN)

* Eliminar dependencias transitivas.

---

# Caso 3 — Sistema de Restaurante

# Modelo Base

Tablas existentes:

* Cliente
* Pedido
* Plato

---

# Actividad

Agregar las siguientes 4 tablas:

* Factura
* Mesero
* CategoriaPlato
* MetodoPago

---

# Requerimientos

# Relaciones sugeridas

* Un Pedido genera una Factura.
* Un Mesero atiende muchos Pedidos.
* Un Plato pertenece a una CategoriaPlato.
* Una Factura utiliza un MetodoPago.

---

# Deben realizar

1. Diseño relacional

Definir:

* atributos,
* PK,
* FK,
* relaciones.

---

2. Normalización

Aplicar:

Primera Forma Normal (1FN)

* Eliminar grupos repetitivos.

Segunda Forma Normal (2FN)

* Eliminar dependencias parciales.

Tercera Forma Normal (3FN)

* Eliminar dependencias transitivas.

---

# Caso 4 — Sistema de Hotel

# Modelo Base

Tablas existentes:

* Huesped
* Habitacion
* Reserva

---

# Actividad

Agregar las siguientes 4 tablas:

* Pago
* Empleado
* TipoHabitacion
* Servicio

---

# Requerimientos

# Relaciones sugeridas

* Una Reserva genera un Pago.
* Un Empleado administra Reservas.
* Una Habitacion pertenece a un TipoHabitacion.
* Una Reserva puede incluir Servicios.

---

# Deben realizar

1. Diseño relacional

Definir:

* atributos,
* PK,
* FK,
* relaciones.

---

2. Normalización

Aplicar:

Primera Forma Normal (1FN)

* Eliminar datos multivaluados.

Segunda Forma Normal (2FN)

* Eliminar dependencias parciales.

Tercera Forma Normal (3FN)

* Eliminar dependencias transitivas.

---

# Caso 5 — Sistema de Gimnasio

# Modelo Base

Tablas existentes:

* Cliente
* Entrenador
* Clase

---

# Actividad

Agregar las siguientes 4 tablas:

* Membresia
* Rutina
* Sala
* Pago

---

# Requerimientos

# Relaciones sugeridas

* Un Cliente tiene una Membresia.
* Un Cliente puede tener varias Rutinas.
* Una Clase se dicta en una Sala.
* Un Cliente realiza Pagos.

---

# Deben realizar

1. Diseño relacional

Definir:

* atributos,
* PK,
* FK,
* relaciones.

---

2. Normalización

Aplicar:

Primera Forma Normal (1FN)

* Garantizar atomicidad.

Segunda Forma Normal (2FN)

* Eliminar dependencias parciales.

Tercera Forma Normal (3FN)

* Eliminar dependencias transitivas.

---

# Entregables

Cada grupo debe entregar:

1. Modelo Entidad Relación ampliado.
2. Modelo relacional ampliado.
3. Explicación de relaciones.
4. Identificación de PK y FK.
5. Aplicación de:
    * 1FN,
    * 2FN,
    * 3FN.
6. Modelo final normalizado.

---

# Recomendaciones

* Utilizar nombres claros para tablas y atributos.
* Identificar correctamente entidades fuertes y débiles.
* Revisar redundancias.
* Validar integridad referencial.
* Mantener consistencia en tipos de datos.
