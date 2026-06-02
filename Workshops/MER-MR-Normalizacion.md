 # Actividad Práctica 4
 # MER - MR - Normalización

 ## Integrantes

Grupo de 3 estudiantes

---

# Objetivo

Ampliar un modelo entidad relación, un modelo relacional y su respectiva normalización, aplicando:

- Modelo Conceptual
- Cardinalidad
- Modelo Lógico
- Primera Forma Normal (1FN)
- Segunda Forma Normal (2FN)
- Tercera Forma Normal (3FN)

con el fin de mejorar la organización, integridad y consistencia de la información.

---

# Ejercicio 1: Sistema de Gestión de Taller Mecánico

Una empresa de mantenimiento automotriz necesita desarrollar una base de datos para controlar la información de sus operaciones.

# Requerimientos

* Cada cliente puede registrar varios vehículos.
* Cada vehículo pertenece únicamente a un cliente.
* Los vehículos ingresan al taller para realizar servicios de mantenimiento o reparación.
* Cada orden de servicio puede incluir varios servicios realizados.
* Cada servicio tiene un costo y una descripción.
* Los mecánicos trabajan en distintas órdenes de servicio.
* Un mecánico puede participar en muchas órdenes y una orden puede tener varios mecánicos.
* Se desea almacenar información de repuestos utilizados en cada orden.
* Un repuesto puede utilizarse en múltiples órdenes.

# Actividades

1. Crear el MER.
2. Establecer las cardinalidades.
3. Convertir el MER en modelo relacional.
4. Aplicar normalización hasta 3FN.

Problemas de normalización intencionales

# El sistema actual guarda información así:

Orden	Fecha	Cliente	Teléfono Cliente	Vehículo	Mecánico1	Mecánico2	Servicio1	Servicio2	Repuesto1	Repuesto2

# El grupo debe identificar:

* Dependencias parciales.
* Grupos repetitivos.
* Dependencias transitivas.
* Problemas de redundancia y actualización.

---

# Ejercicio 2: Sistema de Gestión de Eventos Empresariales

Una empresa organiza eventos corporativos para distintas compañías.

# Requerimientos

* Cada empresa cliente puede contratar múltiples eventos.
* Cada evento se realiza en un único salón.
* Un salón puede utilizarse para muchos eventos.
* Los eventos requieren varios proveedores.
* Cada proveedor puede participar en muchos eventos.
* Los proveedores ofrecen diferentes servicios.
* Los empleados coordinadores gestionan eventos específicos.
* Un evento puede tener varios coordinadores.

# Actividades

1. Crear el MER.
2. Establecer las cardinalidades.
3. Convertir el MER en modelo relacional.
4. Aplicar normalización hasta 3FN.

Problemas de normalización intencionales

# La empresa almacena los datos así:

Evento	Empresa	Teléfono Empresa	Salón	Dirección Salón	Proveedor1	Servicio1	Proveedor2	Servicio2	Coordinador1	Coordinador2

# El grupo debe identificar:

* Eliminar atributos multivaluados.
* Resolver redundancia de datos.
* Separar dependencias transitivas.
* Llevar el esquema a 1FN, 2FN y 3FN.

---

# Ejercicio 3: Sistema de Gestión de Cultivos Agrícolas

Una cooperativa agrícola desea administrar la información de sus cultivos y productores.

# Requerimientos

* Cada productor puede tener varias fincas.
* Cada finca puede sembrar distintos cultivos.
* Un cultivo puede sembrarse en muchas fincas.
* Cada cultivo utiliza varios insumos agrícolas.
* Los insumos pueden utilizarse en diferentes cultivos.
* Los trabajadores realizan labores en distintas fincas.
* Cada labor tiene fecha, duración y descripción.

# Actividades

1. Crear el MER.
2. Establecer las cardinalidades.
3. Convertir el MER en modelo relacional.
4. Aplicar normalización hasta 3FN.

Problemas de normalización intencionales

# La cooperativa guarda la información así:

Productor	Finca	Cultivo1	Cultivo2	Insumo1	Insumo2	Trabajador1	Trabajador2	Labor	Fecha

# El grupo debe identificar:

* Repetición de datos.
* Dependencias parciales.
* Dependencias transitivas.
* Problemas derivados de atributos múltiples.

---

# Ejercicio 4: Sistema de Gestión de Agencia de Viajes

Una agencia de viajes necesita controlar paquetes turísticos y reservas.

# Requerimientos

* Cada cliente puede reservar múltiples paquetes turísticos.
* Cada paquete incluye diferentes destinos.
* Un destino puede pertenecer a varios paquetes.
* Los guías turísticos trabajan en diferentes paquetes.
* Un paquete puede tener varios guías.
* Los transportes son asignados a los paquetes turísticos.
* Cada transporte tiene conductor asignado.

# Actividades

1. Crear el MER.
2. Establecer las cardinalidades.
3. Convertir el MER en modelo relacional.
4. Aplicar normalización hasta 3FN.

Problemas de normalización intencionales

# La información se registra así:

Reserva	Cliente	Teléfono Cliente	Paquete	Destino1	Destino2	Guía1	Guía2	Transporte	Conductor

# El grupo debe identificar:

* Resolver grupos repetitivos.
* Detectar dependencias transitivas.
* Eliminar redundancias.
* Aplicar correctamente 1FN, 2FN y 3FN.

---

# Ejercicio 5: Sistema de Gestión de Producción Audiovisual

Una productora audiovisual requiere administrar sus proyectos.

# Requerimientos

* Cada proyecto audiovisual tiene varios empleados.
* Un empleado puede participar en muchos proyectos.
* Cada proyecto utiliza distintos equipos tecnológicos.
* Un equipo puede usarse en varios proyectos.
* Los proyectos tienen clientes asociados.
* Cada cliente puede contratar varios proyectos.
* Cada proyecto maneja múltiples locaciones.
* Las locaciones pueden utilizarse en diferentes proyectos.

# Actividades

1. Crear el MER.
2. Establecer las cardinalidades.
3. Convertir el MER en modelo relacional.
4. Aplicar normalización hasta 3FN.

Problemas de normalización intencionales

# Actualmente la productora almacena los datos así:

Proyecto	Cliente	Teléfono Cliente	Empleado1	Empleado2	Equipo1	Equipo2	Locación1	Locación2

# El grupo debe identificar:

* Detectar anomalías de inserción, actualización y eliminación.
* Resolver atributos repetitivos.
* Identificar dependencias funcionales.
* Aplicar las tres formas normales correctamente.