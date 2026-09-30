# Instalación de MySQL Server y MySQL Workbench

## Objetivo

Instalar y configurar **MySQL Server** y **MySQL Workbench** en Windows o macOS para desarrollar las prácticas del curso de Bases de Datos.

Al finalizar la instalación, el estudiante deberá poder:

- Iniciar MySQL Server.
- Abrir MySQL Workbench.
- Conectarse al servidor utilizando el usuario `root`.
- Crear bases de datos.
- Crear tablas.
- Ejecutar consultas SQL.

---

# Requisitos

Antes de comenzar, verificar que el equipo tenga:

- Windows 10 o superior, o macOS 13 o superior.
- Conexión a Internet.
- Permisos de administrador.
- Espacio disponible para instalar MySQL Server y MySQL Workbench.

> **Importante:** para facilitar las prácticas académicas del curso, todos los estudiantes utilizarán la siguiente contraseña para el usuario `root`:
>
> `Admin12345`
>
> Esta contraseña se utiliza únicamente con fines académicos. En sistemas reales se deben utilizar contraseñas seguras y únicas.

---

# Parte 1. Instalación en Windows

## Paso 1. Descargar MySQL Installer

Ingresar al sitio oficial de MySQL:

https://dev.mysql.com/downloads/installer/

Seleccionar:

**MySQL Installer for Windows**

Descargar **MySQL Installer Community**.

Si la página solicita iniciar sesión o crear una cuenta de Oracle, seleccionar:

**No thanks, just start my download**

para iniciar directamente la descarga.

---

## Paso 2. Ejecutar el instalador

Abrir el archivo descargado.

El nombre será similar a:

`mysql-installer-community-x.x.x.msi`

Windows puede solicitar permisos de administrador.

Seleccionar:

**Yes / Sí**

para permitir la instalación.

---

## Paso 3. Seleccionar el tipo de instalación

Cuando aparezca la pantalla para seleccionar el tipo de instalación, elegir:

**Developer Default**

Esta opción permite instalar los componentes necesarios para las prácticas del curso, entre ellos:

- MySQL Server.
- MySQL Workbench.
- MySQL Shell.
- Connectors.
- Componentes adicionales para desarrollo.

Luego seleccionar:

**Next**

> **Importante:** para este curso utilizar **Developer Default** y no **Server Only**.

---

## Paso 4. Verificar los requisitos

El instalador puede mostrar una pantalla llamada:

**Check Requirements**

Si aparecen componentes adicionales requeridos, permitir que el instalador los instale.

Seleccionar:

**Execute**

Esperar hasta que finalice la instalación de los requisitos.

Luego seleccionar:

**Next**

---

## Paso 5. Instalar los componentes

El instalador mostrará los productos que serán instalados.

Verificar que aparezcan como mínimo:

- MySQL Server.
- MySQL Workbench.

Seleccionar:

**Execute**

Esperar hasta que los componentes aparezcan como instalados correctamente.

Luego seleccionar:

**Next**

---

## Paso 6. Configurar MySQL Server

Cuando aparezca la configuración del servidor, seleccionar:

**Standalone MySQL Server**

Luego seleccionar:

**Next**

---

## Paso 7. Configurar la red y el puerto

Mantener la configuración predeterminada.

Verificar que el puerto sea:

`3306`

El puerto `3306` es el puerto utilizado normalmente por MySQL.

Si aparece una configuración relacionada con el Firewall de Windows, mantener la configuración recomendada por el instalador.

Luego seleccionar:

**Next**

---

## Paso 8. Configurar la autenticación

Si el instalador solicita seleccionar el método de autenticación, utilizar:

**Use Strong Password Encryption for Authentication**

Luego seleccionar:

**Next**

---

## Paso 9. Configurar el usuario administrador

MySQL incluye un usuario administrador llamado:

`root`

Configurar la siguiente contraseña:

`Admin12345`

Por lo tanto, para las prácticas del curso utilizaremos:

| Configuración | Valor |
|---|---|
| Usuario | `root` |
| Contraseña | `Admin12345` |
| Puerto | `3306` |

No es necesario crear usuarios adicionales durante la instalación.

Seleccionar:

**Next**

---

## Paso 10. Configurar MySQL como servicio de Windows

Mantener habilitada la opción para ejecutar MySQL como un servicio de Windows.

Se recomienda conservar las opciones predeterminadas mostradas por el instalador.

Esto permitirá que MySQL Server pueda iniciarse automáticamente con Windows.

Seleccionar:

**Next**

---

## Paso 11. Aplicar la configuración

El instalador mostrará las configuraciones que serán aplicadas.

Seleccionar:

**Execute**

Esperar hasta que todas las configuraciones se completen correctamente.

Luego seleccionar:

**Finish**

Continuar hasta finalizar completamente el asistente de instalación.

---

# Parte 2. Verificación en Windows

## Opción 1. Verificar utilizando MySQL Workbench

Abrir:

**MySQL Workbench**

En la pantalla principal debería aparecer una conexión local similar a:

**Local instance MySQL**

Abrir la conexión.

Cuando solicite las credenciales utilizar:

| Campo | Valor |
|---|---|
| Username | `root` |
| Password | `Admin12345` |

Si se abre correctamente el editor SQL, significa que la conexión con MySQL Server funciona.

---

## Opción 2. Verificar desde CMD

Abrir:

**Símbolo del sistema (CMD)**

Ejecutar:

```cmd
mysql --version
```

Deberá mostrarse información sobre la versión instalada de MySQL.

Por ejemplo:

```text
mysql  Ver x.x.x
```

> **Nota:** si Windows muestra el mensaje `'mysql' is not recognized as an internal or external command`, esto no significa necesariamente que MySQL esté mal instalado.
>
> Puede indicar que MySQL no se encuentra configurado en la variable de entorno `PATH`.
>
> Para las prácticas iniciales del curso es suficiente verificar el funcionamiento utilizando MySQL Workbench.

---

# Parte 3. Instalación en macOS

## Paso 1. Identificar el procesador del Mac

Antes de descargar MySQL, verificar qué procesador tiene el equipo.

Ingresar a:

**Menú Apple → Acerca de esta Mac**

Identificar si el equipo utiliza:

- **Apple Silicon:** M1, M2, M3, M4, etc.
- **Intel:** procesador Intel.

Esta información permitirá seleccionar el instalador correcto.

---

## Paso 2. Descargar MySQL Server

Ingresar al sitio oficial:

https://dev.mysql.com/downloads/mysql/

Seleccionar:

**macOS**

Descargar el instalador correspondiente al procesador del equipo.

### Mac con Apple Silicon

Para procesadores:

- M1
- M2
- M3
- M4
- O posteriores

Seleccionar la versión:

**ARM 64-bit**

### Mac con procesador Intel

Seleccionar la versión:

**x86 64-bit**

Descargar el archivo en formato:

`.dmg`

Si la página solicita iniciar sesión o crear una cuenta de Oracle, seleccionar:

**No thanks, just start my download**

---

## Paso 3. Instalar MySQL Server

Abrir el archivo `.dmg` descargado.

Dentro aparecerá el instalador de MySQL.

Abrir el paquete cuyo nombre será similar a:

`mysql-x.x.x-macos.pkg`

Seguir el asistente utilizando las opciones predeterminadas:

**Continue → Continue → Agree → Install**

macOS puede solicitar la contraseña del usuario administrador del computador.

Ingresarla para autorizar la instalación.

---

## Paso 4. Configurar el usuario root

Durante la configuración de MySQL utilizar:

**Usuario:**

`root`

**Contraseña:**

`Admin12345`

Por lo tanto, la configuración utilizada durante las prácticas será:

| Configuración | Valor |
|---|---|
| Usuario | `root` |
| Contraseña | `Admin12345` |
| Puerto | `3306` |

> **Importante:** utilizar exactamente esta contraseña durante las prácticas académicas para evitar problemas posteriores de conexión.

---

## Paso 5. Finalizar la instalación

Continuar con el asistente hasta que aparezca el mensaje indicando que MySQL fue instalado correctamente.

Cerrar el instalador.

---

# Parte 4. Verificación de MySQL Server en macOS

Abrir:

**Configuración del Sistema**

Buscar la configuración correspondiente a MySQL si está disponible en la versión instalada.

Verificar que MySQL Server se encuentre en ejecución.

También puede verificarse utilizando la Terminal.

Abrir:

**Terminal**

Ejecutar:

```bash
/usr/local/mysql/bin/mysql --version
```

Deberá mostrarse información sobre la versión instalada.

Por ejemplo:

```text
mysql  Ver x.x.x
```

---

# Parte 5. Instalación de MySQL Workbench

## Windows

Si durante la instalación se seleccionó:

**Developer Default**

MySQL Workbench debería haberse instalado automáticamente junto con MySQL Server.

Buscar en el menú Inicio:

**MySQL Workbench**

Abrir la aplicación.

---

## macOS

En macOS, MySQL Workbench debe descargarse por separado.

Ingresar al sitio oficial:

https://dev.mysql.com/downloads/workbench/

Seleccionar la versión correspondiente a macOS.

Descargar el archivo `.dmg`.

Abrir el archivo descargado.

Arrastrar:

**MySQL Workbench**

hacia:

**Applications**

Luego abrir:

**Aplicaciones → MySQL Workbench**

La primera vez que se abra, macOS puede solicitar confirmación para ejecutar la aplicación.

Aceptar para continuar.

---

# Parte 6. Configurar la conexión en MySQL Workbench

Este procedimiento aplica tanto para **Windows como para macOS**.

Abrir:

**MySQL Workbench**

Si ya aparece una conexión local creada automáticamente, puede utilizarse.

Si no aparece ninguna conexión, seleccionar el botón:

**+**

ubicado junto a:

**MySQL Connections**

Configurar los siguientes valores:

| Campo | Valor |
|---|---|
| Connection Name | `MySQL Local` |
| Hostname | `localhost` |
| Port | `3306` |
| Username | `root` |

Seleccionar:

**Test Connection**

Cuando solicite la contraseña ingresar:

`Admin12345`

Si todo está configurado correctamente, deberá aparecer un mensaje indicando que la conexión fue exitosa.

Seleccionar:

**OK**

Guardar la conexión.

---

# Parte 7. Prueba final de funcionamiento

Este procedimiento aplica tanto para **Windows como para macOS**.

Abrir MySQL Workbench.

Abrir la conexión:

**MySQL Local**

Utilizar las siguientes credenciales:

| Campo | Valor |
|---|---|
| Usuario | `root` |
| Contraseña | `Admin12345` |

Una vez abierto el editor SQL, realizar las siguientes pruebas.

---

## Prueba 1. Consultar la versión de MySQL

Ejecutar:

```sql
SELECT VERSION();
```

Seleccionar el botón del **rayo** para ejecutar la consulta.

MySQL deberá mostrar la versión instalada.

---

## Prueba 2. Crear una base de datos

Ejecutar:

```sql
CREATE DATABASE prueba_instalacion;
```

---

## Prueba 3. Consultar las bases de datos

Ejecutar:

```sql
SHOW DATABASES;
```

En los resultados deberá aparecer:

`prueba_instalacion`

---

## Prueba 4. Eliminar la base de datos de prueba

Ejecutar:

```sql
DROP DATABASE prueba_instalacion;
```

La base de datos utilizada para verificar la instalación será eliminada.

---

# Configuración que utilizaremos durante el curso

Durante las prácticas del curso utilizaremos la siguiente configuración:

| Configuración | Valor |
|---|---|
| Servidor | `localhost` |
| Puerto | `3306` |
| Usuario | `root` |
| Contraseña | `Admin12345` |

---

# Resultado esperado

Al finalizar este procedimiento, el estudiante deberá tener correctamente instalado y configurado:

- MySQL Server.
- MySQL Workbench.
- MySQL Server en ejecución.
- Usuario `root`.
- Contraseña académica `Admin12345`.
- Puerto `3306`.
- Una conexión local desde MySQL Workbench.
- Capacidad para crear y eliminar bases de datos.
- Capacidad para ejecutar consultas SQL.

Si las cuatro pruebas finales se ejecutan correctamente, el entorno está listo para comenzar las prácticas del curso de **Bases de Datos**.