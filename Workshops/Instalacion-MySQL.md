# Instalación de MySQL Server y MySQL Workbench

## Objetivo

Instalar MySQL Server y MySQL Workbench en Windows y macOS para desarrollar las prácticas del curso.

---

# Requisitos

- Windows 10 o superior
- macOS 13 o superior
- Conexión a Internet
- Permisos de administrador

---

# Instalación en Windows

## Paso 1. Descargar MySQL

Ingresar a:

https://dev.mysql.com/downloads/

Seleccionar:

- MySQL Installer for Windows

---

## Paso 2. Ejecutar instalador

Abrir:

mysql-installer-community-x.x.x.msi 

---

## Paso 3. Tipo de instalación

Seleccionar:

Developer Default 

Incluye:

- MySQL Server
- MySQL Workbench
- MySQL Shell
- Connectors

---

## Paso 4. Instalar componentes

Presionar:

Execute 

---

## Paso 5. Configurar servidor

Seleccionar:

Standalone MySQL Server 

---

## Paso 6. Puerto

Dejar:

3306 

---

## Paso 7. Usuario administrador

Usuario:

root 

Contraseña sugerida:

Admin12345 

---

## Paso 8. Finalizar instalación

Presionar:

Execute Finish 

---

# Verificación en Windows

Abrir CMD:

cmd:

mysql --version 

Resultado esperado:

mysql Ver 9.x.x 

---

# Instalación en macOS

## Paso 1. Descargar MySQL

Ingresar a:

https://dev.mysql.com/downloads/mysql/

Seleccionar:

macOS 

---

## Paso 2. Instalar paquete

Abrir:

mysql-x.x.x-macos.pkg 

Seguir asistente:

Continue Continue Agree Install 

---

## Paso 3. Configurar contraseña root

Ejemplo:

Admin12345 

---

## Paso 4. Instalar Preference Pane

Permite iniciar y detener MySQL desde Configuración del Sistema.

---

# Verificación en macOS

Abrir Terminal:

bash:

/usr/local/mysql/bin/mysql --version 

Resultado esperado:

mysql Ver 9.x.x 

---

# Instalación de MySQL Workbench

## Windows

Instalado automáticamente con Developer Default.

---

## macOS

Descargar desde:

https://dev.mysql.com/downloads/workbench/

Abrir:

mysql-workbench-community.dmg 

Arrastrar:

MySQL Workbench 

hacia:

Applications 

---

# Resultado Esperado

- Abrir MySQL Workbench
- Conectarse como root
- Ejecutar consultas SQL