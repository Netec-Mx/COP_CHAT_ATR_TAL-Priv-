---LAB_START---
LAB_ID: 02-00-01
---MARKDOWN---
# Práctica 2 — Simulación de Screening Curricular y Creación de Scorecards de Selección

---

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Aplicar (*Apply*) |
| **Módulo** | Módulo 2 — Atracción y Selección de Talento con Copilot |
| **Práctica anterior requerida** | Lab 01 — Diseño de Descriptivo de Puesto con Copilot |
| **Tecnologías principales** | Microsoft 365 Copilot Chat · Copilot en Excel · Copilot en Word · OneDrive for Business |

---

## 2. Descripción General

En esta práctica aplicarás directamente los conceptos de análisis multidimensional y filtrado asistido por IA estudiados en la Lección 2.1. Trabajarás con un conjunto de cuatro CVs ficticios para simular un proceso real de screening curricular, construyendo prompts estructurados que permitan a Copilot evaluar candidatos desde las dimensiones técnica, conductual, de potencial y cultural. Posteriormente, trasladarás esos resultados a un scorecard ponderado en Excel y generarás un banco de preguntas de entrevista por competencias exportable a Word.

La práctica está dividida en dos bloques: **Bloque A — Screening Curricular** (≈ 45 min) y **Bloque B — Scorecard de Selección y Banco de Preguntas** (≈ 45 min).

> ⚠️ **Aviso de privacidad:** Todos los CVs utilizados en esta práctica son completamente ficticios. No ingreses datos personales reales de ningún colaborador o candidato en Copilot Chat bajo ninguna circunstancia.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio, serás capaz de:

- [ ] Construir prompts de análisis multidimensional en Copilot Chat para filtrar y comparar CVs ficticios frente a un descriptivo de puesto, aplicando criterios ponderados de evaluación.
- [ ] Crear un scorecard de selección en Microsoft Excel con Copilot, incluyendo criterios ponderados, escalas de puntuación, fórmulas automáticas y visualización gráfica comparativa.
- [ ] Generar un banco de al menos 15 preguntas de entrevista por competencias (conductuales, técnicas y situacionales) con criterios de evaluación de respuesta, utilizando Copilot Chat y exportándolas a Word.
- [ ] Identificar fortalezas, brechas y recomendaciones de avance para cada candidato ficticio, documentando el razonamiento detrás de cada decisión de selección.

---

## 4. Prerrequisitos

### Conocimiento previo

| Requisito | Nivel esperado |
|---|---|
| Haber completado Lab 01 (Descriptivo de Puesto) | Obligatorio |
| Familiaridad con tablas de Excel y fórmulas básicas (`SUMA`, `PROMEDIO`) | Básico |
| Haber leído la Lección 2.1 (Filtrado de CVs y Análisis Multidimensional) | Obligatorio |
| Comprensión del modelo de prompt: Contexto + Criterios + Formato de salida | Básico |

### Acceso y licencias

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 (no cuenta personal) | ✅ Activa |
| Licencia Microsoft 365 Copilot (complemento) asignada | ✅ Confirmada con TI |
| Microsoft Excel (versión 2401 o superior) con Copilot habilitado | ✅ Instalado |
| Microsoft Word (versión 2401 o superior) | ✅ Instalado |
| OneDrive for Business sincronizado | ✅ Activo |
| Archivos de práctica descargados en carpeta `Copilot-RH-Labs` en OneDrive | ✅ Disponibles |
| Descriptivo de puesto de Lab 01 guardado en OneDrive | ✅ Guardado |

> 🔒 **Modo seguro:** Antes de comenzar, verifica que el ícono de escudo/protección esté visible en la interfaz de Copilot Chat. Esto confirma que las conversaciones permanecen dentro del tenant corporativo.

---

## 5. Entorno de Laboratorio

### Hardware mínimo recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 / AMD Ryzen 5 (8ª gen) | i7 / Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px |
| Almacenamiento libre | 5 GB | 10 GB |
| Conexión a internet | 10 Mbps bajada / 5 Mbps subida | 25 Mbps |

### Software requerido

| Aplicación | Versión mínima | Notas |
|---|---|---|
| Microsoft 365 Copilot Chat | Vigente (M365 E3/E5 + complemento) | Acceder en [microsoft365.com/copilot](https://microsoft365.com/copilot) |
| Microsoft Excel | Microsoft 365 Apps v2401+ | Copilot requiere datos en formato **Tabla** |
| Microsoft Word | Microsoft 365 Apps v2401+ | Para exportar banco de preguntas |
| Microsoft Edge | Versión 120+ | Navegador recomendado |
| OneDrive for Business | Cliente sincronizado | Para guardar y acceder a archivos |

### Configuración inicial del entorno

Ejecuta los siguientes pasos antes de iniciar el Bloque A:

**Paso 0.1 — Verificar estructura de carpetas en OneDrive**

1. Abre el Explorador de archivos (Windows) o Finder (Mac).
2. Navega a tu carpeta de OneDrive for Business.
3. Confirma que existe la carpeta `Copilot-RH-Labs` con la siguiente estructura:

```
Copilot-RH-Labs/
├── Practica-01/
│   └── Descriptivo-Puesto-[TuNombre].docx   ← del Lab 01
├── Practica-02/
│   ├── CV-Candidato-01-Ana-Torres.docx
│   ├── CV-Candidato-02-Roberto-Mendez.docx
│   ├── CV-Candidato-03-Sofia-Rios.docx
│   └── CV-Candidato-04-Carlos-Vega.docx
```

4. Si la carpeta `Practica-02` no existe, créala y descarga los archivos de CVs ficticios desde el repositorio del curso.

**Paso 0.2 — Abrir Copilot Chat con cuenta corporativa**

1. Abre Microsoft Edge.
2. Navega a `https://microsoft365.com/copilot` o abre la aplicación **Microsoft 365 Copilot** desde el menú de aplicaciones.
3. Inicia sesión con tu cuenta corporativa (formato: `nombre@empresa.com`). **No uses una cuenta personal de Microsoft.**
4. Verifica que el **ícono de escudo/protección** sea visible en la parte superior de la interfaz de Copilot Chat. Si no aparece, detente y contacta al instructor.

**Paso 0.3 — Abrir los archivos de CVs**

1. Abre los cuatro archivos `.docx` de CVs ficticios desde la carpeta `Practica-02` en OneDrive.
2. Mantén los documentos abiertos en Word o en el navegador para copiar el texto en los pasos posteriores.
3. Abre también el descriptivo de puesto creado en Lab 01.

---

## 6. Instrucciones Paso a Paso

---

### 🔵 BLOQUE A — Screening Curricular Asistido por Copilot (≈ 45 minutos)

---

### Paso A1 — Preparar el Contexto del Puesto para Copilot

**Objetivo:** Extraer del descriptivo de puesto (Lab 01) los elementos clave que servirán como base para todos los prompts de screening del Bloque A.

#### Instrucciones

1. Abre el descriptivo de puesto que creaste en Lab 01 (`Descriptivo-Puesto-[TuNombre].docx`).

2. Identifica y copia los siguientes elementos en un documento de texto o bloc de notas temporal:
   - **Nombre del puesto**
   - **Área / Departamento**
   - **Nivel de experiencia requerido**
   - **Requisitos obligatorios** (mínimo 4 ítems: formación académica, experiencia, herramientas/sistemas, competencias técnicas clave)
   - **Requisitos deseables** (mínimo 3 ítems)
   - **Competencias conductuales clave** (mínimo 3)

3. Organiza esta información en el siguiente formato de referencia (adapta los valores al puesto que definiste en Lab 01):

```text
PUESTO: [Nombre del puesto, ej. Analista de Compensaciones Sr.]
ÁREA: [Área, ej. Recursos Humanos — Compensaciones y Beneficios]
NIVEL: [Nivel, ej. Semisenior — 3 a 5 años de experiencia]

REQUISITOS OBLIGATORIOS:
- [Formación: ej. Licenciatura en Administración, Psicología, Contaduría o afín]
- [Experiencia: ej. Mínimo 3 años en puestos de compensaciones o nómina]
- [Herramienta 1: ej. Dominio de Excel avanzado (tablas dinámicas, VLOOKUP, macros básicas)]
- [Herramienta 2: ej. Experiencia con sistemas HRIS (SAP HCM, Workday o similar)]

REQUISITOS DESEABLES:
- [ej. Certificación en compensaciones (CCP o equivalente)]
- [ej. Inglés intermedio (lectura de documentación técnica)]
- [ej. Conocimiento de encuestas salariales (Mercer, Hay Group)]

COMPETENCIAS CONDUCTUALES:
- [ej. Orientación al detalle y precisión analítica]
- [ej. Comunicación efectiva con áreas de negocio]
- [ej. Manejo de información confidencial con discreción]
```

> 💡 **Nota pedagógica:** Este paso replica el componente "Contexto del puesto" del modelo de prompt de tres elementos estudiado en la Lección 2.1. La calidad de este contexto determinará directamente la precisión del análisis de Copilot.

#### Resultado esperado
Un bloque de texto estructurado con el perfil del puesto, listo para ser insertado en los prompts de los pasos siguientes. Guarda este texto en un archivo temporal llamado `Contexto-Puesto-A1.txt` dentro de la carpeta `Practica-02`.

#### Verificación
✅ El bloque de texto contiene al menos 4 requisitos obligatorios, 3 deseables y 3 competencias conductuales.
✅ La información proviene directamente del descriptivo de puesto de Lab 01, no de fuentes externas.

---

### Paso A2 — Primer Screening: Análisis Rápido de los 4 CVs

**Objetivo:** Usar Copilot Chat para realizar un filtrado inicial de los cuatro CVs ficticios, generando una tabla comparativa que identifique qué candidatos cumplen los requisitos mínimos.

#### Instrucciones

1. Ve a la ventana de **Copilot Chat** (abierta en el Paso 0.2).

2. Abre el archivo `CV-Candidato-01-Ana-Torres.docx` y **copia todo el texto** del CV.

3. Repite el proceso para los otros tres CVs y ten el texto de los cuatro disponible.

4. En Copilot Chat, escribe el siguiente prompt. **Sustituye los campos entre corchetes con la información de tu puesto (del Paso A1) y pega el texto de los cuatro CVs en los espacios indicados:**

```text
Actúa como un especialista senior en selección de talento con experiencia en evaluación de perfiles para el área de Recursos Humanos.

Voy a proporcionarte el perfil del puesto y los CVs de 4 candidatos ficticios. Tu tarea es realizar un filtrado inicial estructurado.

=== PERFIL DEL PUESTO ===
[Pega aquí el bloque de texto del Paso A1]

=== CV CANDIDATO 1 — ANA TORRES ===
[Pega aquí el texto completo del CV de Ana Torres]

=== CV CANDIDATO 2 — ROBERTO MÉNDEZ ===
[Pega aquí el texto completo del CV de Roberto Méndez]

=== CV CANDIDATO 3 — SOFÍA RÍOS ===
[Pega aquí el texto completo del CV de Sofía Ríos]

=== CV CANDIDATO 4 — CARLOS VEGA ===
[Pega aquí el texto completo del CV de Carlos Vega]

=== INSTRUCCIONES DE ANÁLISIS ===
Para cada candidato, genera una tabla con las siguientes columnas:
1. Nombre del candidato
2. Cumple requisitos obligatorios (Sí / Parcial / No)
3. Número de requisitos deseables que cumple (X de 3)
4. Competencias conductuales evidenciadas en el CV
5. Principal fortaleza
6. Principal brecha frente al puesto
7. Recomendación de avance (Avanzar / Revisar / Descartar)

Al final de la tabla, escribe un párrafo ejecutivo de máximo 100 palabras resumiendo tu recomendación de los candidatos prioritarios para avanzar a la siguiente etapa.
```

5. Envía el prompt y espera la respuesta de Copilot.

6. **Lee cuidadosamente la tabla generada.** Si alguna columna está incompleta o la recomendación no está justificada, usa el siguiente prompt de refinamiento:

```text
Para el candidato [nombre], la columna de "Competencias conductuales evidenciadas" está vacía.
Por favor, revisa el CV de ese candidato y extrae al menos 2 evidencias conductuales
(logros en equipo, situaciones de liderazgo, manejo de conflictos, etc.) que aparezcan
en el texto. Si no hay evidencia explícita, indícalo claramente como "No evidenciado en CV".
```

7. Copia la tabla y el párrafo ejecutivo final. Pégalos en un nuevo documento de Word llamado `Screening-Comparativo-A2.docx` y guárdalo en `Copilot-RH-Labs/Practica-02/`.

#### Resultado esperado
Una tabla con los 4 candidatos evaluados en 7 dimensiones, más un párrafo ejecutivo de recomendación. La tabla debe mostrar diferencias claras entre candidatos (no todos deben tener la misma recomendación).

#### Verificación
✅ La tabla contiene las 7 columnas solicitadas para los 4 candidatos.
✅ Al menos un candidato tiene recomendación "Descartar" y al menos uno tiene "Avanzar".
✅ El párrafo ejecutivo menciona criterios específicos del puesto (no es genérico).
✅ El archivo `Screening-Comparativo-A2.docx` está guardado en OneDrive.

---

### Paso A3 — Análisis Multidimensional de los Candidatos Finalistas

**Objetivo:** Aplicar el modelo de análisis multidimensional de cuatro dimensiones (técnica, conductual, potencial, cultural) a los candidatos recomendados para "Avanzar" o "Revisar" en el paso anterior.

#### Instrucciones

1. Identifica los candidatos con recomendación **"Avanzar"** o **"Revisar"** de la tabla del Paso A2 (normalmente 2 o 3 candidatos).

2. En Copilot Chat, inicia una **nueva conversación** (haz clic en "Nueva conversación" o el ícono de lápiz/más) para evitar que el contexto anterior interfiera.

3. Para **cada candidato finalista**, envía el siguiente prompt de análisis multidimensional (un prompt por candidato):

```text
Actúa como un consultor de selección de talento especializado en evaluación por competencias.

Analiza el siguiente CV desde cuatro dimensiones de evaluación. Para cada dimensión:
- Asigna una puntuación del 1 al 5 (1 = muy por debajo del perfil; 5 = supera el perfil)
- Justifica la puntuación con 2-3 evidencias concretas del CV
- Identifica la principal brecha (si existe)

=== DIMENSIONES Y PESOS ===
1. Técnica (peso: 40%) — Conocimientos, herramientas, certificaciones, logros cuantificables
2. Conductual (peso: 30%) — Trabajo en equipo, liderazgo, comunicación, adaptabilidad
3. Potencial de crecimiento (peso: 20%) — Velocidad de aprendizaje, iniciativa, progresión de roles
4. Alineación cultural (peso: 10%) — Valores, estilo de trabajo, motivaciones declaradas

=== PERFIL DEL PUESTO (referencia) ===
[Pega aquí el bloque de texto del Paso A1]

=== CV DEL CANDIDATO ===
Nombre: [Nombre del candidato]
[Pega aquí el texto completo del CV]

=== FORMATO DE SALIDA ===
Presenta los resultados en una tabla con columnas:
Dimensión | Peso | Puntuación (1-5) | Evidencias del CV | Brecha identificada

Al final, calcula la puntuación ponderada total usando la fórmula:
(Puntuación_Técnica × 0.40) + (Puntuación_Conductual × 0.30) +
(Puntuación_Potencial × 0.20) + (Puntuación_Cultural × 0.10)

Concluye con una recomendación de avance (Sí / Condicional / No) y las 2 áreas
prioritarias a explorar en entrevista para este candidato.
```

4. Envía el prompt para cada candidato finalista y espera las respuestas.

5. Copia los resultados de cada análisis multidimensional y agrégalos al documento `Screening-Comparativo-A2.docx` en una nueva sección titulada **"Análisis Multidimensional — Candidatos Finalistas"**.

6. Al tener los análisis de todos los finalistas, usa el siguiente prompt de comparación:

```text
Tengo los siguientes análisis multidimensionales de mis candidatos finalistas:

Candidato A — [Nombre]: Puntuación ponderada = [X.X]
Candidato B — [Nombre]: Puntuación ponderada = [X.X]
[Agrega más si aplica]

Considerando que el puesto es [nombre del puesto] y que el factor más crítico
para el éxito en el rol es [menciona el factor más importante según tu descriptivo],
¿cuál candidato recomendarías como primera opción y cuál como segunda opción de reserva?
Justifica tu respuesta en máximo 150 palabras.
```

7. Agrega esta recomendación comparativa al documento `Screening-Comparativo-A2.docx`.

8. Guarda y cierra el documento.

#### Resultado esperado
Para cada candidato finalista: una tabla de análisis multidimensional con puntuaciones, evidencias y brechas, más una puntuación ponderada total y recomendación de áreas a explorar en entrevista. Una recomendación comparativa final que justifica la selección de la primera y segunda opción.

#### Verificación
✅ Cada análisis contiene las 4 dimensiones con puntuaciones del 1 al 5 y evidencias concretas del CV.
✅ La puntuación ponderada total está calculada correctamente (verificar manualmente: suma de productos dimensión × peso).
✅ Se identifican al menos 2 áreas de exploración para entrevista por candidato.
✅ La recomendación comparativa hace referencia explícita al factor crítico del puesto.

---

### 🟢 BLOQUE B — Scorecard de Selección y Banco de Preguntas (≈ 45 minutos)

---

### Paso B1 — Crear el Scorecard de Selección en Excel con Copilot

**Objetivo:** Construir un scorecard de evaluación ponderado en Microsoft Excel utilizando Copilot en Excel, con criterios, escalas, fórmulas automáticas y visualización gráfica.

#### Instrucciones

**Parte B1.1 — Preparar la estructura base en Excel**

1. Abre **Microsoft Excel** y crea un nuevo libro en blanco.

2. Guárdalo inmediatamente como `Scorecard-Seleccion-[NombrePuesto].xlsx` en `Copilot-RH-Labs/Practica-02/` en OneDrive.

3. En la **Hoja 1**, crea manualmente la siguiente estructura de encabezados (fila 1, celdas A1:J1):

```
A1: Criterio de Evaluación
B1: Dimensión
C1: Peso (%)
D1: Candidato 1 - [Nombre]
E1: Candidato 2 - [Nombre]
F1: Candidato 3 - [Nombre]
G1: Candidato 4 - [Nombre]
H1: Escala (1-5)
I1: Descripción de Nivel 3 (Competente)
J1: Descripción de Nivel 5 (Excepcional)
```

4. Completa las primeras filas con los criterios de evaluación basados en tu descriptivo de puesto. Usa como referencia los criterios del análisis multidimensional del Paso A3. Ejemplo de estructura (adapta a tu puesto):

```
A2: Formación académica requerida        | B2: Técnica    | C2: 10
A3: Años de experiencia relevante        | B3: Técnica    | C3: 15
A4: Dominio de herramientas clave        | B4: Técnica    | C4: 15
A5: Logros cuantificables en CV          | B5: Técnica    | C5: 10
A6: Trabajo en equipo (evidencias)       | B6: Conductual | C6: 10
A7: Liderazgo / Iniciativa               | B7: Conductual | C7: 10
A8: Comunicación efectiva                | B8: Conductual | C8: 10
A9: Progresión de carrera                | B9: Potencial  | C9: 10
A10: Formación continua / Certificaciones| B10: Potencial | C10: 5
A11: Alineación cultural declarada       | B11: Cultural  | C11: 5
A12: TOTAL PONDERADO                     | B12:           | C12: =SUMA(C2:C11)
```

> ⚠️ Verifica que la suma de la columna C (pesos) sea exactamente 100%. Si no suma 100, ajusta los valores antes de continuar.

5. Selecciona el rango **A1:J12** y conviértelo en **Tabla de Excel**:
   - Ve a **Insertar → Tabla**
   - Confirma que "La tabla tiene encabezados" esté marcado
   - Haz clic en **Aceptar**
   - Nombra la tabla como `TablaScorecard` en el campo "Nombre de tabla" (esquina superior izquierda)

> ⚠️ **Importante:** Copilot en Excel **requiere** que los datos estén en formato Tabla para funcionar correctamente. Este paso es obligatorio.

**Parte B1.2 — Usar Copilot en Excel para completar el scorecard**

6. Haz clic en el botón **Copilot** en la cinta de opciones de Excel (pestaña **Inicio** o **Copilot**). Se abrirá el panel de Copilot en el lado derecho.

7. Escribe el siguiente prompt en el panel de Copilot de Excel:

```text
Tengo una tabla de scorecard de selección para el puesto de [nombre del puesto].
La tabla tiene criterios de evaluación, dimensiones y pesos para 4 candidatos.

Por favor, ayúdame a:
1. Agregar una columna "Puntuación Ponderada Candidato 1" que calcule
   el producto de la puntuación del Candidato 1 por el peso (%) dividido entre 100,
   para cada criterio.
2. Crear una fila de TOTAL que sume todas las puntuaciones ponderadas de cada candidato.
3. Agregar una fila de CLASIFICACIÓN que indique el ranking de cada candidato
   (1 = mejor puntuación).

Muéstrame las fórmulas que debo usar antes de aplicarlas.
```

8. Revisa las fórmulas sugeridas por Copilot. Si son correctas, aplícalas. Si no, usa el siguiente prompt de corrección:

```text
La fórmula sugerida para la puntuación ponderada no está tomando en cuenta
el peso porcentual correctamente. La fórmula correcta debería ser:
= [Puntuación del candidato] * [Peso en %] / 100
¿Puedes mostrarme la fórmula ajustada para la celda correspondiente?
```

9. Una vez aplicadas las fórmulas, ingresa las puntuaciones de los candidatos en las columnas D, E, F, G para cada criterio, basándote en los análisis del Bloque A. Usa la escala 1-5:

```
1 = No cumple el criterio
2 = Cumple parcialmente (por debajo del mínimo)
3 = Cumple el criterio (nivel competente)
4 = Supera el criterio
5 = Excede ampliamente el criterio
```

10. En el panel de Copilot de Excel, escribe el siguiente prompt para completar las descripciones de escala:

```text
Para la columna "Descripción de Nivel 3 (Competente)" y "Descripción de Nivel 5 (Excepcional)",
necesito que generes descripciones conductuales específicas para cada criterio de evaluación
de mi tabla. Por ejemplo, para el criterio "Dominio de herramientas clave":
- Nivel 3: "Demuestra uso funcional de las herramientas requeridas en tareas cotidianas"
- Nivel 5: "Domina las herramientas requeridas y puede capacitar a otros en su uso"

Genera las descripciones para los 10 criterios de evaluación de mi tabla.
Preséntalas en formato de tabla: Criterio | Descripción Nivel 3 | Descripción Nivel 5
```

11. Copia las descripciones generadas por Copilot y pégalas en las columnas I y J de tu tabla de Excel.

**Parte B1.3 — Crear visualización gráfica comparativa**

12. En el panel de Copilot de Excel, escribe:

```text
Basándote en las puntuaciones ponderadas totales de los 4 candidatos en mi tabla,
crea un gráfico de barras comparativo que muestre la puntuación total de cada candidato.
El gráfico debe tener título "Comparativo de Candidatos — [Nombre del Puesto]",
etiquetas de datos visibles y los candidatos ordenados de mayor a menor puntuación.
```

13. Si Copilot no puede insertar el gráfico directamente, insértalo manualmente:
    - Selecciona los nombres de los candidatos y sus puntuaciones totales ponderadas
    - Ve a **Insertar → Gráfico de barras agrupadas**
    - Agrega título y etiquetas de datos

14. Guarda el archivo Excel.

#### Resultado esperado
Un libro de Excel con una tabla de scorecard completa que incluye: 10 criterios de evaluación con pesos, puntuaciones de 4 candidatos, fórmulas de puntuación ponderada, totales, clasificación, descripciones de escala y un gráfico comparativo. La suma de pesos debe ser exactamente 100%.

#### Verificación
✅ La tabla tiene formato de Tabla de Excel (con encabezados resaltados y filtros automáticos).
✅ La suma de todos los pesos en la columna C es exactamente 100%.
✅ Las fórmulas de puntuación ponderada funcionan correctamente (verificar manualmente un cálculo).
✅ El gráfico comparativo muestra los 4 candidatos con sus puntuaciones totales.
✅ El archivo está guardado en OneDrive en la carpeta correcta.

---

### Paso B2 — Generar el Banco de Preguntas de Entrevista por Competencias

**Objetivo:** Usar Copilot Chat para generar un banco de 15 preguntas de entrevista por competencias (5 conductuales, 5 técnicas, 5 situacionales) con criterios de evaluación de respuesta, alineadas al perfil del puesto.

#### Instrucciones

1. Ve a la ventana de **Copilot Chat** y abre una **nueva conversación**.

2. Envía el siguiente prompt para generar el banco de preguntas conductuales:

```text
Actúa como un experto en selección por competencias con certificación en entrevistas
conductuales basadas en el modelo STAR (Situación, Tarea, Acción, Resultado).

Voy a proporcionarte el perfil del puesto y las competencias conductuales clave.
Tu tarea es generar 5 preguntas de entrevista CONDUCTUAL para este perfil.

=== PERFIL DEL PUESTO ===
[Pega aquí el bloque de texto del Paso A1]

=== COMPETENCIAS CONDUCTUALES A EVALUAR ===
[Lista las 3 competencias conductuales de tu descriptivo de puesto]

=== INSTRUCCIONES ===
Para cada pregunta conductual:
1. Escribe la pregunta (debe comenzar con "Cuéntame sobre una ocasión en que..." 
   o "Describe una situación en la que..." o similar)
2. Indica qué competencia evalúa
3. Proporciona los criterios de una respuesta EXCELENTE (nivel 5):
   qué elementos STAR debe contener para considerarse sobresaliente
4. Proporciona los criterios de una respuesta SUFICIENTE (nivel 3):
   qué mínimo debe incluir para considerarse aceptable
5. Señala 1 señal de alerta (red flag) en la respuesta que indicaría riesgo

Presenta el resultado en formato de tabla:
N° | Pregunta | Competencia | Criterios Respuesta Excelente | Criterios Respuesta Suficiente | Señal de Alerta
```

3. Envía el prompt y espera la respuesta. Copia los resultados.

4. En la **misma conversación**, envía el siguiente prompt para las preguntas técnicas:

```text
Ahora genera 5 preguntas de entrevista TÉCNICA para el mismo puesto.

Las preguntas técnicas deben evaluar los conocimientos y habilidades específicas
del rol, incluyendo herramientas, metodologías y situaciones técnicas reales.

Para cada pregunta técnica:
1. Escribe la pregunta (puede ser directa, de demostración o de resolución de caso)
2. Indica qué conocimiento técnico evalúa
3. Proporciona los elementos clave que debe contener una respuesta correcta
4. Indica el nivel de profundidad esperado para el nivel [semisenior/senior/etc.] del puesto
5. Sugiere 1 pregunta de seguimiento (follow-up) para profundizar

Usa el mismo formato de tabla que las preguntas conductuales.
```

5. Copia los resultados y envía el siguiente prompt para las preguntas situacionales:

```text
Finalmente, genera 5 preguntas SITUACIONALES (hipotéticas) para el mismo puesto.

Las preguntas situacionales presentan escenarios futuros hipotéticos y evalúan
el juicio, la toma de decisiones y la capacidad de resolución de problemas del candidato.
Deben comenzar con "Imagina que..." o "¿Qué harías si..." o "Supón que..."

Para cada pregunta situacional:
1. Escribe el escenario y la pregunta
2. Indica qué habilidad o juicio evalúa
3. Describe los elementos de una respuesta que demuestre alto criterio
4. Describe los elementos de una respuesta que muestre criterio insuficiente
5. Señala si la situación es común o crítica en el puesto

Usa el mismo formato de tabla.
```

6. Una vez que tengas las 15 preguntas (5 + 5 + 5), usa el siguiente prompt de consolidación:

```text
Excelente. Ahora necesito que consolides las 15 preguntas en un documento
estructurado para uso del entrevistador. El documento debe tener:

1. Encabezado: "Guía de Entrevista por Competencias — [Nombre del Puesto]"
2. Instrucciones breves para el entrevistador (máximo 5 líneas)
3. Sección 1: Preguntas Conductuales (las 5 preguntas con sus criterios)
4. Sección 2: Preguntas Técnicas (las 5 preguntas con sus criterios)
5. Sección 3: Preguntas Situacionales (las 5 preguntas con sus criterios)
6. Sección 4: Tabla de Puntuación Global del Candidato con las 15 preguntas,
   espacio para puntuación (1-5) y comentarios del entrevistador
7. Pie de página: "Documento de uso interno — Información confidencial"

Genera el contenido completo del documento en formato Markdown.
```

7. Copia el contenido Markdown generado por Copilot.

#### Resultado esperado
Un banco de 15 preguntas de entrevista organizadas en tres categorías, con criterios de evaluación de respuesta, señales de alerta y preguntas de seguimiento, consolidado en un documento estructurado para el entrevistador.

#### Verificación
✅ El banco contiene exactamente 5 preguntas conductuales, 5 técnicas y 5 situacionales.
✅ Cada pregunta tiene al menos: criterios de respuesta excelente, criterios de respuesta suficiente y una señal de alerta o indicador de calidad.
✅ Las preguntas conductuales usan el modelo STAR explícitamente.
✅ Las preguntas técnicas son específicas al puesto (no genéricas de RH).
✅ El documento consolidado tiene las 4 secciones solicitadas.

---

### Paso B3 — Exportar el Banco de Preguntas a Word con Copilot

**Objetivo:** Transferir el banco de preguntas generado en Copilot Chat a un documento de Word profesional, utilizando Copilot en Word para dar formato ejecutivo al documento.

#### Instrucciones

1. Abre **Microsoft Word** y crea un nuevo documento en blanco.

2. Guárdalo como `Guia-Entrevista-[NombrePuesto].docx` en `Copilot-RH-Labs/Practica-02/` en OneDrive.

3. Pega el contenido Markdown copiado del Paso B2 en el documento de Word.

4. Haz clic en el botón **Copilot** en la cinta de opciones de Word (pestaña **Inicio**) para abrir el panel de Copilot en Word.

5. Selecciona **todo el texto** del documento (Ctrl+A) y escribe el siguiente prompt en el panel de Copilot de Word:

```text
Por favor, da formato profesional a este documento de guía de entrevista.
Aplica las siguientes instrucciones de formato:
- El título principal debe estar en Título 1, centrado
- Los títulos de sección (Sección 1, 2, 3, 4) deben estar en Título 2
- Cada pregunta debe estar numerada y en negrita
- Los criterios de evaluación deben estar en viñetas con sangría
- La tabla de puntuación global debe tener bordes visibles y encabezados sombreados
- Agrega un encabezado de página con el nombre del puesto y la fecha de hoy
- Agrega un pie de página con "Documento de uso interno — Información confidencial"
- El documento debe verse profesional y listo para imprimir
```

6. Aplica los cambios sugeridos por Copilot.

7. Si el documento tiene secciones en Markdown sin convertir (texto con `#`, `**`, `-`), usa el siguiente prompt de limpieza:

```text
El documento todavía tiene símbolos de formato Markdown sin convertir
(como ##, **, - al inicio de líneas). Por favor, elimina todos esos símbolos
y aplica el formato de Word equivalente (encabezados, negrita, viñetas)
para que el documento se vea limpio y profesional.
```

8. Revisa el documento final y realiza ajustes manuales si es necesario (márgenes, fuente, espaciado).

9. Guarda el documento final.

10. **Paso de integración:** Abre el documento `Screening-Comparativo-A2.docx` y agrega al final una sección titulada **"Áreas Prioritarias de Entrevista por Candidato"** donde vincules las brechas identificadas en el Paso A3 con las preguntas específicas del banco que explorarían esas brechas. Ejemplo:

```
Candidato: Ana Torres
Brecha identificada: Evidencia limitada de liderazgo conductual
Preguntas recomendadas del banco: P.C-2 (Conductual), P.S-4 (Situacional)
```

#### Resultado esperado
Un documento Word profesional con la guía de entrevista completa, formateado con estilos de Word (Título 1, Título 2, viñetas, tabla con bordes), encabezado y pie de página, listo para usar en entrevistas reales.

#### Verificación
✅ El documento Word tiene formato profesional con estilos aplicados (no texto plano).
✅ La tabla de puntuación global es funcional y tiene espacio para notas del entrevistador.
✅ El encabezado y pie de página están presentes.
✅ El documento `Screening-Comparativo-A2.docx` tiene la sección de integración con brechas y preguntas vinculadas.
✅ Ambos archivos están guardados en OneDrive.

---

## 7. Validación y Pruebas

Al finalizar los dos bloques, realiza las siguientes verificaciones de calidad:

### Lista de verificación de entregables

| Entregable | Archivo | Criterio de calidad |
|---|---|---|
| Tabla de screening comparativo | `Screening-Comparativo-A2.docx` | 4 candidatos, 7 columnas, párrafo ejecutivo |
| Análisis multidimensional | Sección en `Screening-Comparativo-A2.docx` | 4 dimensiones, puntuaciones ponderadas, áreas de exploración |
| Scorecard de selección | `Scorecard-Seleccion-[Puesto].xlsx` | Tabla Excel, pesos = 100%, fórmulas, gráfico |
| Guía de entrevista | `Guia-Entrevista-[Puesto].docx` | 15 preguntas, 3 categorías, criterios de evaluación |
| Integración brechas-preguntas | Sección final en `Screening-Comparativo-A2.docx` | Mínimo 2 candidatos con preguntas vinculadas |

### Prueba de coherencia cruzada

Ejecuta esta verificación final para asegurar que los tres entregables son coherentes entre sí:

1. **Abre Copilot Chat** (nueva conversación) y escribe:

```text
Tengo tres documentos de un proceso de selección para el puesto de [nombre del puesto]:
1. Un screening comparativo con análisis multidimensional de 4 candidatos
2. Un scorecard de selección con puntuaciones ponderadas
3. Una guía de entrevista con 15 preguntas por competencias

El candidato mejor evaluado en el screening es [nombre del candidato con mayor puntuación].
Las brechas identificadas para este candidato son: [lista las brechas del Paso A3].

¿Las preguntas de entrevista que generé son suficientes para explorar estas brechas específicas,
o debería agregar preguntas adicionales? Si recomiendas agregar preguntas, genera 2-3
preguntas adicionales focalizadas en las brechas identificadas.
```

2. Si Copilot recomienda preguntas adicionales, agrégalas al banco en el documento Word con la etiqueta **"[Preguntas complementarias — brechas específicas]"**.

3. Verifica que la clasificación del scorecard (Paso B1) sea **consistente** con la recomendación de avance del análisis multidimensional (Paso A3). Si hay discrepancias, documenta la razón en el archivo `Screening-Comparativo-A2.docx`.

---

## 8. Solución de Problemas

### Problema 1: Copilot en Excel no responde o no genera fórmulas correctas

**Síntoma:** Al escribir prompts en el panel de Copilot de Excel, la herramienta no genera fórmulas, muestra un mensaje de error, o las fórmulas generadas no funcionan correctamente en la tabla.

**Causa probable:** Los datos no están en formato de Tabla de Excel reconocido por Copilot, la versión de Excel no cumple el requisito mínimo (v2401), o la licencia de Copilot no está activa en la aplicación de escritorio.

**Solución:**

1. Verifica que el rango de datos tenga formato de Tabla: haz clic dentro del rango → pestaña **Tabla** debe aparecer en la cinta de opciones. Si no aparece, selecciona el rango y ve a **Insertar → Tabla**.
2. Verifica la versión de Excel: **Archivo → Cuenta → Acerca de Excel**. Si es anterior a 2401, actualiza desde **Archivo → Cuenta → Opciones de actualización → Actualizar ahora**.
3. Cierra y vuelve a abrir Excel. Haz clic en **Copilot** en la cinta de opciones; si no aparece, ve a **Archivo → Opciones → Complementos** y verifica que el complemento de Copilot esté habilitado.
4. Si el problema persiste, usa **Copilot Chat** (versión web) como alternativa: pide las fórmulas en el chat y aplícalas manualmente en Excel.

---

### Problema 2: Los outputs de Copilot Chat son demasiado genéricos o no se alinean al puesto específico

**Síntoma:** Copilot genera preguntas de entrevista o análisis de CVs que parecen aplicables a cualquier puesto de RH, sin referencias específicas al perfil definido. Las puntuaciones del análisis multidimensional no tienen evidencias concretas del CV.

**Causa probable:** El prompt no incluye suficiente contexto específico del puesto, o el texto del CV pegado en el chat fue truncado o está incompleto. También puede ocurrir cuando la conversación tiene demasiado contexto acumulado que "diluye" las instrucciones.

**Solución:**

1. Inicia una **nueva conversación** en Copilot Chat (no continúes en la misma sesión con muchos mensajes previos).
2. Verifica que el texto del CV pegado en el prompt esté **completo** y no cortado. El límite de tokens de Copilot puede truncar CVs muy largos; si el CV tiene más de 2 páginas, divide el análisis en dos prompts.
3. Refuerza el contexto del puesto en el prompt usando la instrucción: `"Recuerda que el puesto es específicamente [nombre exacto del puesto] en el área de [área]. Todas tus respuestas deben hacer referencia explícita a los requisitos de este puesto, no a puestos genéricos de RH."`.
4. Si las preguntas siguen siendo genéricas, usa el prompt de refinamiento: `"Las preguntas que generaste son demasiado genéricas. Por favor, reformula la pregunta número [X] para que sea específica al contexto de [competencia o herramienta específica del puesto]. Incluye terminología técnica del área."`.

---

## 9. Limpieza del Entorno

Al finalizar la práctica, realiza los siguientes pasos de cierre:

1. **Guardar todos los archivos finales** en OneDrive:
   - `Screening-Comparativo-A2.docx` ✅
   - `Scorecard-Seleccion-[NombrePuesto].xlsx` ✅
   - `Guia-Entrevista-[NombrePuesto].docx` ✅

2. **Cerrar las conversaciones de Copilot Chat:** No es necesario eliminarlas, pero evita dejar conversaciones con datos de práctica abiertas en pantalla en entornos compartidos.

3. **Verificar sincronización de OneDrive:** Confirma que el ícono de OneDrive en la barra de tareas muestre el símbolo de sincronización completada (✅ palomita azul), no el ícono de sincronización pendiente (⟳).

4. **Cerrar los archivos de CVs ficticios:** Cierra los cuatro archivos `.docx` de CVs que estuvieron abiertos durante la práctica.

5. **No eliminar archivos de práctica:** Los archivos de CVs ficticios en `Practica-02/` deben permanecer en OneDrive para futuras referencias del curso.

6. **Registro de reflexión (opcional pero recomendado):** En el documento `Screening-Comparativo-A2.docx`, agrega una sección final titulada **"Reflexión del Participante"** y responde brevemente (3-5 líneas) a estas preguntas:
   - ¿Qué aspecto del proceso de screening asistido por Copilot te resultó más valioso?
   - ¿Qué ajustes harías a los prompts si repitieras este ejercicio?
   - ¿Cómo aplicarías este flujo de trabajo en tu contexto laboral real?

---

## 10. Resumen

### Lo que lograste en esta práctica

En este laboratorio aplicaste de forma práctica los conceptos centrales de la Lección 2.1, ejecutando un proceso completo de screening curricular asistido por IA con criterios multidimensionales:

| Bloque | Habilidad desarrollada | Herramienta |
|---|---|---|
| **A1** | Extracción y estructuración de criterios de puesto para prompts | Copilot Chat |
| **A2** | Filtrado comparativo de 4 CVs con tabla de 7 dimensiones | Copilot Chat |
| **A3** | Análisis multidimensional ponderado (técnica, conductual, potencial, cultural) | Copilot Chat |
| **B1** | Construcción de scorecard ponderado con fórmulas y visualización | Copilot en Excel |
| **B2** | Generación de banco de 15 preguntas por competencias con criterios STAR | Copilot Chat |
| **B3** | Exportación y formato profesional de guía de entrevista | Copilot en Word |

### Principios clave reforzados

- **El prompt es el diferenciador:** La calidad del análisis de Copilot es directamente proporcional a la precisión de las instrucciones. Los prompts con contexto + criterios + formato de salida producen resultados accionables.
- **Copilot como amplificador, no sustituto:** Todas las recomendaciones generadas por Copilot fueron validadas y contextualizadas por ti como profesional de RH. La decisión final siempre es humana.
- **Variabilidad es normal:** Si tus resultados difieren de los de otros participantes, esto es esperado. Lo que cuenta es la calidad del proceso de prompting y los criterios de refinamiento que aplicaste.
- **Coherencia cruzada:** Los tres entregables (screening, scorecard, guía de entrevista) deben ser coherentes entre sí, formando un expediente de selección integrado.

### Conexión con la siguiente práctica

En la **Práctica 3** avanzarás al diseño de guías de entrevista profunda y matrices de evaluación de candidatos finalistas. Los documentos generados en esta práctica —especialmente el banco de preguntas y el análisis de brechas— serán insumos directos para ese siguiente laboratorio. Asegúrate de que todos tus archivos estén correctamente guardados y sincronizados en OneDrive antes de la siguiente sesión.

---

### Recursos de Referencia

| Recurso | Descripción | Enlace |
|---|---|---|
| Documentación oficial de Copilot en Microsoft 365 | Guía de uso y casos de aplicación | [learn.microsoft.com/es-es/copilot/microsoft-365](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview) |
| Copilot en Excel — Primeros pasos | Requisitos y funcionalidades de Copilot en Excel | [support.microsoft.com — Copilot en Excel](https://support.microsoft.com/es-es/topic/copilot-en-excel) |
| Modelo STAR para entrevistas conductuales | Guía de la SHRM sobre entrevistas por competencias | [shrm.org/topics-tools/topics/selection-assessment](https://www.shrm.org/topics-tools/topics/selection-assessment) |
| Análisis multidimensional de talento | Deloitte Insights — Human Capital Trends | [deloitte.com/us/en/insights/focus/human-capital-trends](https://www2.deloitte.com/us/en/insights/focus/human-capital-trends.html) |
| Reducción de sesgos en selección con IA | Harvard Business Review — Hiring Algorithms | [hbr.org/2019/05/all-the-ways-hiring-algorithms-can-introduce-bias](https://hbr.org/2019/05/all-the-ways-hiring-algorithms-can-introduce-bias) |

---

> 📌 **Recordatorio final de privacidad:** Todos los CVs, nombres y datos utilizados en esta práctica son ficticios. Si en algún momento durante el laboratorio te encontraste ante la tentación de usar datos reales de candidatos o colaboradores para "hacer el ejercicio más realista", recuerda que esto está estrictamente prohibido por la política del curso y por las regulaciones de protección de datos de tu organización. Los datos reales nunca deben ingresarse en Copilot Chat.

---
LAB_END---
