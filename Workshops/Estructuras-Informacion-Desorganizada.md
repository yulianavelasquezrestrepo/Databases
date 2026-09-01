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

---

# Tabla Grupo 6 — Restaurante

| Cliente       | Teléfono   | Ciudad      | Plato        | Precio | Pedido |
|---------------|------------|-------------|--------------|--------|--------|
| Natalia Gómez | 3001112221 | Bogotá      | Hamburguesa  | 28000  | R001   |
| Natalia Gómez | 3001112221 | Bogotá      | Pizza        | 35000  | R002   |
| Andrés Pérez  | 3012223332 | Medellín    | Pasta        | 32000  | R003   |
| Laura Torres  | 3023334443 | Cali        | Hamburguesa  | 28000  | R004   |
| Andrés Pérez  | 3012223332 | Medellin    | Pizza        | 35000  | R005   |
| Carlos Díaz   | 3034445554 | Bogotá      | Ensalada     | 22000  | R006   |
| Carlos Díaz   | 3034445554 | Bogota      | Jugo Natural | 12000  | R007   |
| Sofía Castro  | 3045556665 | Pereira     | Pasta        | 32000  | R008   |
| Mateo Ruiz    | 3056667776 | Cali        | Pizza        | 35000  | R009   |
| Mateo Ruiz    | 3056667776 | Cali        | Hamburguesa  | 28000  | R010   |
| Paula León    | 3067778887 | Medellín    | Ensalada     | 22000  | R011   |
| Paula León    | 3067778887 | Medellin    | Pasta        | 32000  | R012   |
| Felipe Mora   | 3078889998 | Bogotá      | Pizza        | 35000  | R013   |
| Lina Vega     | 3089991119 | Bucaramanga | Hamburguesa  | 28000  | R014   |
| Lina Vega     | 3089991119 | Bucaramanga | Jugo Natural | 12000  | R015   |
| Daniel Gil    | 3091012120 | Cali        | Pasta        | 32000  | R016   |
| Daniel Gil    | 3091012120 | Cali        | Ensalada     | 22000  | R017   |
| Valeria Rojas | 3102023231 | Pereira     | Pizza        | 35000  | R018   |
| Valeria Rojas | 3102023231 | Pereira     | Hamburguesa  | 28000  | R019   |
| Nicolás Silva | 3113034342 | Bogotá      | Jugo Natural | 12000  | R020   |

---

# Tabla Grupo 7 — Hotel

| Huésped      | Teléfono   | Ciudad   | Habitación | Tipo Habitación | Reserva |
|--------------|------------|----------|------------|-----------------|---------|
| María López  | 3004441111 | Bogotá   | 101        | Sencilla        | H001    |
| María López  | 3004441111 | Bogotá   | 102        | Doble           | H002    |
| Juan Torres  | 3015552222 | Medellín | 201        | Doble           | H003    |
| Camila Pérez | 3026663333 | Cali     | 301        | Suite           | H004    |
| Juan Torres  | 3015552222 | Medellin | 202        | Doble           | H005    |
| Andrés Gómez | 3037774444 | Bogotá   | 103        | Sencilla        | H006    |
| Andrés Gómez | 3037774444 | Bogotá   | 104        | Sencilla        | H007    |
| Laura Díaz   | 3048885555 | Pereira  | 302        | Suite           | H008    |
| Felipe Ruiz  | 3059996666 | Cali     | 203        | Doble           | H009    |
| Felipe Ruiz  | 3059996666 | Cali     | 204        | Doble           | H010    |
| Sofía Castro | 3061017777 | Medellín | 105        | Sencilla        | H011    |
| Sofía Castro | 3061017777 | Medellin | 303        | Suite           | H012    |
| Mateo León   | 3072028888 | Bogotá   | 205        | Doble           | H013    |
| Mateo León   | 3072028888 | Bogota   | 106        | Sencilla        | H014    |
| Paula Mora   | 3083039999 | Cali     | 304        | Suite           | H015    |
| Paula Mora   | 3083039999 | Cali     | 206        | Doble           | H016    |
| Carlos Vega  | 3094041010 | Pereira  | 107        | Sencilla        | H017    |
| Carlos Vega  | 3094041010 | Pereira  | 207        | Doble           | H018    |
| Diana Gil    | 3105052021 | Medellín | 305        | Suite           | H019    |
| Diana Gil    | 3105052021 | Medellín | 108        | Sencilla        | H020    |

---

# Tabla Grupo 8 — Gimnasio

| Cliente       | Teléfono   | Ciudad   | Plan    | Entrenador  | Inscripción |
|---------------|------------|----------|---------|-------------|-------------|
| Ana Martínez  | 3001113331 | Bogotá   | Básico  | Carlos Ruiz | G001        |
| Ana Martínez  | 3001113331 | Bogotá   | Premium | Laura Gómez | G002        |
| Luis Pérez    | 3012224442 | Medellín | Básico  | Carlos Ruiz | G003        |
| Camila Torres | 3023335553 | Cali     | Premium | Diana León  | G004        |
| Luis Pérez    | 3012224442 | Medellin | Básico  | Laura Gómez | G005        |
| Felipe Díaz   | 3034446664 | Bogotá   | Básico  | Carlos Ruiz | G006        |
| Felipe Díaz   | 3034446664 | Bogotá   | Premium | Diana León  | G007        |
| Sofía Castro  | 3045557775 | Pereira  | Premium | Laura Gómez | G008        |
| Mateo Ruiz    | 3056668886 | Cali     | Básico  | Carlos Ruiz | G009        |
| Mateo Ruiz    | 3056668886 | Cali     | Premium | Diana León  | G010        |
| Paula Gómez   | 3067779997 | Medellín | Básico  | Laura Gómez | G011        |
| Paula Gómez   | 3067779997 | Medellin | Premium | Carlos Ruiz | G012        |
| Andrés León   | 3078881118 | Bogotá   | Premium | Diana León  | G013        |
| Andrés León   | 3078881118 | Bogota   | Básico  | Carlos Ruiz | G014        |
| Lina Mora     | 3089992229 | Cali     | Básico  | Laura Gómez | G015        |
| Lina Mora     | 3089992229 | Cali     | Premium | Diana León  | G016        |
| Carlos Vega   | 3091013330 | Pereira  | Básico  | Carlos Ruiz | G017        |
| Carlos Vega   | 3091013330 | Pereira  | Premium | Laura Gómez | G018        |
| Diana Rojas   | 3102024441 | Medellín | Premium | Diana León  | G019        |
| Diana Rojas   | 3102024441 | Medellín | Básico  | Carlos Ruiz | G020        |
