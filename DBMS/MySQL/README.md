# MySQL: conceptos generales e instalación paso a paso

## ¿Qué es MySQL?

MySQL es un **sistema de gestión de bases de datos relacional (RDBMS)** de código abierto que permite crear, administrar y consultar bases de datos estructuradas mediante el lenguaje SQL (Structured Query Language).

MySQL se basa en el **modelo relacional**, lo que significa que:
- la información se almacena en **tablas**,
- las tablas están formadas por **filas (registros)** y **columnas (atributos)**,
- las tablas pueden relacionarse entre sí mediante **claves primarias y foráneas**.

Es ampliamente utilizado en entornos académicos, empresariales y de desarrollo de software.

---

## ¿Para qué se utiliza MySQL?

MySQL se utiliza para:
- almacenar información estructurada de forma persistente,
- garantizar integridad y consistencia de los datos,
- permitir consultas eficientes sobre grandes volúmenes de información,
- soportar aplicaciones que requieren múltiples usuarios accediendo a los datos.

En el contexto del curso, MySQL se usará para:
- implementar modelos relacionales diseñados en papel,
- aplicar conceptos de normalización y claves,
- ejecutar consultas SQL de forma práctica.

---

## Componentes principales de MySQL

Al trabajar con MySQL normalmente se utilizan dos componentes principales.

### MySQL Server

Es el **motor de base de datos** propiamente dicho.
- Se ejecuta como un servicio en el sistema operativo.
- Se encarga de almacenar, procesar y proteger los datos.
- Es indispensable para que MySQL funcione.

### MySQL Workbench

Es una **herramienta gráfica** que permite:
- conectarse al servidor MySQL,
- ejecutar comandos SQL,
- diseñar modelos de datos,
- administrar bases de datos y usuarios.

MySQL Workbench **no es el motor de base de datos**, es solo una interfaz.

---

## ¿Qué significa instalar MySQL de forma local?

Instalar MySQL de forma local significa que:
- el servidor MySQL se ejecuta en el computador del estudiante,
- las bases de datos existen únicamente en ese equipo,
- no se requiere conexión a internet para trabajar.

Este enfoque es ideal para:
- prácticas académicas,
- pruebas de diseño,
- aprendizaje de SQL sin depender de servidores externos.

---

## Requisitos previos para la instalación

Antes de instalar MySQL se recomienda:
- contar con un sistema operativo actualizado,
- tener permisos de administrador en el equipo,
- disponer de al menos 2 GB de memoria RAM libre,
- cerrar otros programas durante la instalación.

---

## Instalación de MySQL paso a paso

### Paso 1: Descargar MySQL

1. Acceder al sitio oficial de MySQL.
2. Seleccionar **MySQL Community Server**.
3. Elegir el instalador correspondiente al sistema operativo.
4. Descargar el archivo de instalación.

Se recomienda utilizar una versión **estable (LTS)**.

---

### Paso 2: Ejecutar el instalador

1. Abrir el archivo descargado.
2. Iniciar el asistente de instalación.
3. Seleccionar el tipo de instalación:
   - *Developer Default* o
   - *Server Only*.

---

### Paso 3: Configuración del servidor

Durante la instalación se solicitará:

- **Puerto del servidor**
  - Por defecto: `3306`
- **Método de autenticación**
  - Se recomienda el método estándar.
- **Usuario administrador**
  - Usuario: `root`
  - Definir una contraseña segura.

Esta información debe ser almacenada por el estudiante.

---

### Paso 4: Instalación de MySQL Workbench

Si no se instaló junto con el servidor:

1. Descargar MySQL Workbench desde el sitio oficial.
2. Ejecutar el instalador.
3. Completar el proceso usando las opciones por defecto.

---

### Paso 5: Verificación de la instalación

1. Abrir MySQL Workbench.
2. Crear o seleccionar una conexión local.
3. Ingresar:
   - usuario: `root`
   - contraseña definida durante la instalación.
4. Conectarse al servidor.

Si la conexión es exitosa, MySQL está correctamente instalado.

---

## Estructura básica de trabajo en MySQL

Una vez instalado, el flujo típico de trabajo es:

1. Crear una base de datos.
2. Seleccionar la base de datos.
3. Crear tablas.
4. Definir claves primarias y foráneas.
5. Insertar y consultar datos.

Este flujo refleja el proceso:
**diseño → implementación → consultas**.

---

## Errores comunes durante la instalación

Algunos errores frecuentes incluyen:
- olvidar la contraseña del usuario `root`,
- intentar instalar MySQL sin permisos de administrador,
- tener el puerto `3306` ocupado por otro servicio,
- confundir MySQL Server con MySQL Workbench.

Estos problemas están relacionados con la configuración del entorno, no con el diseño de bases de datos.

---

## Recomendaciones para el curso

- Mantener MySQL instalado durante todo el curso.
- No modificar configuraciones avanzadas sin guía docente.
- Trabajar siempre desde MySQL Workbench.
- Guardar los scripts SQL desarrollados en clase.

---