---LAB_START---
LAB_ID: 03-00-01
---MARKDOWN---
# Práctica 3 — Estructuración de la Matriz de Habilidades, DNC y Planes de Capacitación por Puesto

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta |
| **Nivel Bloom** | Crear (Create) |
| **Módulo** | Módulo 3 — Desarrollo y Retención de Talento |
| **Herramientas principales** | Copilot en Excel · Copilot en Word · Microsoft 365 Copilot Chat · OneDrive for Business |
| **Datos utilizados** | Dataset ficticio del equipo de trabajo (archivo proporcionado por el instructor) |

---

## 2. Descripción General

En esta práctica construirás el ciclo completo de identificación de brechas y diseño de intervenciones de desarrollo para un equipo ficticio de ocho personas. Comenzarás estructurando una **skill matrix** en Excel con niveles de dominio del 1 al 4, utilizando Copilot para detectar brechas y generar visualizaciones de calor. A partir de esa matriz producirás un **Diagnóstico de Necesidades de Capacitación (DNC)** formal en Copilot Chat y, finalmente, diseñarás en Word **planes de capacitación individualizados** y una **guía de onboarding** de dos páginas alineada con los principios del modelo de las 4 C y las estrategias de employer branding interno estudiadas en la Lección 3.1.

> ⚠️ **Aviso de privacidad:** Todos los datos utilizados en esta práctica son ficticios. No ingreses información personal real de empleados o candidatos en ninguna herramienta de Copilot bajo ninguna circunstancia.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio, serás capaz de:

- [ ] Construir una skill matrix funcional en Excel con Copilot, asignando niveles de dominio (1–4) y calculando brechas respecto al perfil requerido para un equipo ficticio de 8 personas.
- [ ] Redactar un DNC estructurado con Copilot Chat, priorizando brechas críticas y alineándolas a objetivos organizacionales con análisis de causa raíz.
- [ ] Diseñar planes de capacitación individualizados en Word con Copilot, incluyendo objetivos SMART, modalidades, cronograma y KPIs de efectividad.
- [ ] Crear una guía de onboarding de dos páginas y un mensaje de employer branding interno utilizando Copilot, aplicando el modelo de las 4 C (Compliance, Clarification, Culture, Connection).

---

## 4. Prerrequisitos

### Conocimiento previo
- Haber completado las Prácticas 1 y 2 del curso; contar con descriptivos de puesto y scorecard de competencias guardados en OneDrive (carpeta `Copilot-RH-Labs`).
- Comprensión del modelo de las 4 C de onboarding (Lección 3.1) y del concepto de DNC (material del Módulo 3).
- Familiaridad básica con tablas de Excel (formato como Tabla, filtros, formato condicional).

### Acceso y licencias
- Cuenta corporativa Microsoft 365 con **licencia Copilot activa** (M365 E3/E5 + complemento Copilot).
- Microsoft Excel y Word versión 2401 o superior con Copilot habilitado.
- Acceso a [Microsoft 365 Copilot Chat](https://m365.cloud.microsoft/chat) con el ícono de escudo/protección visible (modo de trabajo protegido).
- Archivo `Dataset_Equipo_Ficticio_Lab03.xlsx` descargado en la carpeta `Copilot-RH-Labs` de OneDrive.

---

## 5. Entorno de Laboratorio

### Hardware recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 / Ryzen 5 (8.ª gen) | Intel Core i7 / Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px |
| Almacenamiento libre | 5 GB | 10 GB |
| Conexión a internet | 10 Mbps bajada / 5 Mbps subida | 25 Mbps bajada / 10 Mbps subida |

### Software requerido

| Aplicación | Versión mínima | Verificación |
|---|---|---|
| Microsoft Excel | M365 Apps 2401 | `Archivo → Cuenta → Acerca de Excel` |
| Microsoft Word | M365 Apps 2401 | `Archivo → Cuenta → Acerca de Word` |
| Microsoft 365 Copilot Chat | Vigente | [m365.cloud.microsoft/chat](https://m365.cloud.microsoft/chat) |
| OneDrive for Business | Cliente sincronizado | Ícono en barra de tareas |
| Microsoft Edge | Versión 120 o superior | `edge://settings/help` |

### Configuración inicial (antes de comenzar)

Ejecuta los siguientes pasos de preparación **antes** de iniciar el Bloque A:

1. Abre el Explorador de archivos y navega a tu carpeta de OneDrive sincronizada.
2. Verifica que existe la carpeta `Copilot-RH-Labs`. Si no existe, créala:
   ```
   OneDrive\Copilot-RH-Labs\
   ```
3. Copia el archivo proporcionado por el instructor dentro de esa carpeta:
   ```
   Dataset_Equipo_Ficticio_Lab03.xlsx
   ```
4. Abre [https://m365.cloud.microsoft/chat](https://m365.cloud.microsoft/chat) en Microsoft Edge con tu cuenta corporativa. Confirma que el ícono de **escudo de protección** (🛡️) esté visible en la interfaz antes de continuar.
5. Deja abiertas simultáneamente: **Excel**, **Word** y la pestaña de **Copilot Chat** en Edge.

---

## 6. Procedimiento Paso a Paso

> 📌 **Organización del laboratorio:**
> - **Bloque A** (Pasos 1–4): Skill Matrix en Excel + DNC en Copilot Chat — *45 minutos*
> - **Bloque B** (Pasos 5–7): Planes de capacitación y materiales en Word — *45 minutos*

---

### BLOQUE A — Matriz de Habilidades y Diagnóstico de Necesidades de Capacitación

---

### Paso 1 — Preparar y formatear el dataset en Excel como Tabla estructurada

**Objetivo:** Transformar el dataset del equipo ficticio en una Tabla de Excel correctamente formateada para que Copilot pueda leerla e interpretarla.

**Instrucciones:**

1. Abre `Dataset_Equipo_Ficticio_Lab03.xlsx` desde la carpeta `Copilot-RH-Labs` en OneDrive. El archivo contiene una hoja llamada `Datos_Equipo` con la siguiente estructura de columnas:

   | Columna | Descripción |
   |---|---|
   | `Colaborador` | Nombre ficticio (ej. Ana Torres) |
   | `Puesto` | Cargo actual |
   | `Antiguedad_años` | Años en la empresa |
   | `Competencia_1` … `Competencia_8` | Calificación actual (1–4) por competencia técnica o conductual |
   | `Nivel_Requerido_C1` … `Nivel_Requerido_C8` | Nivel mínimo requerido por el puesto (1–4) |

2. Selecciona el rango completo de datos (incluyendo encabezados). Usa el atajo:
   ```
   Ctrl + Shift + Fin
   ```
   para extender la selección hasta la última celda con datos.

3. Convierte el rango en Tabla de Excel:
   ```
   Insertar → Tabla → (verificar que "La tabla tiene encabezados" esté marcado) → Aceptar
   ```

4. Renombra la tabla en la pestaña **Diseño de tabla**:
   ```
   Nombre de tabla: Matriz_Habilidades
   ```

5. Guarda el archivo con `Ctrl + S`. Verifica que se guarde en OneDrive (la barra de título debe mostrar el ícono de nube sincronizada).

**Resultado esperado:** El dataset aparece formateado como Tabla de Excel con bandas de color alternadas, filtros automáticos en los encabezados y nombre `Matriz_Habilidades` visible en el cuadro de nombres.

**Verificación:** Haz clic en cualquier celda de la tabla. En la cinta de opciones debe aparecer la pestaña contextual **Diseño de tabla** y el nombre `Matriz_Habilidades` debe estar visible en el campo "Nombre de tabla" (esquina superior izquierda de la cinta, dentro de esa pestaña).

---

### Paso 2 — Usar Copilot en Excel para calcular brechas y generar análisis de la skill matrix

**Objetivo:** Utilizar Copilot en Excel para calcular automáticamente las brechas de competencias, identificar los colaboradores con mayor déficit y obtener un análisis priorizado de necesidades.

**Instrucciones:**

1. Con el archivo Excel abierto y la tabla activa, abre el panel de Copilot:
   ```
   Inicio → Copilot (ícono en la cinta)
   ```
   O usa el atajo de teclado `Alt + Shift + C` si está disponible en tu versión.

2. En el panel de Copilot, escribe el siguiente prompt para calcular las brechas por competencia:

   ```
   Analiza la tabla Matriz_Habilidades. Para cada colaborador, calcula la brecha
   entre el nivel actual y el nivel requerido en cada competencia
   (Brecha = Nivel_Requerido - Competencia_actual). Si la brecha es negativa o cero,
   muéstrala como 0 (no hay brecha). Agrega columnas de brecha calculadas
   al final de la tabla para cada competencia.
   ```

3. Revisa las columnas de brecha generadas. Copilot puede proponer fórmulas como:
   ```excel
   =MAX(0, [@[Nivel_Requerido_C1]] - [@[Competencia_1]])
   ```
   Acepta la propuesta haciendo clic en **Insertar columnas**.

4. Una vez generadas las columnas de brecha, escribe un segundo prompt para obtener un resumen priorizado:

   ```
   Con base en las columnas de brecha recién calculadas, identifica:
   1. Las tres competencias con mayor brecha promedio en el equipo.
   2. Los dos colaboradores con la brecha total más alta (suma de todas sus brechas).
   3. Las competencias donde ningún colaborador tiene brecha (dominio completo del equipo).
   Presenta los resultados en formato de lista numerada con los valores exactos.
   ```

5. Copia el texto de respuesta de Copilot y pégalo en una nueva hoja llamada `Análisis_DNC` dentro del mismo archivo (clic derecho en la pestaña → Insertar hoja).

6. Ahora aplica formato condicional para crear el **heatmap de brechas**. Selecciona únicamente las columnas de brecha calculadas (por ejemplo, `Brecha_C1` hasta `Brecha_C8`). Luego pide a Copilot:

   ```
   Aplica formato condicional de escala de color a las columnas de brecha
   seleccionadas: verde para brecha = 0, amarillo para brecha = 1,
   naranja para brecha = 2 y rojo para brecha = 3 o más.
   ```

   > 💡 **Nota:** Si Copilot no puede aplicar el formato condicional directamente, hazlo manualmente: `Inicio → Formato condicional → Escalas de color`. Elige la escala verde-amarillo-rojo y ajusta los valores de umbral manualmente.

7. Guarda el archivo con `Ctrl + S`.

**Resultado esperado:** La tabla `Matriz_Habilidades` tiene columnas adicionales de brecha por competencia. La hoja `Análisis_DNC` contiene el resumen textual con las tres competencias críticas, los dos colaboradores con mayor déficit y las competencias sin brecha. El heatmap muestra visualmente en rojo las brechas más críticas.

**Verificación:** Selecciona la celda de brecha de un colaborador y verifica manualmente que la fórmula sea `=MAX(0, Nivel_Requerido - Nivel_Actual)`. El heatmap debe mostrar al menos dos celdas en rojo si el dataset tiene brechas de 3 o más puntos.

---

### Paso 3 — Redactar el DNC formal con Copilot Chat

**Objetivo:** Utilizar Copilot Chat para transformar los datos de la skill matrix en un Diagnóstico de Necesidades de Capacitación (DNC) estructurado, con análisis de causa raíz, impacto organizacional y propuesta de intervenciones.

**Instrucciones:**

1. Abre la pestaña de **Copilot Chat** en Microsoft Edge ([m365.cloud.microsoft/chat](https://m365.cloud.microsoft/chat)). Verifica que el ícono de escudo esté activo.

2. Inicia una nueva conversación. Escribe el siguiente prompt de contexto inicial:

   ```
   Actúa como especialista senior en Recursos Humanos con experiencia en
   diagnóstico de necesidades de capacitación (DNC) para empresas medianas.
   Voy a proporcionarte los resultados de una skill matrix de un equipo ficticio
   de 8 personas y necesito que redactes un DNC formal.
   ```

3. En el siguiente mensaje, proporciona los datos del análisis (copia los resultados que pegaste en la hoja `Análisis_DNC`):

   ```
   Aquí están los resultados del análisis de la skill matrix del equipo ficticio:

   [PEGA AQUÍ EL CONTENIDO DE LA HOJA Análisis_DNC:
    - Las tres competencias con mayor brecha promedio
    - Los dos colaboradores con mayor déficit
    - Las competencias sin brecha]

   El equipo pertenece al área de Operaciones de una empresa de servicios
   financieros con 200 empleados en México. El objetivo estratégico del área
   para este año es reducir el tiempo de procesamiento de operaciones en un 20 %
   y mejorar la satisfacción del cliente interno en un 15 %.
   ```

4. Solicita el DNC estructurado con este prompt:

   ```
   Con base en estos datos, redacta un DNC formal que incluya las siguientes secciones:

   1. Resumen ejecutivo (máximo 100 palabras)
   2. Metodología de diagnóstico (cómo se obtuvo la información)
   3. Hallazgos principales (tabla con: Competencia | Brecha Promedio | Nivel de Criticidad | Impacto en Objetivos)
   4. Análisis de causa raíz de las tres brechas críticas (usa el formato: Brecha → Posible causa → Evidencia)
   5. Propuesta de intervenciones priorizadas (tabla con: Intervención | Modalidad | Colaboradores objetivo | Plazo | Prioridad Alta/Media/Baja)
   6. Indicadores de éxito (KPIs para medir el impacto del plan de capacitación)

   Formato: Documento formal en español, tono profesional, listo para presentar a la Dirección.
   ```

5. Una vez generado el DNC, solicita un refinamiento:

   ```
   En la sección de propuesta de intervenciones, asegúrate de incluir al menos
   una modalidad de cada tipo: e-learning, taller presencial, mentoring interno
   y aprendizaje en el puesto (on-the-job). Ajusta el plazo de implementación
   para que todo el plan se ejecute en un periodo de 6 meses.
   ```

6. Copia el texto completo del DNC generado. Abre un nuevo documento de Word en blanco, guárdalo como `DNC_Equipo_Operaciones_Lab03.docx` en la carpeta `Copilot-RH-Labs` de OneDrive y pega el contenido.

7. Aplica estilos de Word para estructurar el documento:
   - Título del documento: **Título** (estilo Word)
   - Secciones numeradas: **Título 1**
   - Subtítulos dentro de secciones: **Título 2**

8. Guarda el documento con `Ctrl + S`.

**Resultado esperado:** Documento `DNC_Equipo_Operaciones_Lab03.docx` con las seis secciones formales del DNC, incluyendo tablas de hallazgos e intervenciones, análisis de causa raíz de tres brechas y KPIs de éxito. El documento tiene una extensión aproximada de 2–3 páginas con formato profesional.

**Verificación:** El DNC debe contener al menos: (a) una tabla de hallazgos con nivel de criticidad, (b) una tabla de intervenciones con las cuatro modalidades solicitadas y (c) al menos tres KPIs medibles con línea base y meta.

---

### Paso 4 — Validar y enriquecer el DNC con análisis adicional de Copilot Chat

**Objetivo:** Aplicar técnicas de refinamiento iterativo de prompts para mejorar la calidad del DNC y añadir valor estratégico al documento.

**Instrucciones:**

1. En la misma conversación de Copilot Chat, solicita una revisión crítica del DNC:

   ```
   Actúa ahora como Director de Recursos Humanos que revisará este DNC antes
   de presentarlo al Comité Directivo. Identifica:
   - Tres fortalezas del diagnóstico tal como está redactado.
   - Dos debilidades o vacíos de información que debería reforzarse.
   - Una recomendación de alto impacto que no está incluida actualmente.
   ```

2. Incorpora la recomendación de alto impacto al documento Word. Usa Copilot en Word para hacerlo: abre el documento, selecciona la sección de "Propuesta de intervenciones" y en el panel de Copilot de Word escribe:

   ```
   Agrega un párrafo de cierre a esta sección que incluya la siguiente
   recomendación de alto impacto: [pega aquí la recomendación generada
   en Copilot Chat]. Mantén el tono formal del documento.
   ```

3. Guarda el documento actualizado con `Ctrl + S`.

**Resultado esperado:** El DNC incorpora la recomendación de alto impacto identificada en el análisis crítico. El documento refleja un ciclo de refinamiento iterativo que eleva su calidad estratégica.

**Verificación:** El documento Word debe mostrar el párrafo de cierre añadido en la sección de intervenciones, coherente con el tono y formato del resto del documento.

---

### BLOQUE B — Planes de Capacitación y Materiales Didácticos

---

### Paso 5 — Diseñar planes de capacitación individualizados en Word con Copilot

**Objetivo:** Crear en Word planes de capacitación formales para dos perfiles del equipo ficticio, utilizando Copilot para generar objetivos de aprendizaje SMART, selección de modalidades, cronograma y KPIs.

**Instrucciones:**

1. Abre un nuevo documento de Word en blanco. Guárdalo como `Plan_Capacitacion_Lab03.docx` en la carpeta `Copilot-RH-Labs` de OneDrive.

2. Abre el panel de Copilot en Word:
   ```
   Inicio → Copilot (ícono en la cinta)
   ```

3. En el panel de Copilot de Word, escribe el siguiente prompt para generar el plan del **Perfil 1** (colaborador con mayor brecha identificado en el Paso 2):

   ```
   Redacta un plan de capacitación individualizado para el siguiente perfil ficticio:

   Nombre: [usa el nombre del colaborador con mayor brecha de tu análisis]
   Puesto: Analista de Operaciones
   Brechas identificadas: [inserta las competencias con brecha del colaborador]
   Objetivo del área: Reducir tiempo de procesamiento 20 % en 12 meses.

   El plan debe incluir:
   1. Encabezado con datos del colaborador y fecha de elaboración
   2. Diagnóstico individual (resumen de brechas en 3 líneas)
   3. Tres objetivos de aprendizaje SMART (Específico, Medible, Alcanzable,
      Relevante, Temporal) alineados a las brechas críticas
   4. Ruta de aprendizaje con tabla: Módulo | Competencia que desarrolla |
      Modalidad | Duración | Fecha tentativa | Responsable
   5. Recursos recomendados (plataformas, materiales, mentores internos)
   6. KPIs de efectividad del plan (mínimo 3, con línea base y meta)
   7. Firma de compromiso: colaborador, líder directo y RH

   Formato: Documento Word formal, con secciones numeradas y tablas donde aplique.
   Extensión aproximada: 2 páginas.
   ```

4. Revisa el contenido generado. Si alguna modalidad no está incluida, usa un prompt de seguimiento:

   ```
   En la ruta de aprendizaje, asegúrate de incluir al menos una actividad
   de mentoring interno y una de aprendizaje en el puesto (on-the-job training).
   Especifica el nombre ficticio del mentor y la actividad concreta de OJT.
   ```

5. Para el **Perfil 2** (un colaborador con perfil de liderazgo, por ejemplo el Supervisor de Operaciones), escribe un nuevo prompt en el mismo documento de Word (coloca el cursor al final del documento):

   ```
   Ahora redacta un segundo plan de capacitación para el siguiente perfil:

   Nombre: Carlos Mendoza (ficticio)
   Puesto: Supervisor de Operaciones
   Brechas identificadas: Liderazgo de equipos (nivel actual 2, requerido 4),
   Gestión de conflictos (nivel actual 1, requerido 3),
   Análisis de datos operativos (nivel actual 2, requerido 3).
   Objetivo: Preparar al colaborador para asumir responsabilidades de
   Gerencia en un horizonte de 18 meses.

   Usa la misma estructura del plan anterior (secciones 1–7).
   Adapta las modalidades al perfil de liderazgo: incluye coaching ejecutivo,
   programa de shadowing con el Gerente actual y un proyecto de mejora asignado.
   ```

6. Agrega una página de portada al documento. En el panel de Copilot de Word:

   ```
   Genera el texto para una portada profesional de este documento que incluya:
   título "Planes de Capacitación Individualizados — Equipo de Operaciones",
   subtítulo con el periodo de vigencia (año en curso), nombre de la empresa
   ficticia "Servicios Financieros Nexo S.A. de C.V.", versión 1.0 y fecha.
   ```

7. Inserta la portada manualmente al inicio del documento y pega el texto generado. Aplica el estilo **Título** de Word al nombre del documento.

8. Guarda con `Ctrl + S`.

**Resultado esperado:** Documento `Plan_Capacitacion_Lab03.docx` con portada y dos planes de capacitación individualizados (Analista de Operaciones y Supervisor de Operaciones), cada uno con objetivos SMART, ruta de aprendizaje en tabla, recursos, KPIs y sección de firma de compromiso. Extensión total aproximada: 5–6 páginas.

**Verificación:** Cada plan debe contener: (a) exactamente tres objetivos SMART redactados en formato "Al finalizar [plazo], [colaborador] será capaz de [verbo medible] [resultado] en [contexto]", (b) al menos cuatro modalidades distintas de aprendizaje en la ruta, y (c) tres KPIs con línea base numérica y meta cuantificada.

---

### Paso 6 — Crear la guía de onboarding aplicando el modelo de las 4 C

**Objetivo:** Diseñar una guía de bienvenida de dos páginas para nuevos integrantes del equipo de Operaciones, aplicando el modelo de las 4 C (Compliance, Clarification, Culture, Connection) con asistencia de Copilot en Word.

**Instrucciones:**

1. Abre un nuevo documento de Word en blanco. Guárdalo como `Guia_Onboarding_Operaciones_Lab03.docx` en `Copilot-RH-Labs`.

2. En el panel de Copilot de Word, escribe el siguiente prompt:

   ```
   Actúa como especialista en diseño de onboarding. Redacta una guía de bienvenida
   de dos páginas para nuevos colaboradores del equipo de Operaciones de la empresa
   ficticia "Servicios Financieros Nexo S.A. de C.V."

   La guía debe estructurarse usando el modelo de las 4 C:

   1. COMPLIANCE (Cumplimiento): Lista de trámites administrativos y políticas
      clave que el colaborador debe completar en los primeros 3 días.
      Incluye: alta en sistemas, firma de políticas de datos, accesos a plataformas.

   2. CLARIFICATION (Claridad): Descripción de las expectativas del rol en los
      primeros 30-60-90 días. Incluye una tabla con metas por periodo.

   3. CULTURE (Cultura): Presentación de los valores de la empresa, la forma de
      trabajar del equipo y las tradiciones del área (ej. reunión semanal de equipo,
      celebración de logros, canal de comunicación principal).

   4. CONNECTION (Conexión): Mapa de personas clave a conocer en la primera semana,
      incluyendo el nombre del buddy asignado (ficticio), el líder directo y
      dos stakeholders internos relevantes.

   Formato: Documento visual y amigable, con íconos textuales (→, ✓, ★),
   subtítulos claros, listas de verificación y una sección final de
   "Primeros 5 días: tu itinerario de bienvenida" con actividades día a día.
   Tono: Cálido, motivador y profesional. Extensión: exactamente 2 páginas.
   ```

3. Revisa el contenido generado. Solicita ajustes con un prompt de refinamiento:

   ```
   En la sección de CONNECTION, agrega una tabla con el siguiente formato:
   Persona | Puesto | Por qué conocerla | Cuándo reunirte
   Incluye al menos 5 personas ficticias relevantes para el nuevo colaborador.
   ```

4. Añade un elemento de employer branding al final de la guía. En el panel de Copilot:

   ```
   Agrega un párrafo final de bienvenida emocional (máximo 80 palabras) que
   refuerce la EVP de la empresa. La propuesta de valor al empleado de Nexo
   se basa en tres pilares: desarrollo profesional acelerado, cultura de
   colaboración y propósito social (acceso a servicios financieros inclusivos).
   El tono debe ser inspirador y auténtico, como si lo escribiera el Director
   de Operaciones personalmente.
   ```

5. Guarda el documento con `Ctrl + S`.

**Resultado esperado:** Documento `Guia_Onboarding_Operaciones_Lab03.docx` de dos páginas con las cuatro dimensiones del modelo de las 4 C claramente estructuradas, itinerario de los primeros 5 días, tabla de personas clave y párrafo de bienvenida con EVP. El documento tiene un tono cálido y visual, apto para entregar físicamente o compartir digitalmente al nuevo colaborador.

**Verificación:** El documento debe contener exactamente cuatro secciones tituladas con las dimensiones del modelo (Compliance, Clarification, Culture, Connection), al menos una lista de verificación (checklist), la tabla de personas clave con 5 entradas y el párrafo final de EVP.

---

### Paso 7 — Generar mensaje de employer branding interno para comunicar el programa de desarrollo

**Objetivo:** Crear materiales de comunicación interna que anuncien el programa de capacitación al equipo, utilizando Copilot Chat para generar mensajes alineados con la EVP y la cultura organizacional.

**Instrucciones:**

1. Regresa a la pestaña de **Copilot Chat** en Edge. Inicia una nueva conversación.

2. Escribe el siguiente prompt para generar el mensaje de comunicación interna:

   ```
   Actúa como especialista en comunicación interna y employer branding.
   Redacta los siguientes materiales para anunciar el nuevo programa de
   desarrollo y capacitación del equipo de Operaciones de "Servicios
   Financieros Nexo S.A. de C.V.":

   MATERIAL 1: Correo electrónico del Director de Operaciones al equipo
   - Asunto atractivo
   - Máximo 200 palabras
   - Menciona los beneficios del programa (no los detalles técnicos)
   - Incluye llamada a la acción: agendar reunión individual con RH
   - Tono: cercano, motivador, sin corporativismo excesivo

   MATERIAL 2: Mensaje para el canal de Teams del equipo
   - Máximo 100 palabras
   - Formato: emoji + texto corto + enlace ficticio al plan
   - Tono: dinámico y conversacional

   MATERIAL 3: Frase inspiracional para el fondo de pantalla del equipo
   - Máximo 15 palabras
   - Relacionada con el desarrollo profesional y el propósito de la empresa
   - Sin clichés corporativos

   Contexto EVP: desarrollo acelerado, colaboración y propósito social.
   ```

3. Revisa los tres materiales generados. Si el correo supera las 200 palabras, solicita:

   ```
   El correo tiene más de 200 palabras. Condensalo manteniendo el tono
   motivador y la llamada a la acción. Elimina cualquier frase genérica
   que no aporte valor específico al mensaje.
   ```

4. Abre el documento `Plan_Capacitacion_Lab03.docx` en Word. Al final del documento, añade una nueva sección titulada **"Estrategia de Comunicación Interna"** y pega los tres materiales generados.

5. Aplica el estilo **Título 1** al encabezado de la nueva sección y **Título 2** a cada material (Material 1, Material 2, Material 3).

6. Realiza una revisión final del documento completo con Copilot en Word:

   ```
   Revisa la coherencia y el tono de todo el documento. Identifica si hay
   alguna sección donde el tono sea inconsistente con el resto o donde
   la información esté incompleta. Sugiere tres mejoras concretas.
   ```

7. Implementa al menos una de las mejoras sugeridas y guarda el documento con `Ctrl + S`.

**Resultado esperado:** El documento `Plan_Capacitacion_Lab03.docx` incluye ahora una sección final de comunicación interna con los tres materiales (correo, mensaje de Teams y frase inspiracional) listos para usar. El documento completo es coherente en tono y estructura.

**Verificación:** El correo no supera 200 palabras, el mensaje de Teams no supera 100 palabras y la frase inspiracional no supera 15 palabras. Los tres materiales mencionan al menos uno de los tres pilares de la EVP.

---

## 7. Validación y Pruebas

Al finalizar los siete pasos, completa la siguiente lista de verificación para confirmar que todos los entregables están correctos:

| # | Entregable | Criterio de validación | ✓ |
|---|---|---|---|
| 1 | `Dataset_Equipo_Ficticio_Lab03.xlsx` | Tabla `Matriz_Habilidades` con columnas de brecha calculadas y heatmap de colores aplicado | ☐ |
| 2 | Hoja `Análisis_DNC` en Excel | Contiene resumen con 3 competencias críticas, 2 colaboradores con mayor déficit y competencias sin brecha | ☐ |
| 3 | `DNC_Equipo_Operaciones_Lab03.docx` | 6 secciones formales incluyendo tablas de hallazgos, intervenciones con 4 modalidades y 3+ KPIs | ☐ |
| 4 | `Plan_Capacitacion_Lab03.docx` — Perfil 1 | 3 objetivos SMART, 4+ modalidades en ruta de aprendizaje, 3 KPIs con línea base y meta | ☐ |
| 5 | `Plan_Capacitacion_Lab03.docx` — Perfil 2 | Incluye coaching ejecutivo, shadowing y proyecto de mejora; orientado a perfil de liderazgo | ☐ |
| 6 | `Guia_Onboarding_Operaciones_Lab03.docx` | Exactamente 2 páginas con las 4 dimensiones del modelo de las 4 C, itinerario de 5 días y tabla de 5 personas clave | ☐ |
| 7 | Sección de comunicación interna en Word | Correo ≤200 palabras, mensaje Teams ≤100 palabras, frase ≤15 palabras; todos mencionan EVP | ☐ |
| 8 | Todos los archivos | Guardados en `OneDrive\Copilot-RH-Labs\` y sincronizados (ícono de nube visible) | ☐ |

**Prueba de integridad del heatmap:**
1. En Excel, filtra la tabla `Matriz_Habilidades` por los dos colaboradores con mayor brecha.
2. Verifica que sus celdas de brecha muestren color rojo o naranja consistentemente.
3. Filtra por un colaborador sin brechas (si existe en el dataset) y confirma que todas sus celdas de brecha sean verdes.

**Prueba de coherencia del DNC:**
1. Abre `DNC_Equipo_Operaciones_Lab03.docx`.
2. Verifica que las competencias listadas en la sección de "Hallazgos principales" coincidan con las brechas identificadas en la hoja `Análisis_DNC` de Excel.
3. Confirma que las intervenciones propuestas en el DNC correspondan a las mismas competencias críticas.

---

## 8. Solución de Problemas

### Problema 1 — Copilot en Excel no puede leer la tabla o genera fórmulas incorrectas

**Síntoma:** Al escribir el prompt en el panel de Copilot de Excel, el sistema responde con un mensaje de error como *"No puedo analizar los datos"* o genera fórmulas que hacen referencia a columnas inexistentes.

**Causa probable:** La tabla no está correctamente formateada como Tabla de Excel (el rango es solo un rango de celdas sin estructura de tabla), los encabezados contienen caracteres especiales o espacios al inicio/final, o el archivo no está guardado en OneDrive (Copilot en Excel requiere que el archivo esté en la nube para funcionar correctamente).

**Solución:**
1. Verifica que el archivo esté guardado en OneDrive: la barra de título debe mostrar la ruta de OneDrive, no una ruta local (`C:\...`). Si está local, usa `Archivo → Guardar una copia → OneDrive`.
2. Haz clic dentro de la tabla y revisa en la cinta **Diseño de tabla** que el nombre `Matriz_Habilidades` esté asignado.
3. Revisa los encabezados: selecciona la fila de encabezados y usa `Ctrl + H` para reemplazar cualquier espacio al inicio por nada. Evita caracteres como `/`, `(`, `)` en los nombres de columna.
4. Si el problema persiste, cierra y vuelve a abrir el archivo desde OneDrive (no desde el historial reciente), espera 30 segundos y reintenta el prompt.

---

### Problema 2 — Copilot Chat genera un DNC o plan de capacitación genérico sin personalización al contexto del equipo

**Síntoma:** El DNC o el plan de capacitación generado contiene información genérica (ej. "el equipo necesita mejorar sus habilidades de comunicación" sin referencias a las brechas específicas del dataset) o no refleja los datos proporcionados en el prompt.

**Causa probable:** El prompt no incluyó los datos numéricos de las brechas de forma explícita, o se proporcionaron en un formato que Copilot no pudo interpretar correctamente (ej. imagen en lugar de texto, tabla mal copiada). También puede ocurrir si la conversación es muy larga y Copilot "perdió" el contexto de los mensajes anteriores.

**Solución:**
1. Inicia una **nueva conversación** en Copilot Chat (botón "Nueva conversación" o `+`).
2. En el primer mensaje, incluye los datos de brechas en formato de lista de texto plano, no como tabla copiada de Excel. Por ejemplo:
   ```
   Datos del equipo:
   - Ana Torres: Brecha en Análisis de Datos = 3, Brecha en Gestión de Proyectos = 2
   - Luis Pérez: Brecha en Comunicación Ejecutiva = 3, Brecha en Excel Avanzado = 1
   [... continúa con todos los colaboradores ...]
   ```
3. Especifica explícitamente en el prompt: *"Usa únicamente los datos que te proporciono a continuación. No uses ejemplos genéricos."*
4. Si el output sigue siendo genérico, agrega al final del prompt: *"Cita al menos dos nombres de colaboradores ficticios del listado anterior en cada sección del documento."*

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realiza los siguientes pasos de limpieza y organización:

1. **Organiza los archivos en OneDrive.** Crea una subcarpeta dentro de `Copilot-RH-Labs`:
   ```
   OneDrive\Copilot-RH-Labs\Lab03\
   ```
   Mueve los tres archivos de entregable a esta carpeta:
   - `Dataset_Equipo_Ficticio_Lab03.xlsx`
   - `DNC_Equipo_Operaciones_Lab03.docx`
   - `Plan_Capacitacion_Lab03.docx`
   - `Guia_Onboarding_Operaciones_Lab03.docx`

2. **Verifica la sincronización.** Espera a que el ícono de OneDrive en la barra de tareas muestre el estado de sincronización completa (palomita verde o ícono en reposo). Confirma que los archivos son visibles en [onedrive.live.com](https://onedrive.live.com) desde el navegador.

3. **Cierra las conversaciones de Copilot Chat.** No es necesario eliminarlas, pero cierra las pestañas activas del navegador para liberar memoria.

4. **Cierra Excel y Word.** Usa `Archivo → Cerrar` en cada aplicación para asegurarte de que los archivos se guardaron correctamente antes de cerrar.

5. **No compartas los archivos externamente.** Los documentos generados contienen datos ficticios de colaboradores. Aunque son ficticios, mantén los archivos dentro del tenant corporativo y no los compartas por canales no seguros.

---

## 10. Resumen y Recursos Adicionales

### Resumen del Laboratorio

En esta práctica completaste el ciclo completo de identificación de brechas y diseño de intervenciones de desarrollo para un equipo ficticio:

| Bloque | Actividad | Herramienta | Entregable |
|---|---|---|---|
| **A** | Skill matrix con cálculo de brechas y heatmap | Copilot en Excel | `Dataset_Equipo_Ficticio_Lab03.xlsx` |
| **A** | DNC formal con análisis de causa raíz e intervenciones | Copilot Chat | `DNC_Equipo_Operaciones_Lab03.docx` |
| **B** | Planes de capacitación individualizados (2 perfiles) | Copilot en Word | `Plan_Capacitacion_Lab03.docx` |
| **B** | Guía de onboarding con modelo 4 C y EVP | Copilot en Word | `Guia_Onboarding_Operaciones_Lab03.docx` |
| **B** | Materiales de employer branding interno | Copilot Chat + Word | Sección en `Plan_Capacitacion_Lab03.docx` |

### Conceptos Clave Aplicados

- **Modelo de las 4 C** (Bauer): Compliance, Clarification, Culture, Connection — estructura base de la guía de onboarding.
- **Prompting contextualizado**: Rol + Contexto + Tarea + Formato = outputs de mayor calidad y menor necesidad de corrección.
- **Refinamiento iterativo**: Cada entregable fue mejorado con al menos un prompt de seguimiento, demostrando que la calidad de los outputs de Copilot mejora progresivamente con la iteración.
- **Objetivos SMART**: Específico, Medible, Alcanzable, Relevante, Temporal — aplicados en los planes de capacitación para garantizar su operacionalización.
- **EVP (Employee Value Proposition)**: Integrada en la guía de onboarding y los materiales de comunicación interna como elemento de employer branding.

### Recursos Adicionales

| Recurso | URL |
|---|---|
| Bauer, T. N. — *Onboarding New Employees: Maximizing Success* (SHRM Foundation) | [shrm.org/topics-tools/toolkits/onboarding-new-employees](https://www.shrm.org/topics-tools/toolkits/onboarding-new-employees) |
| Microsoft Copilot en Excel — Documentación oficial | [learn.microsoft.com/es-es/copilot/microsoft-365](https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview) |
| LinkedIn Talent Solutions — Guía de Employer Branding | [business.linkedin.com/es-es/talent-solutions](https://business.linkedin.com/es-es/talent-solutions/resources/talent-acquisition/employer-branding) |
| SHRM — Employee Value Proposition | [shrm.org/topics-tools/topics/employee-value-proposition](https://www.shrm.org/topics-tools/topics/employee-value-proposition) |
| Brandon Hall Group — Impacto del onboarding en retención | [brandonhall.com/solution/talent-acquisition](https://brandonhall.com/solution/talent-acquisition/) |

---

> 🎯 **Conexión con la siguiente práctica:** En el **Lab 04**, aplicarás los planes de capacitación generados en esta práctica para diseñar un tablero de control de desarrollo de talento en Excel y Power BI, visualizando el avance del equipo contra los KPIs definidos en el DNC. Los archivos de esta práctica son insumos directos para ese laboratorio.

---
LAB_END---
