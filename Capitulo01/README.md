# Práctica 1 — Generación de Descriptivos de Puesto y Prompts de Búsqueda para Candidatos

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 60 minutos (Densidad Operativa en Atracción y Sourcing Avanzado) |
| **Complejidad** | Inicial - Intermedia |
| **Audiencia** | Gerentes de Reclutamiento, Consultores de Atracción de Talento y Generalistas de RH |
| **Tecnologías** | Microsoft Copilot (M365 / Interfaz de Chat) y Microsoft Word |
| **Enfoque** | Diseño avanzado de descriptivos de puesto (Job Descriptions) para roles industriales críticos, uso de Meta-Prompting para crear plantillas de búsqueda hiper-específicas y automatización de cadenas de búsqueda Booleana para plataformas de empleo. |

---

## 2. Descripción Corta

Este laboratorio práctico de 60 minutos capacita a los profesionales de Recursos Humanos en el uso de Microsoft Copilot para acelerar la etapa de prospección en la industria de recubrimientos. Los estudiantes aprenderán a estructurar descriptivos de puesto técnicos para áreas de producción de alta temperatura y laboratorios de diseño, y dominarán el arte del "Meta-Prompting" para obligar a la IA a construir sus propias instrucciones de filtrado y sourcing, reduciendo los tiempos de publicación y búsqueda de candidatos calificados.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar descriptivos de puestos industriales y de diseño** que equilibren habilidades técnicas (Hard Skills) del sector cerámico con competencias blandas.
* **Aplicar técnicas de Meta-Prompting** en Copilot para autogenerar prompts de reclutamiento altamente efectivos y personalizados.
* **Construir cadenas de búsqueda Booleana óptimas** (AND, OR, NOT) mediante IA para localizar perfiles técnicos en LinkedIn y bases de datos.
* **Diseñar estrategias de atracción de talento** basadas en la Propuesta de Valor al Candidato (EVP) específica para plantas de manufactura automatizada.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Manual_Atraccion_Talento_Ceramico.docx`.

---

## 5. Procedimiento Paso a Paso

### Fase A: Ingeniería del Descriptivo de Puesto – Perfil Técnico de Planta

El departamento de producción requiere incorporar de manera urgente un **Ingeniero de Investigación y Desarrollo (I+D) especializado en Esmaltes y Formulación Cerámica**. Este es un perfil sumamente escaso que requiere entender de química de materiales y procesos de cocción.

1. Abra el chat general de **Microsoft Copilot**.
2. Introduzca el siguiente prompt avanzado para estructurar la vacante:

```
Actúa como un Headhunter Senior y Consultor de Atracción de Talento especializado en la industria de recubrimientos pesados. Necesito estructurar un Descriptivo de Puesto (Job Description) formal y atractivo para el rol de: 'Ingeniero de I+D de Esmaltes Cerámicos y Porcelánicos'.

El entregable debe ser en español, con tono corporativo y redactado en bloques limpios para Word, incluyendo:
1. **Misión del Puesto:** Una introducción de 3 líneas que conecte el rol con la innovación en tendencias de diseño y acabados en piedra natural y cerámica.
2. **Responsabilidades Clave (5 viñetas):** Deben incluir la formulación de barbotinas (pastas cerámicas), control de defectos post-cocción (como el "craquelado" o "pinholing"), y pruebas de resistencia al desgaste (PEI) y absorción de agua.
3. **Requisitos Técnicos (Hard Skills):** Formación, manejo de software de colorimetría y conocimiento en hornos de rodillos continuos.
4. **Competencias (Soft Skills):** Enfoque basado en metodologías de resolución de problemas en piso de planta.

Genera el texto de manera directa, sin introducciones ni saludos.
```

3. Seleccione el descriptivo generado, cópielo (`Ctrl+C`) y péguelo (`Ctrl+V`) en su archivo de Word (`Manual_Atraccion_Talento_Ceramico.docx`).

---

### Fase B: Creación de Cadenas de Búsqueda Booleana para Sourcing Avanzado

Una vez estructurado el perfil, el reclutador debe salir al mercado a buscar candidatos de forma activa utilizando comandos booleanos en motores de búsqueda o redes profesionales.

1. Introduzca el siguiente prompt en Copilot para automatizar la cadena de búsqueda exacta:

```
Actúa como un Talent Sourcer Experto. Basado en el perfil de 'Ingeniero de I+D de Esmaltes Cerámicos' de la fase anterior, necesito que generes 3 cadenas de búsqueda Booleana diferentes para localizar candidatos pasivos en LinkedIn o Google.

Debes emplear operadores lógicos de forma estricta (AND, OR, NOT, comillas y paréntesis). 
- La primera cadena debe enfocarse en la combinación de títulos de puesto alternativos (ej. Químico Cerámico, Ingeniero de Procesos Cerámicos).
- La segunda cadena debe enfocarse en habilidades técnicas específicas (ej. "esmaltes", "porcelánico", "colorimetría").
- La tercera cadena debe ser restrictiva, excluyendo perfiles que pertenezcan únicamente al sector cementero o de construcción civil (usando NOT o el signo menos).

Entrega únicamente las líneas de comando listas para copiar y usar en los motores de búsqueda.
```

2. Copie las tres cadenas booleanas, pruebalas en LinkedIn o Google y agréguelas a su documento de Word bajo el subtítulo `## Estrategia de Sourcing Booleano`.

---

### Fase C: El Meta-Prompt – Obligando a Copilot a Diseñar Prompts de Reclutamiento Perfectos

Para profesionalizar el área de Recursos Humanos, el estudiante aprenderá a usar un **Meta-Prompt**. En lugar de adivinar cómo pedirle cosas a la IA, usaremos una instrucción maestra que guiará a Copilot para crear plantillas de prompts efectivas que cualquier reclutador junior de la empresa pueda usar en el futuro.

1. Ingrese el siguiente Meta-Prompt en la interfaz de Copilot:

```
Actúa como un Ingeniero de Prompts experto y Director Global de Adquisición de Talento. Tu objetivo es crear un PROMPT PERFECTO y REUTILIZABLE en español que el equipo de Recursos Humanos usará para evaluar candidatos en entrevistas.

Diseña un prompt estructurado bajo la metodología 'Rol + Contexto + Tarea + Restricción' para que, cuando un reclutador lo use en el futuro, la IA actúe como un entrevistador técnico y genere un banco de 5 preguntas de entrevista por competencias STAR (Situación, Tarea, Acción, Resultado). El prompt que diseñes debe incluir marcadores de posición entre corchetes como [Insertar Nombre del Puesto] e [Insertar Competencia Clave] para que sea una plantilla adaptable.

Devuélveme la plantilla del prompt final dentro de un bloque de código limpio, explicando brevemente al inicio por qué esa estructura garantiza un resultado de calidad.
```

2. Analice la plantilla generada por Copilot. Copie la estructura completa y péguela en un nuevo chat ajustandola con los parametros deseados. Finalmente copie y péguela en su archivo de Word bajo el título `## Herramientas de Productividad: Plantillas de Meta-Prompting`.

---

### Fase D: Reto de Aplicación Autónoma – Sourcing para el Área de Diseño y Tendencias

**Instrucciones para el estudiante:** La planta necesita abrir una nueva línea de negocio orientada a la comercialización de **Piedras Naturales y Porcelánicos de Gran Formato (Slabs)** para proyectos arquitectónicos de lujo. El Director de RH solicita perfiles para el puesto de **Diseñador de Producto / Trendsetter de Superficies**. Este perfil requiere tanto competencias artísticas de diseño industrial (diseño digital de vetas de mármol y texturas) como conocimientos comerciales para entender el mercado premium.

#### El Desafío:
Aplicando lo aprendido en las fases anteriores, redacte un prompt estratégico de forma totalmente autónoma en Copilot para resolver este requerimiento de atracción:

1. **Estructura del Requerimiento:**
   - Solicite a la IA que genere el perfil del puesto combinando diseño técnico con análisis de tendencias arquitectónicas internacionales.
   - Pídale específicamente que incluya la Propuesta de Valor al Candidato (EVP) orientada a atraer perfiles creativos de alto nivel (beneficios no económicos, flexibilidad, retos creativos).
2. **Generación de la Estrategia:** Ordene a Copilot que, junto al perfil, entregue un mensaje de contacto directo (InMail para LinkedIn) de máximo 150 palabras. Este mensaje debe ser persuasivo, cercano y debe enganchar al diseñador invitándolo a liderar la transformación estética de los recubrimientos cerámicos de la empresa.
3. **Prueba de Verificación:** El estudiante debe validar que el mensaje de contacto sea personalizado para el sector de acabados de lujo y que use un tono que un diseñador industrial considere disruptivo, evitando formatos rígidos o puramente fabriles.

---

## 6. Conceptos Clave para Recordar

* **Sourcing:** Proceso proactivo de identificación, contacto y preevaluación de candidatos potenciales (tanto activos como pasivos) que no se han postulado formalmente a una oferta de empleo.
* **Búsqueda Booleana:** Técnica de búsqueda basada en la utilización de operadores matemáticos/lógicos (AND, OR, NOT) que permite combinar palabras clave para filtrar bases de datos de talento con precisión milimétrica.
* **Meta-Prompt:** Una instrucción de alto nivel dirigida a la Inteligencia Artificial donde se le pide que actúe como programador o diseñador para redactar un nuevo prompt optimizado, estandarizando procesos de trabajo.

---

## 7. Resultado Esperado del Estudiante

Para validar la correcta conclusión de esta práctica de 60 minutos, el estudiante consolidará los siguientes componentes:

1. **Archivo `Manual_Atraccion_Talento_Ceramico.docx` (Word):**
   * Documento técnico que contiene el Job Description del Ingeniero de I+D de la Fase A, las cadenas booleanas listas de la Fase B y la plantilla maestra de Meta-Prompting obtenida en la Fase C.
2. **Evidencia del Reto Autónomo:**
   * La documentación completa del perfil de Diseñador Trendsetter y el mensaje de InMail persuasivo de la Fase D integrados al final del archivo, demostrando el control total de metodologías modernas de prospección con IA.
