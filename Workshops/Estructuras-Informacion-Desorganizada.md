# Actividad Práctica 1
# Análisis de problemas de información en estructuras desorganizadas

## Integrantes
Grupo de 3 estudiantes

---

# Objetivo

Analizar estructuras de información desorganizadas e identificar problemas relacionados con redundancia, inconsistencias y dificultad de mantenimiento de datos.

---

# Instrucciones

Cada grupo debe analizar la tabla asignada e identificar:

1. Información repetida
2. Posibles inconsistencias
3. Problemas de actualización
4. Problemas de eliminación de registros
5. Problemas de búsqueda de información
6. Posibles errores humanos
7. Ventajas que tendría una base de datos relacional frente a esta estructura

---

# Entregable

El grupo debe entregar:

- respuestas del análisis,
- problemas identificados,
- conclusiones generales.

---

# Tabla Grupo 1 — Tienda Tecnológica

| Cliente | Teléfono | Ciudad | Producto | Precio | Pedido |
|---|---|---|---|---|---|
| Ana López | 3001111111 | Bogotá | Mouse | 50000 | P001 |
| Ana López | 3001111111 | Bogotá | Teclado | 80000 | P002 |
| Carlos Ruiz | 3012222222 | Medellín | Monitor | 700000 | P003 |
| Laura Díaz | 3023333333 | Cali | Portátil | 2500000 | P004 |
| Carlos Ruiz | 3012222222 | Medellín | Mouse | 50000 | P005 |
| Juan Pérez | 3034444444 | Bogotá | Impresora | 450000 | P006 |
| Juan Pérez | 3034444444 | Bogota | Cámara | 600000 | P007 |
| Sofía Torres | 3045555555 | Pereira | Disco SSD | 320000 | P008 |
| Andrés Mora | 3056666666 | Cali | Router | 180000 | P009 |
| Andrés Mora | 3056666666 | Cali | Monitor | 700000 | P010 |
| Paula Gómez | 3067777777 | Medellín | Teclado | 80000 | P011 |
| Paula Gómez | 3067777777 | Medellin | Mouse | 50000 | P012 |
| Camilo Vega | 3078888888 | Bogotá | Webcam | 250000 | P013 |
| Lina Castro | 3089999999 | Bucaramanga | Audífonos | 120000 | P014 |
| Lina Castro | 3089999999 | Bucaramanga | Micrófono | 350000 | P015 |
| Felipe Rojas | 3091010101 | Cali | Tablet | 1200000 | P016 |
| Felipe Rojas | 3091010101 | Cali | Router | 180000 | P017 |
| Diana León | 3102020202 | Pereira | Disco SSD | 320000 | P018 |
| Diana León | 3102020202 | Pereira | Mouse | 50000 | P019 |
| Mateo Gil | 3113030303 | Bogotá | Portátil | 2500000 | P020 |

---

# Tabla Grupo 2 — Clínica Veterinaria

| Dueño | Teléfono | Ciudad | Mascota | Veterinario | Consulta |
|---|---|---|---|---|---|
| María Torres | 3005551111 | Bogotá | Max | Dr. Pérez | C001 |
| María Torres | 3005551111 | Bogotá | Luna | Dr. Gómez | C002 |
| Andrés Silva | 3016662222 | Medellín | Rocky | Dr. Pérez | C003 |
| Camila Díaz | 3027773333 | Cali | Toby | Dra. Ruiz | C004 |
| Andrés Silva | 3016662222 | Medellin | Rocky | Dr. Gómez | C005 |
| Juan Herrera | 3038884444 | Bogotá | Simón | Dra. Ruiz | C006 |
| Laura Castro | 3049995555 | Pereira | Nina | Dr. Pérez | C007 |
| Laura Castro | 3049995555 | Pereira | Nina | Dr. Pérez | C008 |
| Felipe León | 3051010101 | Cali | Bruno | Dra. Ruiz | C009 |
| Felipe León | 3051010101 | Cali | Bruno | Dr. Gómez | C010 |
| Sara Gómez | 3062020202 | Medellín | Max | Dr. Pérez | C011 |
| Sara Gómez | 3062020202 | Medellín | Luna | Dra. Ruiz | C012 |
| Diego Ruiz | 3073030303 | Bogotá | Toby | Dr. Pérez | C013 |
| Diego Ruiz | 3073030303 | Bogota | Rocky | Dr. Gómez | C014 |
| Valeria Mora | 3084040404 | Cali | Nina | Dra. Ruiz | C015 |
| Valeria Mora | 3084040404 | Cali | Max | Dr. Pérez | C016 |
| Nicolás Gil | 3095050505 | Pereira | Bruno | Dr. Gómez | C017 |
| Nicolás Gil | 3095050505 | Pereira | Simón | Dra. Ruiz | C018 |
| Paula Vega | 3106060606 | Medellín | Toby | Dr. Pérez | C019 |
| Paula Vega | 3106060606 | Medellín | Luna | Dr. Gómez | C020 |

---

# Tabla Grupo 3 — Universidad

| Estudiante | Teléfono | Ciudad | Curso | Docente | Matrícula |
|---|---|---|---|---|---|
| Ana Pérez | 3001001001 | Bogotá | Bases de Datos | Carlos Gómez | M001 |
| Ana Pérez | 3001001001 | Bogotá | Programación | Laura Díaz | M002 |
| Luis Herrera | 3012002002 | Medellín | Redes | Juan Ruiz | M003 |
| Camila Torres | 3023003003 | Cali | Bases de Datos | Carlos Gómez | M004 |
| Luis Herrera | 3012002002 | Medellin | Programación | Laura Díaz | M005 |
| Felipe Castro | 3034004004 | Bogotá | Sistemas Operativos | Marta León | M006 |
| Sofía Gil | 3045005005 | Pereira | Redes | Juan Ruiz | M007 |
| Sofía Gil | 3045005005 | Pereira | Programación | Laura Díaz | M008 |
| Mateo Vega | 3056006006 | Cali | Bases de Datos | Carlos Gómez | M009 |
| Mateo Vega | 3056006006 | Cali | Redes | Juan Ruiz | M010 |
| Paula Díaz | 3067007007 | Medellín | Programación | Laura Díaz | M011 |
| Paula Díaz | 3067007007 | Medellin | Bases de Datos | Carlos Gómez | M012 |
| Andrés Mora | 3078008008 | Bogotá | Redes | Juan Ruiz | M013 |
| Andrés Mora | 3078008008 | Bogotá | Sistemas Operativos | Marta León | M014 |
| Lina Ruiz | 3089009009 | Cali | Programación | Laura Díaz | M015 |
| Lina Ruiz | 3089009009 | Cali | Bases de Datos | Carlos Gómez | M016 |
| Carlos León | 3091111111 | Pereira | Redes | Juan Ruiz | M017 |
| Carlos León | 3091111111 | Pereira | Sistemas Operativos | Marta León | M018 |
| Diana Gómez | 3102222222 | Medellín | Bases de Datos | Carlos Gómez | M019 |
| Diana Gómez | 3102222222 | Medellín | Redes | Juan Ruiz | M020 |

---

# Tabla Grupo 4 — Hospital

| Paciente | Teléfono | Ciudad | Médico | Especialidad | Cita |
|---|---|---|---|---|---|
| Laura Pérez | 3001110001 | Bogotá | Dr. Ruiz | Cardiología | H001 |
| Laura Pérez | 3001110001 | Bogotá | Dra. León | Pediatría | H002 |
| Juan Gómez | 3012220002 | Medellín | Dr. Ruiz | Cardiología | H003 |
| Camila Díaz | 3023330003 | Cali | Dr. Castro | Dermatología | H004 |
| Juan Gómez | 3012220002 | Medellin | Dra. León | Pediatría | H005 |
| Andrés Torres | 3034440004 | Bogotá | Dr. Ruiz | Cardiología | H006 |
| Paula Gil | 3045550005 | Pereira | Dr. Castro | Dermatología | H007 |
| Paula Gil | 3045550005 | Pereira | Dra. León | Pediatría | H008 |
| Felipe Mora | 3056660006 | Cali | Dr. Ruiz | Cardiología | H009 |
| Felipe Mora | 3056660006 | Cali | Dr. Castro | Dermatología | H010 |
| Sara Vega | 3067770007 | Medellín | Dra. León | Pediatría | H011 |
| Sara Vega | 3067770007 | Medellín | Dr. Ruiz | Cardiología | H012 |
| Mateo León | 3078880008 | Bogotá | Dr. Castro | Dermatología | H013 |
| Mateo León | 3078880008 | Bogota | Dra. León | Pediatría | H014 |
| Lina Castro | 3089990009 | Cali | Dr. Ruiz | Cardiología | H015 |
| Lina Castro | 3089990009 | Cali | Dr. Castro | Dermatología | H016 |
| Carlos Díaz | 3091010001 | Pereira | Dra. León | Pediatría | H017 |
| Carlos Díaz | 3091010001 | Pereira | Dr. Ruiz | Cardiología | H018 |
| Diana Ruiz | 3102020002 | Medellín | Dr. Castro | Dermatología | H019 |
| Diana Ruiz | 3102020002 | Medellín | Dra. León | Pediatría | H020 |

---

# Tabla Grupo 5 — Plataforma de Streaming

| Usuario | Teléfono | Ciudad | Película | Género | Visualización |
|---|---|---|---|---|---|
| Ana Torres | 3005000001 | Bogotá | Inception | Ciencia Ficción | V001 |
| Ana Torres | 3005000001 | Bogotá | Titanic | Drama | V002 |
| Luis Gómez | 3016000002 | Medellín | Matrix | Acción | V003 |
| Camila Ruiz | 3027000003 | Cali | Coco | Animación | V004 |
| Luis Gómez | 3016000002 | Medellin | Titanic | Drama | V005 |
| Felipe Castro | 3038000004 | Bogotá | Avatar | Ciencia Ficción | V006 |
| Sofía Díaz | 3049000005 | Pereira | Matrix | Acción | V007 |
| Sofía Díaz | 3049000005 | Pereira | Coco | Animación | V008 |
| Mateo León | 3051010006 | Cali | Inception | Ciencia Ficción | V009 |
| Mateo León | 3051010006 | Cali | Avatar | Ciencia Ficción | V010 |
| Paula Vega | 3062020007 | Medellín | Titanic | Drama | V011 |
| Paula Vega | 3062020007 | Medellin | Coco | Animación | V012 |
| Andrés Mora | 3073030008 | Bogotá | Matrix | Acción | V013 |
| Andrés Mora | 3073030008 | Bogotá | Avatar | Ciencia Ficción | V014 |
| Lina Gil | 3084040009 | Cali | Titanic | Drama | V015 |
| Lina Gil | 3084040009 | Cali | Inception | Ciencia Ficción | V016 |
| Carlos Ruiz | 3095050010 | Pereira | Coco | Animación | V017 |
| Carlos Ruiz | 3095050010 | Pereira | Matrix | Acción | V018 |
| Diana León | 3106060011 | Medellín | Avatar | Ciencia Ficción | V019 |
| Diana León | 3106060011 | Medellín | Titanic | Drama | V020 |