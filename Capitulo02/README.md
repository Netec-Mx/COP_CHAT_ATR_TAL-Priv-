# Práctica 2 — Simulación de Screening Curricular y Creación de Scorecards de Selección

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 90 minutos (Alta Densidad Analítica, Simulación y Toma de Decisiones Basada en Datos) |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Reclutamiento, Consultores de Atracción de Talento y Generalistas de RH |
| **Tecnologías** | Microsoft Copilot (M365 / Interfaz de Chat) y Microsoft Word / Excel |
| **Enfoque** | Evaluación objetiva de perfiles para la industria de recubrimientos, diseño de matrices de puntuación (Scorecards) estandarizadas, mitigación de sesgos inconscientes en procesos de selección y auditoría de currículums frente a requisitos de planta. |

---

## 2. Descripción Corta

Este laboratorio práctico de 90 minutos capacita a los profesionales de Recursos Humanos en el uso avanzado de Microsoft Copilot para la etapa de selección y toma de decisiones. Los estudiantes aprenderán a transformar requerimientos ambiguos en tablas estructuradas de evaluación, auditar de forma ética perfiles profesionales reduciendo sesgos de género o edad, automatizar guías de entrevistas por competencias y programar rúbricas numéricas personalizadas para mitigar la subjetividad en las ternas de candidatos para posiciones clave de la compañía de recubrimientos cerámicos y porcelánicos.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Diseñar Scorecards de Selección cuantitativos** que traduzcan las necesidades operativas en indicadores medibles numéricamente.
* **Simular procesos de screening curricular masivo** utilizando prompts de extracción y análisis de texto.
* **Construir guías de entrevista estructuradas** con preguntas de comportamiento y criterios de respuestas esperadas.
* **Detectar y mitigar sesgos inconscientes** en las descripciones de experiencia laboral y en los criterios de los líderes de área.
* **Construir matrices de decisiones ponderadas** para justificar técnicamente ante la dirección la selección de un candidato sobre otro.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Manual_Evaluacion_Eficiente_Talento.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Construcción de la Scorecard de Selección (Matriz de Puntuación) 

Para evitar que los líderes de área contraten basándose en "intuiciones", el equipo de talento debe diseñar una Scorecard estandarizada. Evaluaremos el perfil de **Gerente de Calidad de Planta de Porcelánico**, responsable de asegurar que el producto final no presente fallas de planeidad ni variaciones de tono en lotes de alto volumen.

1. Abra el chat general de **Microsoft Copilot**.
2. Introduzca el siguiente prompt avanzado para estructurar la Scorecard en formato de tabla limpia:

```
Actúa como un Consultor de Talent Analytics y Compensación. Necesito diseñar una Scorecard de Selección (Matriz de Evaluación) cuantitativa para la posición de: 'Gerente de Calidad de Planta de Porcelánico'. 

El resultado debe ser una tabla formal en español, lista para copiar a Word/Excel, estructurada bajo las siguientes especificaciones:
1. Columnas exactas: Competencia/Habilidad, Criterio de Evaluación (Qué buscar), Ponderación (0% a 100%), Escala de Calificación (1 a 5 donde 1 es Deficiente y 5 es Sobresaliente).
2. Debes incluir exactamente 5 filas evaluables distribuidas así:
   - 2 Habilidades Técnicas Críticas (ej. Conocimiento en normas ISO 9001 aplicadas a manufactura continua, control de mermas y desviaciones de colorimetría en cerámica).
   - 2 Competencias Conductuales/Liderazgo (ej. Gestión de equipos operativos bajo presión, resolución de conflictos sindicados).
   - 1 Ajuste Cultural (Alineación con la seguridad industrial en plantas de alta temperatura y hornos).
3. Asegúrate de que la suma de todas las ponderaciones de las 5 filas sea exactamente igual al 100%.

Omite saludos y textos introductorios. Entrégame la tabla directamente.
```

3. Seleccione la tabla estructurada devuelta por Copilot, cópiela (`Ctrl+C`) y péguela (`Ctrl+V`) en su archivo de Word (`Manual_Evaluacion_Eficiente_Talento.docx`).

---

### Fase B: Simulación de Screening Curricular Avanzado (Extracción de Datos) 

En esta fase, simularemos cómo la IA procesa el texto de un currículum complejo y desordenado para mapearlo directamente contra las necesidades de la vacante, aislando los datos de valor.

1. Introduzca el siguiente comando en la interfaz de Copilot para realizar el filtro del candidato simulado:

```
Actúa como un Reclutador Técnico Senior. Analiza el siguiente fragmento de perfil profesional extraído de un currículum y evalúa si cumple con los requisitos mínimos para el puesto de Gerente de Calidad de la planta de recubrimientos cerámicos.

Currículum a evaluar:
'Ing. Alejandro Ruiz - 14 años de experiencia en plantas industriales. Me especializo en controlar la eficiencia en procesos de manufactura automatizada. Del 2018 al 2024 fui Jefe de Control de Calidad en Azulejos del Centro, reduciendo el scrap de la planta en un 12% mediante la implementación de herramientas Lean Six Sigma. Conozco la normativa ISO 9001 de memoria. Sé liderar cuadrillas de hasta 45 operarios en turnos rotativos. Anteriormente trabajé en el sector automotriz, pero me pasé a los materiales cerámicos porque me apasiona el diseño de superficies. Hablo inglés intermedio.'

Devuélveme un reporte ejecutivo estructurado en español con tres apartados claros:
1. **Factores de Éxito Encontrados:** Qué elementos del texto hacen un match perfecto con la industria de acabados cerámicos.
2. **Brechas Identificadas (Gaps):** Qué requisitos técnicos o de nivel de puesto le hacen falta o quedan ambiguos según el texto.
3. **Decisión de Screening:** Clasifica al candidato estrictamente en una de estas categorías: 'Avanza a Entrevista', 'En Reserva' o 'Rechazado'. Justifica la decisión en un párrafo técnico.
```

2. De acuerdo a la respuesta de Copilot continúe la conversación hasta que logre obtener un resultado deseado.

3. Copie el análisis resultante de Copilot y archívelo en su documento de Word bajo el título `## Reporte Técnico de Screening: Caso Alejandro Ruiz`.

---

### Fase C: Ingeniería de la Guía de Entrevista por Competencias (STAR) 

Una vez que el candidato avanza, el reclutador necesita una guía exacta de preguntas de comportamiento para validar la veracidad de la experiencia declarada en el currículum, evitando respuestas teóricas.

1. En el mismo chat, introduzca el siguiente prompt para estructurar la guía de preguntas:

```
Actúa como un Diseñador de Procesos de Selección de Alto Desempeño. Tomando como base la competencia conductual de la Scorecard: 'Gestión de equipos operativos bajo presión y resolución de conflictos sindicados', genera una guía de entrevista estructurada en español para el puesto de Gerente de Calidad.

La guía debe entregarse en formato de tabla con las siguientes columnas esenciales:
- **Dimensión Evaluada** (Fase del método STAR: Situación/Tarea, Acción, Resultado).
- **Pregunta Sugerida para el Reclutador** (Enfocada en experiencias pasadas en plantas de manufactura continua).
- **Semáforo de Respuestas Esperadas** (Divide esta celda en dos subapartados: Red Flags o Respuestas Insatisfactorias VS. Respuestas Ideales o Green Flags).

Genera al menos 3 preguntas profundas que fuercen al candidato a describir un conflicto real con operarios en el piso de producción y cómo logró que se acataran los estándares de calidad sin detener los hornos.
```

2. Copie la guía de entrevista generada e incorpórela en el archivo de Word bajo la sección `## Guía de Entrevista Estructurada por Competencias`.

---

### Fase D: Calibración Ética, Equidad y Mitigación de Sesgos

Una de las grandes directrices del desarrollo de talento moderno es garantizar procesos de selección ciegos, equitativos y libres de discriminación. En esta fase, utilizaremos a Copilot para auditar criterios tradicionales de selección e identificar sesgos inconscientes en la industria de manufactura pesada.

1. Ingrese la siguiente instrucción analítica en Copilot:

```
Actúa como un Especialista en Diversidad, Equidad e Inclusión (DEI) aplicado a entornos industriales. Analiza los siguientes tres comentarios reales emitidos por directores de operaciones y líderes de planta tradicionales al evaluar candidatos para puestos de supervisión en la fábrica de recubrimientos cerámicos:

1. 'Prefiero que el supervisor del área de molienda pesada sea un hombre, porque el ambiente en piso con las tolvas de arcilla y los molinos es muy tosco y requiere carácter fuerte.'
2. 'Este candidato de 53 años tiene un currículum impecable en colorimetría porcelánica, pero me preocupa que no se adapte a las nuevas tecnologías y pantallas táctiles de las prensas de última generación que instalamos el año pasado.'
3. 'Buscamos un perfil joven y con energía para el área de desarrollo de canales comerciales institucionales, que aguante viajes constantes y no tenga compromisos familiares que lo aten.'

Para cada uno de los tres puntos, redacta un contraargumento profesional, ético y corporativo en español. Explica el sesgo específico que se está cometiendo (género, edadismo, situación familiar) y propón un criterio alternativo de evaluación de competencias que el equipo de Atracción de Talento pueda presentarle a los líderes para reorientar la decisión de forma objetiva.
```

2. Copie la guía de mitigación de sesgos generada por la IA y guárdela en su documento bajo el título `## Protocolo de Calibración Ética y Mitigación de Sesgos`.

---

### Fase E: Reto de Aplicación Autónoma – Creación de la Matriz Decisional Ponderada Final

**Instrucciones para el estudiante:** Imagina que has concluido las entrevistas para la vacante de **Diseñador de Producto / Trendsetter de Superficies** (la vacante del reto del Capítulo 1). Tienes dos candidatas finalistas en la mesa:

* **Candidata A (Elena V.):** Diseñadora Industrial con 8 años de experiencia modelando texturas visuales de mármol y granito para marcas de lujo en Italia. Su portafolio técnico es perfecto (5/5), pero sus habilidades de negociación comercial y liderazgo de equipos son moderadas (3/5).
* **Candidata B (Mónica S.):** Arquitecta con 4 años de experiencia en desarrollo de productos cerámicos locales, con un empuje comercial sobresaliente, experiencia liderando proyectos complejos y excelente manejo de clientes institucionales (5/5), pero su portafolio técnico en modelado digital avanzado está en un nivel intermedio (3/5).

#### El Desafío:
Redacte un prompt de forma totalmente autónoma en Copilot para resolver este dilema de selección mediante el uso de lógica analítica:

1. **Parámetros del Desafío:**
   - Ordene a Copilot que cree una **Tabla de Comparación Ponderada** entre Elena V. y Mónica S.
   - La tabla debe calificar numéricamente tres dimensiones: Aptitud Técnica, Competencia Comercial y Liderazgo/Gestión.
2. **Asignación de Ponderación Estratégica:** Usted debe definir en su instrucción qué dimensión pesa más para la empresa (por ejemplo, si el negocio necesita innovar urgentemente en diseño de lujo, la Aptitud Técnica debería pesar el 60% del total; si el negocio necesita vender más el inventario existente, la Competencia Comercial debe mandar).
3. **Recomendación Final de Contratación:** Pídale a Copilot que calcule la puntuación final ponderada de cada candidata basada en las reglas que usted definió y que emita un dictamen definitivo argumentando a cuál de las dos se le debe extender la oferta económica y qué plan de desarrollo corto se le debe estructurar para mitigar la debilidad con la que entra.
4. **Prueba de Verificación:** Verifique que el dictamen final no contenga contradicciones y demuestre que una decisión de contratación de alto nivel se toma con datos duros y ponderaciones del negocio, no por afinidades personales.

---

## 6. Conceptos Clave para Recordar

* **Scorecard de Selección:** Herramienta de evaluación estandarizada que desglosa los requisitos de una vacante en indicadores medibles e idénticos para todos los candidatos, garantizando una competencia justa.
* **Metodología STAR:** Técnica de entrevista que evalúa competencias pidiendo al candidato que describa de forma cronológica una **S**ituación, la **T**area requerida, la **A**cción tomada y el **R**esultado cuantitativo obtenido.
* **Sesgo Inconsciente:** Atajos mentales u opiniones preconcebidas (sobre edad, género, procedencia) que influyen en las decisiones de contratación de forma involuntaria, afectando la objetividad del proceso.
* **Matriz de Decisión Ponderada:** Modelo matemático simple donde se asignan pesos específicos a diferentes criterios de evaluación según las prioridades del negocio en ese momento temporal exacto.

---

## 7. Resultado Esperado del Estudiante

Para validar la correcta conclusión de esta práctica avanzada de 90 minutos, el estudiante consolidará los siguientes componentes:

1. **Archivo `Manual_Evaluacion_Eficiente_Talento.docx` (Word):**
   * Documento corporativo que incluye la Scorecard del Gerente de Calidad (Fase A), el análisis de screening curricular de Alejandro Ruiz (Fase B), la guía de entrevista STAR de la Fase C y la guía ética de mitigación de sesgos industriales (Fase D).
2. **Evidencia del Reto Autónomo:**
   * La tabla comparativa numérica y el dictamen final de contratación ponderado para la posición de Diseñador Trendsetter de la Fase E adjuntos al cierre del documento, demostrando el dominio de técnicas avanzadas de selección basadas en analítica.
