# Diferencias de Tipos de Datos en DBMS

| Categoría | MySQL | PostgreSQL | Oracle | SQL Server | SQLite | MariaDB |
|---|---|---|---|---|---|---|
| Entero pequeño | TINYINT | SMALLINT | NUMBER(3) | TINYINT | INTEGER | TINYINT |
| Entero estándar | INT / INTEGER | INTEGER | NUMBER(10) | INT | INTEGER | INT / INTEGER |
| Entero grande | BIGINT | BIGINT | NUMBER(19) | BIGINT | INTEGER | BIGINT |
| Decimal exacto | DECIMAL(p,s) | NUMERIC(p,s) | NUMBER(p,s) | DECIMAL(p,s) | NUMERIC | DECIMAL(p,s) |
| Número flotante | FLOAT / DOUBLE | REAL / DOUBLE PRECISION | BINARY_FLOAT / BINARY_DOUBLE | FLOAT / REAL | REAL | FLOAT / DOUBLE |
| Cadena corta | VARCHAR(n) | VARCHAR(n) | VARCHAR2(n) | VARCHAR(n) | TEXT | VARCHAR(n) |
| Cadena fija | CHAR(n) | CHAR(n) | CHAR(n) | CHAR(n) | TEXT | CHAR(n) |
| Texto largo | TEXT | TEXT | CLOB | TEXT | TEXT | TEXT |
| Fecha | DATE | DATE | DATE | DATE | TEXT / NUMERIC | DATE |
| Fecha y hora | DATETIME / TIMESTAMP | TIMESTAMP | TIMESTAMP | DATETIME / DATETIME2 | TEXT / NUMERIC | DATETIME / TIMESTAMP |
| Hora | TIME | TIME | DATE o INTERVAL | TIME | TEXT | TIME |
| Año | YEAR | No existe directamente | No existe directamente | No existe directamente | No existe directamente | YEAR |
| Booleano | BOOLEAN / TINYINT(1) | BOOLEAN | NUMBER(1) o CHAR(1) | BIT | INTEGER | BOOLEAN |
| Binario | BLOB | BYTEA | BLOB | VARBINARY / IMAGE | BLOB | BLOB |
| JSON | JSON | JSON / JSONB | JSON | JSON | TEXT | JSON |
| XML | No nativo | XML | XMLTYPE | XML | No nativo | No nativo |
| UUID | CHAR(36) | UUID | RAW(16) | UNIQUEIDENTIFIER | TEXT | UUID |
| Auto incremental | AUTO_INCREMENT | SERIAL / IDENTITY | SEQUENCE + TRIGGER / IDENTITY | IDENTITY | AUTOINCREMENT | AUTO_INCREMENT |
| Enumeraciones | ENUM | CREATE TYPE ENUM | No nativo | No nativo | No nativo | ENUM |

---

# Observaciones Importantes

## MySQL

- Muy usado en aplicaciones web.
- Soporta `AUTO_INCREMENT`.
- Tiene tipos `ENUM` y `SET`.
- `BOOLEAN` internamente funciona como `TINYINT(1)`.

---

## PostgreSQL

- Muy estricto y robusto.
- Soporta `JSONB`, uno de los mejores manejos JSON.
- Tiene soporte nativo para `UUID`.
- Permite crear tipos personalizados.

---

## Oracle

- Usa principalmente el tipo `NUMBER`.
- El equivalente de `VARCHAR` es `VARCHAR2`.
- Maneja XML mediante `XMLTYPE`.
- Tradicionalmente usa `SEQUENCE` para autoincrementales.

---

## SQL Server

- Usa `IDENTITY` para autoincrementales.
- Tiene `UNIQUEIDENTIFIER` para UUID.
- Excelente integración empresarial.
- Soporta XML y JSON.

---

## SQLite

- Muy liviano.
- Tiene tipado dinámico.
- No maneja tipos estrictos como otros DBMS.
- Ideal para móviles y aplicaciones pequeñas.

---

## MariaDB

- Compatible con MySQL.
- Mantiene `AUTO_INCREMENT`.
- Incluye mejoras de rendimiento y motores adicionales.
- Compatible con JSON y ENUM.

---

# Ejemplo Comparativo

## Crear un ID autoincremental

### MySQL / MariaDB

```sql
id INT AUTO_INCREMENT PRIMARY KEY