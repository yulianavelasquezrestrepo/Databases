# Actividad Práctica 5
# Expansión y Normalización del Modelo Relacional

## Integrantes

Grupo de 3 estudiantes

---

# Objetivo

Ampliar un modelo relacional existente agregando nuevas tablas y aplicar correctamente:

- Primera Forma Normal (1FN)
- Segunda Forma Normal (2FN)
- Tercera Forma Normal (3FN)

con el fin de mejorar la organización, integridad y consistencia de la información.

---

# Instrucciones Generales

Cada grupo debe trabajar sobre el modelo relacional construido en la Actividad Práctica 3.

A partir de dicho modelo, deberán:

1. Agregar 4 nuevas tablas relacionadas con el contexto del sistema.
2. Identificar posibles problemas de redundancia o dependencias.
3. Aplicar las formas normales necesarias.
4. Presentar el modelo relacional final normalizado.

---

# Requerimientos

El grupo debe:

1. Diseñar 4 tablas nuevas relacionadas con el caso asignado.
2. Definir atributos para cada tabla.
3. Identificar PK y FK.
4. Aplicar correctamente:
   - 1FN
   - 2FN
   - 3FN
5. Explicar los cambios realizados durante el proceso de normalización.
6. Entregar el modelo relacional final normalizado.

---

# Reglas importantes

- Todas las tablas deben tener clave primaria.
- Las relaciones deben representarse mediante claves foráneas.
- No deben existir atributos multivaluados.
- No deben existir dependencias parciales.
- No deben existir dependencias transitivas.
- No se requiere implementar SQL todavía.

---

# Entregable

El grupo debe entregar:

- Modelo relacional ampliado.
- Explicación de las nuevas tablas.
- Aplicación de 1FN, 2FN y 3FN.
- Modelo final normalizado.
- Conclusiones del ejercicio.

---

# Grupo 1 — Sistema de Biblioteca

## Modelo Relacional Base

Tablas existentes:

- Libro
- Usuario
- Prestamo

---

# Nuevas Tablas Obligatorias

Agregar las siguientes tablas:

1. Autor
2. Categoria
3. Editorial
4. Multa

---

# Requerimientos del Grupo

El grupo debe:

- Relacionar libros con autores.
- Clasificar libros por categorías.
- Asociar libros con editoriales.
- Registrar multas por retrasos.

---

# Aspectos de Normalización Esperados

El grupo debe evitar:

- repetir datos de editoriales en múltiples libros,
- repetir datos de autores,
- almacenar múltiples categorías en un mismo atributo,
- redundancia en multas y préstamos.

---

# Grupo 2 — Sistema de Clínica Médica

## Modelo Relacional Base

Tablas existentes:

- Paciente
- Medico
- Cita

---

# Nuevas Tablas Obligatorias

Agregar las siguientes tablas:

1. Especialidad
2. Consultorio
3. Factura
4. Medicamento

---

# Requerimientos del Grupo

El grupo debe:

- asociar médicos con especialidades,
- registrar consultorios,
- generar facturas por citas,
- relacionar medicamentos con pacientes o citas.

---

# Aspectos de Normalización Esperados

El grupo debe evitar:

- repetir información de especialidades,
- almacenar múltiples medicamentos en un solo campo,
- redundancia de datos de facturación,
- dependencias transitivas entre médicos y consultorios.

---

# Grupo 3 — Sistema de Restaurante

## Modelo Relacional Base

Tablas existentes:

- Cliente
- Pedido
- Plato

---

# Nuevas Tablas Obligatorias

Agregar las siguientes tablas:

1. Categoria_Plato
2. Mesero
3. Factura
4. Ingrediente

---

# Requerimientos del Grupo

El grupo debe:

- clasificar platos,
- registrar meseros,
- asociar facturas a pedidos,
- relacionar ingredientes con platos.

---

# Aspectos de Normalización Esperados

El grupo debe evitar:

- listas de ingredientes en un solo atributo,
- repetición de categorías,
- duplicación de datos de facturación,
- redundancia de información de meseros.

---

# Grupo 4 — Sistema de Hotel

## Modelo Relacional Base

Tablas existentes:

- Huesped
- Habitacion
- Reserva

---

# Nuevas Tablas Obligatorias

Agregar las siguientes tablas:

1. Tipo_Habitacion
2. Pago
3. Empleado
4. Servicio

---

# Requerimientos del Grupo

El grupo debe:

- clasificar habitaciones,
- registrar pagos,
- administrar empleados,
- gestionar servicios del hotel.

---

# Aspectos de Normalización Esperados

El grupo debe evitar:

- repetir tipos de habitación,
- redundancia en pagos,
- múltiples servicios en un solo campo,
- dependencias transitivas relacionadas con empleados.

---

# Grupo 5 — Sistema de Gimnasio

## Modelo Relacional Base

Tablas existentes:

- Cliente
- Entrenador
- Clase

---

# Nuevas Tablas Obligatorias

Agregar las siguientes tablas:

1. Plan
2. Pago
3. Sede
4. Rutina

---

# Requerimientos del Grupo

El grupo debe:

- administrar planes de membresía,
- registrar pagos,
- gestionar sedes,
- asignar rutinas a clientes.

---

# Aspectos de Normalización Esperados

El grupo debe evitar:

- almacenar varias rutinas en un mismo atributo,
- repetir datos de planes,
- redundancia de pagos,
- dependencias transitivas entre sedes y entrenadores.

---

# Recomendaciones

- Revisar cuidadosamente dependencias entre atributos.
- Verificar redundancias antes de normalizar.
- Separar información repetitiva en nuevas tablas.
- Mantener nombres claros y consistentes.
- Pensar cómo se almacenaría realmente la información en una base de datos relacional.