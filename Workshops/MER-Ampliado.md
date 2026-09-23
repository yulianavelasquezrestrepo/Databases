# Actividad 3 – Ampliación del Modelo Entidad Relación (MER)

## Modalidad

Trabajo en los mismos grupos de la Actividad 2.

---

# Objetivo

Ampliar el Modelo Entidad Relación (MER) desarrollado anteriormente, incorporando nuevas entidades, atributos y relaciones que permitan representar un sistema de información más completo.

El modelo resultante será utilizado posteriormente para realizar la transformación del Modelo Entidad Relación a un Modelo Relacional.

---

# Punto de partida

Cada grupo debe utilizar como base el MER desarrollado en la **Actividad 2**.

**No se debe realizar un modelo completamente nuevo.**

El objetivo es analizar cómo las nuevas necesidades del sistema modifican y amplían el modelo existente.

---

# Instrucciones Generales

Cada grupo debe:

1. Recuperar el MER realizado en la Actividad 2.

2. Revisar las nuevas necesidades descritas para su caso.

3. Identificar las nuevas entidades necesarias.

4. Definir los atributos de las nuevas entidades.

5. Determinar si las entidades existentes necesitan nuevos atributos.

6. Identificar las nuevas relaciones.

7. Determinar las cardinalidades de todas las relaciones.

8. Actualizar el diagrama MER.

9. Revisar que todas las entidades estén correctamente relacionadas.

10. Entregar el MER completo, incluyendo las entidades originales y las nuevas entidades.

---

# Requisitos del MER ampliado

El modelo final debe contener:

- Entidades.
- Atributos.
- Relaciones.
- Cardinalidades.
- Relaciones uno a uno (1:1), cuando el caso lo requiera.
- Relaciones uno a muchos (1:N).
- Relaciones muchos a muchos (N:M), cuando el caso lo requiera.

En esta actividad **no es necesario definir claves primarias ni claves foráneas**.

Estas serán trabajadas posteriormente durante la transformación del MER al Modelo Relacional.

---

# Caso 1 – Sistema de Biblioteca

En la actividad anterior la biblioteca necesitaba organizar información sobre:

- Libros
- Usuarios
- Préstamos

La biblioteca ahora desea ampliar su sistema.

Cada libro pertenece a una **editorial**.

Una editorial puede publicar muchos libros.

Los libros también pueden tener uno o varios **autores**.

Un autor puede escribir varios libros.

La biblioteca dispone de diferentes **ejemplares** de un mismo libro.

Por ejemplo, puede tener cinco copias físicas del mismo libro.

Cada ejemplar puede participar en diferentes préstamos a lo largo del tiempo.

Además, los usuarios que entreguen un ejemplar después de la fecha establecida pueden recibir una **multa**.

La multa debe almacenar:

- fecha,
- valor,
- estado del pago.

## El MER ampliado debe considerar:

- Libros
- Usuarios
- Préstamos
- Editoriales
- Autores
- Ejemplares
- Multas

## Analizar especialmente:

- Relación entre libros y autores.
- Relación entre libros y ejemplares.
- Relación entre editoriales y libros.
- Relación entre usuarios y préstamos.
- Relación entre ejemplares y préstamos.
- Relación entre préstamos y multas.

---

# Caso 2 – Sistema de Clínica Médica

En la actividad anterior la clínica manejaba:

- Pacientes
- Médicos
- Citas

La clínica ahora necesita ampliar su sistema.

Cada médico pertenece a una **especialidad médica**.

Una especialidad puede tener varios médicos.

Los médicos pueden ordenar **exámenes médicos** durante una cita.

Una cita puede requerir varios exámenes.

El sistema también debe registrar los **consultorios** donde se realizan las citas.

Un consultorio puede ser utilizado para muchas citas en diferentes horarios.

Después de una cita, el médico puede generar una **fórmula médica**.

Una fórmula puede contener varios **medicamentos**.

Un medicamento puede aparecer en muchas fórmulas médicas.

## El MER ampliado debe considerar:

- Pacientes
- Médicos
- Citas
- Especialidades
- Exámenes
- Consultorios
- Fórmulas médicas
- Medicamentos

## Analizar especialmente:

- Relación entre médicos y especialidades.
- Relación entre pacientes y citas.
- Relación entre médicos y citas.
- Relación entre citas y consultorios.
- Relación entre citas y exámenes.
- Relación entre citas y fórmulas médicas.
- Relación entre fórmulas médicas y medicamentos.

---

# Caso 3 – Sistema de Restaurante

En la actividad anterior el restaurante manejaba:

- Clientes
- Pedidos
- Platos

El restaurante ahora necesita ampliar su sistema.

Los platos están organizados en **categorías**, por ejemplo:

- entradas,
- platos fuertes,
- bebidas,
- postres.

Una categoría puede contener varios platos.

Cada pedido es atendido por un **mesero**.

Un mesero puede atender muchos pedidos durante su jornada.

El restaurante también desea registrar las **mesas**.

Una mesa puede tener muchos pedidos en diferentes momentos.

Los platos son preparados utilizando diferentes **ingredientes**.

Un plato puede utilizar muchos ingredientes y un ingrediente puede utilizarse en diferentes platos.

Finalmente, cada pedido puede generar un **pago**.

El pago registra:

- fecha,
- valor,
- método de pago.

## El MER ampliado debe considerar:

- Clientes
- Pedidos
- Platos
- Categorías
- Meseros
- Mesas
- Ingredientes
- Pagos

## Analizar especialmente:

- Relación entre clientes y pedidos.
- Relación entre pedidos y platos.
- Relación entre categorías y platos.
- Relación entre meseros y pedidos.
- Relación entre mesas y pedidos.
- Relación entre platos e ingredientes.
- Relación entre pedidos y pagos.

---

# Caso 4 – Sistema de Hotel

En la actividad anterior el hotel manejaba:

- Habitaciones
- Huéspedes
- Reservas

El hotel ahora desea ampliar su sistema.

Cada habitación pertenece a un **tipo de habitación**, por ejemplo:

- sencilla,
- doble,
- familiar,
- suite.

Un tipo de habitación puede corresponder a muchas habitaciones.

Los huéspedes pueden solicitar **servicios adicionales** durante su estadía, como:

- lavandería,
- restaurante,
- transporte,
- spa.

Una reserva puede utilizar varios servicios y un servicio puede ser utilizado en muchas reservas.

El hotel también registra los **pagos** realizados sobre las reservas.

Una reserva puede tener uno o varios pagos.

Además, cada reserva es gestionada inicialmente por un **empleado** del hotel.

Un empleado puede gestionar muchas reservas.

## El MER ampliado debe considerar:

- Habitaciones
- Huéspedes
- Reservas
- Tipos de habitación
- Servicios
- Pagos
- Empleados

## Analizar especialmente:

- Relación entre huéspedes y reservas.
- Relación entre habitaciones y reservas.
- Relación entre habitaciones y tipos de habitación.
- Relación entre reservas y servicios.
- Relación entre reservas y pagos.
- Relación entre empleados y reservas.

---

# Caso 5 – Sistema de Gimnasio

En la actividad anterior el gimnasio manejaba:

- Clientes
- Entrenadores
- Clases

El gimnasio ahora desea ampliar su sistema.

Cada cliente debe tener un **plan de membresía**.

Los planes disponibles pueden ser:

- básico,
- estándar,
- premium.

Un mismo plan puede ser contratado por muchos clientes.

Las clases pertenecen a un **tipo de clase**, por ejemplo:

- yoga,
- spinning,
- funcional,
- zumba.

Un tipo puede tener varias clases programadas.

Las clases se realizan en diferentes **salones**.

Un salón puede utilizarse para muchas clases en diferentes horarios.

Los clientes también pueden realizar **pagos** relacionados con su membresía.

Un cliente puede realizar muchos pagos.

Además, los entrenadores pueden tener diferentes **especialidades** y una especialidad puede corresponder a varios entrenadores.

## El MER ampliado debe considerar:

- Clientes
- Entrenadores
- Clases
- Planes de membresía
- Tipos de clase
- Salones
- Pagos
- Especialidades

## Analizar especialmente:

- Relación entre clientes y clases.
- Relación entre entrenadores y clases.
- Relación entre clientes y planes.
- Relación entre clases y tipos de clase.
- Relación entre clases y salones.
- Relación entre clientes y pagos.
- Relación entre entrenadores y especialidades.

---

# Caso 6 – Sistema de Tienda de Ropa

En la actividad anterior la tienda manejaba:

- Clientes
- Productos
- Ventas

La tienda ahora desea ampliar su sistema.

Cada producto pertenece a una **categoría**, por ejemplo:

- camisetas,
- pantalones,
- zapatos,
- accesorios.

Una categoría puede contener muchos productos.

Cada producto pertenece a una **marca**.

Una marca puede tener muchos productos.

La tienda trabaja con diferentes **proveedores**.

Un proveedor puede suministrar varios productos y un producto puede ser suministrado por diferentes proveedores.

Cada venta es atendida por un **empleado**.

Un empleado puede registrar muchas ventas.

Los clientes pueden realizar diferentes **pagos** asociados a sus ventas.

Además, algunos productos pueden tener **promociones**.

Una promoción puede aplicarse a varios productos y un producto puede participar en diferentes promociones en distintos momentos.

## El MER ampliado debe considerar:

- Clientes
- Productos
- Ventas
- Categorías
- Marcas
- Proveedores
- Empleados
- Promociones

## Analizar especialmente:

- Relación entre clientes y ventas.
- Relación entre ventas y productos.
- Relación entre productos y categorías.
- Relación entre productos y marcas.
- Relación entre productos y proveedores.
- Relación entre empleados y ventas.
- Relación entre productos y promociones.

---

# Caso 7 – Sistema de Taller de Vehículos

En la actividad anterior el taller manejaba:

- Clientes
- Vehículos
- Servicios

El taller ahora necesita ampliar su sistema.

Cada vehículo pertenece a una **marca**.

Una marca puede tener muchos vehículos registrados.

Cada ingreso del vehículo al taller genera una **orden de trabajo**.

Una orden puede incluir varios servicios.

Los servicios son realizados por **mecánicos**.

Un mecánico puede realizar muchos servicios.

Durante una reparación pueden utilizarse diferentes **repuestos**.

Un repuesto puede ser utilizado en muchas reparaciones.

Los repuestos son suministrados por diferentes **proveedores**.

Un proveedor puede suministrar varios repuestos.

Finalmente, cada orden de trabajo puede generar una **factura**.

## El MER ampliado debe considerar:

- Clientes
- Vehículos
- Servicios
- Marcas
- Órdenes de trabajo
- Mecánicos
- Repuestos
- Proveedores
- Facturas

## Analizar especialmente:

- Relación entre clientes y vehículos.
- Relación entre vehículos y marcas.
- Relación entre vehículos y órdenes de trabajo.
- Relación entre órdenes y servicios.
- Relación entre mecánicos y servicios.
- Relación entre servicios y repuestos.
- Relación entre proveedores y repuestos.
- Relación entre órdenes y facturas.

---

# Caso 8 – Sistema de Universidad

En la actividad anterior la universidad manejaba:

- Estudiantes
- Cursos
- Docentes

La universidad ahora necesita ampliar su sistema.

Los cursos pertenecen a un **programa académico**.

Un programa académico puede contener muchos cursos.

Los docentes pertenecen a diferentes **departamentos académicos**.

Un departamento puede tener varios docentes.

Cada curso puede abrir diferentes **grupos** durante un periodo académico.

Por ejemplo, Bases de Datos puede tener:

- Grupo A
- Grupo B
- Grupo C

Cada grupo es dirigido por un docente.

Los estudiantes se matriculan en los diferentes grupos.

La universidad también debe registrar las **aulas** donde se desarrollan las clases.

Un aula puede ser utilizada por muchos grupos en diferentes horarios.

Finalmente, los estudiantes reciben **calificaciones** correspondientes a los cursos matriculados.

## El MER ampliado debe considerar:

- Estudiantes
- Cursos
- Docentes
- Programas académicos
- Departamentos
- Grupos
- Aulas
- Calificaciones

## Analizar especialmente:

- Relación entre programas y cursos.
- Relación entre departamentos y docentes.
- Relación entre cursos y grupos.
- Relación entre docentes y grupos.
- Relación entre estudiantes y grupos.
- Relación entre grupos y aulas.
- Relación entre estudiantes y calificaciones.

---

# Caso 9 – Sistema de Agencia de Viajes

En la actividad anterior la agencia manejaba:

- Clientes
- Viajes
- Reservas

La agencia ahora desea ampliar su sistema.

Cada viaje tiene asociado uno o varios **destinos**.

Un destino puede formar parte de diferentes viajes.

Los clientes pueden realizar **pagos** correspondientes a sus reservas.

Una reserva puede tener varios pagos.

La agencia trabaja con diferentes **hoteles**.

Un destino puede ofrecer varios hoteles y un hotel puede aparecer en diferentes paquetes turísticos.

También existen diferentes **transportes**, por ejemplo:

- avión,
- bus,
- barco.

Un viaje puede utilizar diferentes medios de transporte.

La agencia cuenta con **asesores** encargados de gestionar las reservas.

Un asesor puede gestionar muchas reservas.

## El MER ampliado debe considerar:

- Clientes
- Viajes
- Reservas
- Destinos
- Pagos
- Hoteles
- Transportes
- Asesores

## Analizar especialmente:

- Relación entre clientes y reservas.
- Relación entre viajes y reservas.
- Relación entre viajes y destinos.
- Relación entre reservas y pagos.
- Relación entre destinos y hoteles.
- Relación entre viajes y transportes.
- Relación entre asesores y reservas.

---

# Caso 10 – Sistema de Plataforma de Streaming

En la actividad anterior la plataforma manejaba:

- Usuarios
- Películas
- Visualizaciones

La plataforma ahora desea ampliar su sistema.

Cada película puede pertenecer a uno o varios **géneros**.

Un género puede contener muchas películas.

Las películas tienen uno o varios **actores**.

Un actor puede participar en muchas películas.

Cada película tiene un **director**, aunque un director puede dirigir varias películas.

Los usuarios deben contratar un **plan de suscripción**.

Un plan puede ser utilizado por muchos usuarios.

Los usuarios pueden crear diferentes **perfiles** dentro de su cuenta.

Cada perfil puede realizar muchas visualizaciones.

Además, los perfiles pueden agregar películas a una **lista de favoritos**.

## El MER ampliado debe considerar:

- Usuarios
- Películas
- Visualizaciones
- Géneros
- Actores
- Directores
- Planes de suscripción
- Perfiles

## Analizar especialmente:

- Relación entre usuarios y planes.
- Relación entre usuarios y perfiles.
- Relación entre perfiles y visualizaciones.
- Relación entre películas y visualizaciones.
- Relación entre películas y géneros.
- Relación entre películas y actores.
- Relación entre películas y directores.
- Relación entre perfiles y películas favoritas.

---

# Caso 11 – Sistema de Veterinaria

En la actividad anterior la veterinaria manejaba:

- Dueños
- Mascotas
- Veterinarios
- Consultas

La veterinaria ahora desea ampliar su sistema.

Cada mascota pertenece a una **especie**.

Una especie puede tener muchas mascotas registradas.

Cada mascota también puede pertenecer a una **raza**.

Una raza puede corresponder a muchas mascotas.

Durante una consulta, el veterinario puede aplicar diferentes **vacunas**.

Una mascota puede recibir muchas vacunas durante su vida.

El veterinario también puede formular diferentes **medicamentos**.

Un medicamento puede ser utilizado en muchas consultas.

La clínica dispone de diferentes **consultorios**.

Un consultorio puede utilizarse para muchas consultas en diferentes horarios.

Finalmente, cada consulta genera un **pago**.

## El MER ampliado debe considerar:

- Dueños
- Mascotas
- Veterinarios
- Consultas
- Especies
- Razas
- Vacunas
- Medicamentos
- Consultorios
- Pagos

## Analizar especialmente:

- Relación entre dueños y mascotas.
- Relación entre mascotas y especies.
- Relación entre mascotas y razas.
- Relación entre mascotas y consultas.
- Relación entre veterinarios y consultas.
- Relación entre consultas y vacunas.
- Relación entre consultas y medicamentos.
- Relación entre consultas y consultorios.
- Relación entre consultas y pagos.

---

# Entregable

Cada grupo debe entregar:

## 1. MER original

El Modelo Entidad Relación desarrollado en la Actividad 2.

## 2. MER ampliado

El nuevo Modelo Entidad Relación que incluya:

- entidades originales,
- nuevas entidades,
- atributos,
- relaciones,
- cardinalidades.

## 3. Listado de nuevas entidades

Indicar cuáles entidades fueron agregadas al modelo original.

## 4. Listado de nuevas relaciones

Por cada nueva relación indicar:

- entidades participantes,
- nombre de la relación,
- cardinalidad.

Ejemplo:

`EDITORIAL 1:N LIBRO`

Una editorial puede publicar muchos libros y cada libro pertenece a una editorial.

## 5. Análisis del modelo

Responder:

1. ¿Cuántas entidades tenía el modelo inicial?
2. ¿Cuántas entidades tiene ahora?
3. ¿Qué nuevas relaciones fueron necesarias?
4. ¿Cuáles relaciones son 1:1?
5. ¿Cuáles relaciones son 1:N?
6. ¿Cuáles relaciones son N:M?
7. ¿Cuál consideran que es la relación más compleja del modelo y por qué?

---

# Condiciones

- No agregar claves foráneas al MER.
- No transformar todavía el modelo en tablas.
- No realizar todavía el Modelo Relacional.
- No agregar tablas intermedias pensando en la implementación.
- Representar las relaciones según la notación utilizada durante las clases.
- Justificar las cardinalidades utilizadas.

---

# Próxima actividad

El MER construido en esta actividad será utilizado posteriormente como punto de partida para realizar la transformación:

**Modelo Entidad Relación (MER) → Modelo Relacional**

En esa actividad se analizarán:

- tablas,
- claves primarias,
- claves foráneas,
- transformación de relaciones 1:1,
- transformación de relaciones 1:N,
- transformación de relaciones N:M,
- tablas intermedias o asociativas,
- restricciones de integridad.