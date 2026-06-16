# Guia Practica: El Misterio de la Integridad Referencial

**Objetivo:** Comprender de forma didactica por que el orden de inserción de datos es crucial en una base de datos relacional y como las Llaves Foraneas (FOREIGN KEY) protegen la logica del negocio ante inserciones, actualizaciones y borrados.

---

## 1. Contexto Real

Imaginen que llega un estudiante a la ventanilla de admisiones de la universidad y dice: 'Quiero matricularme en el Grupo 202601 de la materia Cálculo I'. El sistema de la universidad no puede crear esa matrícula si el estudiante aún no esta registrado con su cédula, o si ese grupo ni siquiera ha sido creado por la facultad.
 
Las bases de datos tienen un guardián para evitar esta información inconsistente: las Llaves Foráneas. En esta práctica vamos a aprender como funcionan experimentando con el error, la propagación y el borrado seguro.

---

## 2. Paso 1: El Experimento del Error (Provocando el Caos)

Con la base de datos university_db totalmente vacía, intentaremos hacer inscribir a un alumno fantasma en una clase que no existe. Ejecutar el siguiente comando:

```sql
USE university_db;

-- Intentando matricular a un estudiante fantasma en una clase inexistente
INSERT INTO enrollments (id_student_enrollment, id_class_enrollment, id_subject_enrollment, date_enrollment, final_grade_enrollments)
VALUES (1012345678, 202601, 1, '2026-06-15', 4.50);

```

### Qué paso en la consola?

MySQL detendra la ejecución de golpe y mostrará el siguiente error:

> **Error Code: 1452.** *Cannot add or update a child row: a foreign key constraint fails (`university_db`.`enrollments`, CONSTRAINT `fk_enrollment_student` FOREIGN KEY (`id_student_enrollment`) REFERENCES `students` (`id_student`))*

### Preguntas de reflexión:

* Por que MySQL rechazo el comando?
* Quien es el estudiante 1012345678? Existe en el sistema?
* **Conclusion:** La tabla enrollments es una tabla hija y no puede inventar dependencias sin que existan sus padres.

---

## 3. Paso 2: Construyendo los Cimientos (Tablas Maestras)

Para solucionar el error, debemos construir los datos desde la base. Las tablas que no dependen de nadie se llaman Tablas Maestras o Independientes. Creamos legalmente al estudiante:

```sql
-- Registramos al estudiante con su ciudad de nacimiento
INSERT INTO students (id_student, name_student, lastname_student, email_student, birthday_student, city_birth_student)
VALUES (1012345678, 'Julian', 'Velres', 'julian.velres1012345678@estudiante.edu.co', '2004-05-20', 'Manizales');

```

> **Pregunta capciosa:** *Si volvemos a intentar la matricula del Paso 1, funcionara?*
> **Respuesta:** No. Aunque el estudiante ya existe, la clase 202601 de la materia 1 todavia es un fantasma en el sistema.

---

## 4. Paso 3: Siguiendo el Hilo de la Dependencia

Para que una clase (classes) pueda existir, requiere un aula, un profesor y una materia. Insertemos estos registros base en estricto orden jerarquico:

```sql
-- 1. Creamos el Aula
INSERT INTO classrooms (id_classroom, capacity_classroom, description_classroom)
VALUES (101, 30, 'Piso 1, Aula 1. Equipada con videobeam y aire acondicionado.');

-- 2. Creamos al Profesor
INSERT INTO teachers (id_teacher, name_teacher, lastname_teacher, email_teacher, specialization_teacher)
VALUES (41987654, 'Carlos', 'Mendoza', 'carlos.mendoza41987654@universidad.edu.co', 'Matematicas Puras');

-- 3. Creamos la Materia
INSERT INTO subjects (id_subject, name_subject, credits_subject)
VALUES (1, 'Calculo Diferencial - Nivel 1', 4);

```

Ahora que los tres padres de la oferta académica existen, abrimos oficialmente la clase:

```sql
-- 4. Creamos la Clase (Vincula materia, profesor y aula)
INSERT INTO classes (id_class, id_subject_class, id_teacher_class, id_classroom_class, semester_class)
VALUES (202601, 1, 41987654, 101, '2026-1');

```

---

## 5. Paso 4: La Victoria de la Integridad (Cierre del Ciclo)

Ahora que el estudiante real (1012345678) y la clase real (202601 de la materia 1) existen en la base de datos, volvamos a intentar la matricula:

```sql
-- Intentamos la matricula de nuevo
INSERT INTO enrollments (id_student_enrollment, id_class_enrollment, id_subject_enrollment, date_enrollment, final_grade_enrollments)
VALUES (1012345678, 202601, 1, '2026-06-15', 4.50);

```

### Que pasé en la consola?

> **Response:** *1 row(s) affected.* Éxito rotundo. Los datos ahora son consistentes.

---

## 6. Paso 5: El Efecto Domino con UPDATE

> **Caso de estudio:** *La Registraduria Nacional cometio un error en la cedula del estudiante Julian Velres. Su cédula real no termina en 78, sino en 99. Si cambiamos su cedula en la tabla maestra students, que pasara con su matricula en enrollments?*

Ejecuten el cambio en la tabla maestra:

```sql
UPDATE students 
SET id_student = 1012345699 
WHERE id_student = 1012345678;

```

Ahora, verificar de inmediato la tabla hija sin haber hecho cambios manuales en ella:

```sql
SELECT * FROM enrollments;

```

### Qué se descubrió?

El campo id_student_enrollment cambió automaticamente a 1012345699. Esto se debe a la regla **ON UPDATE CASCADE** definida en el DDL, la cual propaga las modificaciones del padre hacia los hijos para no romper la relación.

---

## 7. Paso 6: El Peligro del DELETE (CASCADE)

> **Caso de estudio:** *El estudiante decide retirarse permanentemente de la universidad. Procederemos a borrarlo de la tabla students. Que pasara con su registro de matrícula y su nota de 4.50?*

Ejecuten el borrado en la tabla maestra:

```sql
DELETE FROM students 
WHERE id_student = 1012345699;

```

Revisen de nuevo la tabla intermedia de matriculas:

```sql
SELECT * FROM enrollments;

```

### Que descubrieron?

La tabla enrollments quedo completamente vacía. Esto ocurre por el **ON DELETE CASCADE**. Al eliminar al padre, se eliminan automaticamente todos sus registros asociados en cascada.

> **Advertencia profesional:** El borrado en cascada es una herramienta potente pero peligrosa; un DELETE mal enfocado en producción puede destruir millones de filas de datos históricos en un instante.

---

## 8. Paso 7: El Borrado Seguro (SET NULL)

Hay ocasiones donde no queremos destruir los datos de la tabla hija cuando el padre desaparece.

> **Caso de estudio:** *El profesor Carlos Mendoza renuncia a la universidad. Si lo borramos, deberián borrarse también todas las clases que él dictaba, dejando a los estudiantes sin materias asignadas?*

Primero, verifiquemos que el profesor esta asignado a su clase en la tabla classes:

```sql
SELECT * FROM classes;

```

Ahora, eliminen al profesor de la tabla maestra teachers:

```sql
DELETE FROM teachers 
WHERE id_teacher = 41987654;

```

Revisen de inmediato la tabla classes:

```sql
SELECT * FROM classes;

```

### Qué se descubrió?

La clase del grupo 202601 **sigue existiendo**, pero la columna del profesor (id_teacher_class) cambio automáticamente a **NULL**. Esto se debe a la regla **ON DELETE SET NULL**: el profesor se retira, pero la clase se preserva vacia en espera de que se asigne un nuevo docente.

---

## 9. Reglas de Oro

1. **Jerarquia:** No se pueden cargar datos en tablas hijas si sus llaves referenciales no existen primero en las tablas maestras.
2. **El Orden de Carga Masiva:** Para migrar o importar archivos planos (CSV) o insertar datos manuales, el orden logico estricto de este sistema debe ser:

$$Students / Classrooms / Teachers / Subjects \longrightarrow Classes \longrightarrow Enrollments$$


3. **Mantenimiento Relacional:**
* ON UPDATE CASCADE: protege los datos relacionales si las llaves naturales cambian.
* ON DELETE CASCADE: borra en cadena de forma automatizada.
* ON DELETE SET NULL: desvincula de forma segura sin destruir la estructura hija.
