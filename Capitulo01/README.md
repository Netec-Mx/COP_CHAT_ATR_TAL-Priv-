# Práctica 1 — Generación de Descriptivos de Puesto y Prompts de Búsqueda para Candidatos

## Metadatos

| Atributo | Valor |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Básica |
| **Nivel Bloom** | Aplicar (Apply) |
| **Módulo** | Módulo 1 — Fundamentos de Copilot en RH |
| **Herramientas principales** | Copilot Chat · Copilot en Word · OneDrive for Business |
| **Última revisión** | 2025 |

---

## Descripción General

En este laboratorio aplicarás los cuatro pilares del prompting efectivo —**Rol, Contexto, Tarea específica y Tono/Formato**— para generar descriptivos de puesto estructurados y strings de búsqueda booleana asistidos por Microsoft Copilot Chat. Trabajarás con dos roles ficticios (uno técnico y uno de gestión) y seguirás una metodología de prompting progresivo: prompt base → refinamiento → prompt avanzado con restricciones. Al finalizar, habrás construido artefactos de RH de alta calidad, guardados en Word dentro de tu OneDrive, que demuestran la diferencia práctica entre un prompt débil y uno bien estructurado.

> ⚠️ **Recordatorio de privacidad:** Todos los perfiles, nombres y datos utilizados en este laboratorio deben ser **completamente ficticios**. No ingreses información personal real de candidatos o colaboradores en Copilot Chat bajo ninguna circunstancia.

---

## Objetivos de Aprendizaje

Al completar este laboratorio serás capaz de:

- [ ] Construir descriptivos de puesto estructurados aplicando los cuatro pilares del prompting efectivo (Rol, Contexto, Tarea, Tono/Formato) en Copilot Chat.
- [ ] Aplicar la metodología de prompting progresivo (prompt base → refinamiento → prompt avanzado) y evaluar la mejora en la calidad de los outputs obtenidos.
- [ ] Diseñar strings de búsqueda booleana y prompts de sourcing para plataformas de reclutamiento con asistencia de Copilot.
- [ ] Transferir los artefactos generados en Copilot Chat a Microsoft Word y guardarlos correctamente en OneDrive for Business.

---

## Prerrequisitos

### Conocimiento previo
- Haber leído el material del **Módulo 1, Lección 1.1** (Introducción a Copilot en RH y buenas prácticas de prompting).
- Comprensión básica de la estructura de un descriptivo de puesto (objetivo, responsabilidades, perfil requerido, métricas de éxito).
- Familiaridad con el concepto de búsqueda booleana (operadores AND, OR, NOT).

### Acceso y configuración
- Cuenta corporativa Microsoft 365 con **licencia Copilot activa y verificada** por TI.
- Sesión iniciada en [copilot.microsoft.com](https://copilot.microsoft.com) con la cuenta corporativa (no personal). El **ícono de escudo de protección** debe ser visible en la interfaz.
- Microsoft Word (Microsoft 365 Apps, versión 2401 o superior) instalado y con Copilot habilitado en la cinta de opciones.
- OneDrive for Business sincronizado y accesible.
- Carpeta **`Copilot-RH-Labs`** creada previamente en OneDrive for Business.
- Navegador Microsoft Edge versión 120 o superior.

---

## Entorno del Laboratorio

### Hardware recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 / AMD Ryzen 5 (8.ª gen) | i7 / Ryzen 7 |
| RAM | 8 GB | 16 GB |
| Almacenamiento libre | 5 GB | 10 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px |
| Conexión a internet | 10 Mbps bajada / 5 Mbps subida | 25 Mbps |

### Software requerido

| Aplicación | Versión mínima | Propósito en este lab |
|---|---|---|
| Microsoft Edge | 120 | Acceso a Copilot Chat |
| Copilot Chat | Versión empresarial vigente | Generación de prompts y descriptivos |
| Microsoft Word | M365 Apps 2401+ | Edición y almacenamiento de artefactos |
| OneDrive for Business | Cliente sincronizado M365 | Guardado de entregables |

### Verificación del entorno (ejecutar antes de comenzar)

Abre una ventana de Edge y navega a la siguiente URL para confirmar que tu sesión de Copilot está activa con tu cuenta corporativa:

```
https://copilot.microsoft.com
```

Confirma los siguientes puntos antes de avanzar:

```
✅ La URL muestra "copilot.microsoft.com" (no "bing.com/chat")
✅ En la esquina superior derecha aparece tu avatar/iniciales corporativas
✅ Es visible el ícono de escudo o candado de "Protección de datos empresariales"
✅ Word está abierto y la pestaña "Inicio" muestra el botón "Copilot" en la cinta
✅ OneDrive muestra la carpeta "Copilot-RH-Labs" en el panel izquierdo
```

> 💡 **Nota del instructor:** Si el ícono de escudo no es visible, el participante puede estar usando una cuenta personal. Detener y corregir antes de continuar.

---

## Instrucciones Paso a Paso

---

### Parte A — Análisis de Prompts: De lo Básico a lo Avanzado (10 minutos)

**Objetivo de esta parte:** Internalizar la diferencia entre un prompt débil y un prompt estructurado antes de generar los artefactos principales, utilizando los cuatro pilares aprendidos en la Lección 1.1.

---

#### Paso A-1: Abrir Copilot Chat y explorar el entorno

**Objetivo:** Familiarizarte con la interfaz de Copilot Chat empresarial e identificar los controles de privacidad.

**Instrucciones:**

1. En Microsoft Edge, navega a `https://copilot.microsoft.com`.
2. Confirma que tu sesión esté iniciada con tu cuenta corporativa (verifica las iniciales o avatar en la esquina superior derecha).
3. Localiza el **ícono de escudo** (🛡️) o la etiqueta "Protección de datos empresariales" en la interfaz. Toma nota mental de su ubicación — esta indicación garantiza que tus conversaciones permanecen dentro del tenant de tu organización.
4. Observa el campo de texto en la parte inferior. Este es el área donde ingresarás tus prompts.
5. Si existe un historial de conversaciones anterior, haz clic en **"Nueva conversación"** (o el equivalente en tu interfaz) para iniciar con un hilo limpio.

**Salida esperada:** Interfaz de Copilot Chat abierta, con sesión corporativa activa y el indicador de protección de datos visible.

**Verificación:** El campo de texto inferior está activo y listo para recibir input. No hay mensajes de error de autenticación.

---

#### Paso A-2: Ejecutar un prompt débil y documentar el resultado

**Objetivo:** Experimentar de primera mano la limitación de un prompt sin estructura para establecer una línea base de comparación.

**Instrucciones:**

1. En el campo de texto de Copilot Chat, escribe exactamente el siguiente prompt débil y presiona **Enter** o el botón de envío:

```
Escribe una descripción de puesto para analista de datos.
```

2. Lee la respuesta completa que genera Copilot.
3. Evalúa mentalmente (o en una hoja de notas) los siguientes criterios:
   - ¿Menciona un sector de industria específico?
   - ¿Incluye métricas de éxito o KPIs del rol?
   - ¿El tono es apropiado para el tipo de empresa que tú conoces?
   - ¿Podría aplicarse a cualquier empresa del mundo sin cambiar una sola palabra?
4. **No copies** esta respuesta a Word todavía. Es únicamente una referencia comparativa.

**Salida esperada:** Una descripción de puesto genérica, probablemente válida pero sin diferenciadores, sin contexto de industria y con estructura variable.

**Verificación:** Identificas al menos 3 elementos que hacen la respuesta demasiado genérica para ser usada directamente en un proceso real de reclutamiento.

---

#### Paso A-3: Ejecutar el prompt optimizado con los cuatro pilares y comparar

**Objetivo:** Demostrar el impacto inmediato de aplicar los cuatro pilares (Rol, Contexto, Tarea, Tono/Formato) en la calidad del output.

**Instrucciones:**

1. Haz clic en **"Nueva conversación"** para limpiar el contexto anterior.
2. Ingresa el siguiente prompt optimizado (puedes copiarlo y adaptarlo):

```
Actúa como un especialista en atracción de talento con 10 años 
de experiencia en el sector financiero en México. 

Redacta una descripción de puesto atractiva y clara para el rol 
de Analista de Datos Jr. en una institución bancaria mediana 
(500-1,000 empleados). 

Estructura la descripción con las siguientes secciones:
1. Objetivo del puesto (2-3 oraciones)
2. Responsabilidades principales (5 viñetas)
3. Perfil requerido:
   - Nivel educativo
   - Años de experiencia
   - Habilidades técnicas (mínimo 4)
   - Competencias conductuales (mínimo 3)
4. Propuesta de valor para el candidato (1 párrafo)

Tono: profesional pero cercano. 
Restricción: no incluyas rangos salariales ni beneficios específicos.
```

3. Lee la respuesta completa.
4. Compara mentalmente con la respuesta del Paso A-2 usando los mismos criterios.

**Salida esperada:** Una descripción de puesto estructurada, con contexto de industria (sector financiero, México), tono definido y todas las secciones solicitadas claramente diferenciadas.

**Verificación:** La respuesta incluye las 4 secciones estructuradas, menciona el contexto de institución bancaria y el tono se percibe diferente al del prompt débil. Si alguna sección está ausente, procede al Paso A-4.

---

#### Paso A-4 (Condicional): Refinamiento del prompt si el output está incompleto

**Objetivo:** Practicar el refinamiento iterativo cuando el primer output no cumple todos los criterios.

**Instrucciones:**

> Ejecuta este paso **solo si** en el Paso A-3 Copilot omitió alguna sección o el tono no fue el esperado.

1. **Sin abrir una nueva conversación** (para mantener el contexto), escribe un prompt de refinamiento como el siguiente, adaptándolo a lo que haya faltado:

```
La respuesta anterior está bien, pero falta la sección de 
"Propuesta de valor para el candidato". Por favor, agrega 
ese párrafo al final del descriptivo manteniendo el mismo 
tono profesional pero cercano.
```

O si el tono no fue adecuado:

```
Reescribe la misma descripción pero con un tono más dinámico 
y orientado a atraer a candidatos de la Generación Z que 
buscan propósito en su trabajo, sin perder la estructura 
de las 4 secciones.
```

2. Evalúa el nuevo output y confirma que cumple todos los criterios.

**Salida esperada:** Output completo con todas las secciones requeridas y el tono ajustado.

**Verificación:** Todos los criterios de la lista del Paso A-2 están ahora satisfechos con el prompt optimizado.

---

### Parte B — Generación de Descriptivos de Puesto para Dos Roles (25 minutos)

**Objetivo de esta parte:** Aplicar la metodología de prompting progresivo para construir descriptivos de puesto completos para un **rol técnico** y un **rol de gestión**, utilizando datos ficticios.

---

#### Paso B-1: Definir el contexto organizacional ficticio

**Objetivo:** Establecer el contexto de empresa ficticia que usarás como base para ambos descriptivos, garantizando coherencia y evitando el uso de datos reales.

**Instrucciones:**

1. Abre un **nuevo documento en Word** (desde el menú Archivo → Nuevo → Documento en blanco).
2. Guarda el documento inmediatamente en tu carpeta de OneDrive con el nombre:

```
Lab01-Descriptivos-[TusIniciales].docx
```

   Por ejemplo: `Lab01-Descriptivos-JGR.docx`

3. En la primera página del documento, escribe el siguiente encabezado y completa los campos con datos **completamente ficticios**:

```
=== CONTEXTO ORGANIZACIONAL FICTICIO ===
Empresa: [Nombre ficticio, ej. "TechFinance Solutions S.A. de C.V."]
Industria: [ej. Fintech / Servicios financieros digitales]
Tamaño: [ej. 800 empleados, presencia en 3 ciudades de México]
Cultura: [ej. Ágil, orientada a datos, trabajo híbrido]
Momento actual: [ej. Expansión de su área de analítica de negocio]
```

4. Vuelve a Copilot Chat y abre una **nueva conversación**.

**Salida esperada:** Documento Word guardado en OneDrive con el contexto organizacional ficticio documentado.

**Verificación:** El archivo aparece en `OneDrive > Copilot-RH-Labs` con el nombre correcto y la primera sección completada.

---

#### Paso B-2: Generar el descriptivo del Rol Técnico — Ingeniero/a de Machine Learning Sr.

**Objetivo:** Construir un descriptivo de puesto completo para un rol técnico usando prompting progresivo en tres etapas.

**Instrucciones:**

**Etapa 1 — Prompt base:**

1. En Copilot Chat (nueva conversación), ingresa el siguiente prompt base:

```
Redacta un descriptivo de puesto para el rol de 
Ingeniero/a de Machine Learning Sr.
```

2. Lee el output. Documenta en tu hoja de notas: ¿qué falta? ¿qué es demasiado genérico?

**Etapa 2 — Prompt de refinamiento con contexto:**

3. En el **mismo hilo de conversación**, ingresa:

```
Mejora el descriptivo anterior considerando este contexto:
- Empresa: fintech mexicana de 800 empleados en expansión
- El rol lidera un equipo de 3 analistas de datos junior
- Trabajo híbrido (3 días presencial en CDMX, 2 remoto)
- Stack tecnológico principal: Python, TensorFlow, Azure ML, 
  Power BI, SQL Server
- El candidato ideal tiene experiencia en modelos de scoring 
  crediticio o detección de fraude

Mantén el formato del descriptivo anterior pero enriquece 
cada sección con este contexto.
```

4. Lee el output refinado y compáralo con el prompt base.

**Etapa 3 — Prompt avanzado con restricciones y métricas de éxito:**

5. En el **mismo hilo**, ingresa el prompt avanzado:

```
Ahora agrega al descriptivo las siguientes dos secciones que 
faltan para hacerlo completo:

5. MÉTRICAS DE ÉXITO DEL ROL (primeros 90 días):
   - Define 3 KPIs medibles que indicarán que el colaborador 
     tuvo un onboarding exitoso
   - Define 2 objetivos estratégicos para el primer año

6. COMPETENCIAS ORGANIZACIONALES REQUERIDAS:
   - Incluye exactamente 3 competencias conductuales alineadas 
     a una cultura ágil y orientada a datos
   - Para cada competencia, agrega una descripción de 1 oración 
     de cómo se manifiesta en este rol específico

Restricciones adicionales:
- No incluyas rangos salariales
- Usa lenguaje inclusivo (evita sesgos de género en la redacción)
- Extensión máxima: 600 palabras en total
```

6. Lee el output final completo.
7. **Selecciona todo el texto del descriptivo final** en Copilot Chat, cópialo y pégalo en tu documento Word bajo el encabezado `## ROL TÉCNICO: Ingeniero/a de Machine Learning Sr.`

**Salida esperada:** Descriptivo de puesto completo con 6 secciones (objetivo, responsabilidades, perfil, propuesta de valor, métricas de éxito y competencias organizacionales), redactado con lenguaje inclusivo y sin rangos salariales.

**Verificación:**
- El descriptivo tiene las 6 secciones claramente diferenciadas.
- Se mencionan al menos 3 tecnologías del stack (Python, TensorFlow, Azure ML, etc.).
- Las métricas de éxito son medibles (tienen un verbo de acción + indicador cuantificable).
- El texto no supera aproximadamente 600 palabras.

---

#### Paso B-3: Generar el descriptivo del Rol de Gestión — Gerente de Desarrollo Organizacional

**Objetivo:** Aplicar la misma metodología de prompting progresivo para un rol de gestión, evidenciando cómo el contexto cambia el enfoque del descriptivo.

**Instrucciones:**

1. Abre una **nueva conversación** en Copilot Chat.
2. Usa directamente el **prompt avanzado completo** (sin pasar por las etapas base), incorporando todo lo aprendido:

```
Actúa como un Director de Recursos Humanos con experiencia en 
empresas de tecnología financiera en México.

Redacta un descriptivo de puesto completo para el rol de 
Gerente de Desarrollo Organizacional en una fintech de 
800 empleados que está en fase de expansión y transformación 
cultural hacia modelos ágiles.

El descriptivo debe incluir las siguientes secciones:

1. OBJETIVO DEL PUESTO
   - 2-3 oraciones que expliquen el propósito estratégico del rol

2. RESPONSABILIDADES PRINCIPALES
   - 6 viñetas, ordenadas de mayor a menor impacto estratégico
   - Incluye al menos una responsabilidad relacionada con 
     analítica de personas (People Analytics)

3. PERFIL REQUERIDO
   - Educación: licenciatura y posgrado (especifica campos)
   - Experiencia: años y tipo de experiencia relevante
   - Habilidades técnicas: mínimo 4 (incluye herramientas 
     digitales de RH y plataformas de e-learning)
   - Competencias conductuales: mínimo 4

4. MÉTRICAS DE ÉXITO DEL ROL
   - 3 KPIs para los primeros 6 meses
   - 2 objetivos de impacto para el primer año

5. COMPETENCIAS ORGANIZACIONALES
   - 3 competencias alineadas a cultura ágil
   - Descripción breve de manifestación en el rol

6. PROPUESTA DE VALOR PARA EL CANDIDATO
   - 1 párrafo que destaque el impacto del rol y 
     las oportunidades de crecimiento

Restricciones:
- Lenguaje inclusivo y libre de sesgos
- Sin rangos salariales ni beneficios monetarios específicos
- Tono: estratégico y ejecutivo, pero humano
- Extensión máxima: 700 palabras
```

3. Lee el output completo.
4. Si alguna sección está incompleta, usa un prompt de refinamiento en el mismo hilo:

```
La sección [nombre de sección] necesita más detalle. 
Por favor, amplía esa sección específicamente, manteniendo 
el resto del descriptivo igual.
```

5. Copia el descriptivo final completo y pégalo en tu documento Word bajo el encabezado `## ROL DE GESTIÓN: Gerente de Desarrollo Organizacional`.

**Salida esperada:** Descriptivo de puesto completo para el rol de gestión con 6 secciones, tono estratégico-ejecutivo, lenguaje inclusivo y sin información salarial.

**Verificación:**
- Las responsabilidades incluyen al menos una mención a People Analytics o analítica de personas.
- Las métricas de éxito son cuantificables (no vagas como "mejorar el clima").
- El tono es notablemente diferente al del rol técnico (más estratégico, menos operativo).

---

### Parte C — Generación de Strings de Búsqueda Booleana y Prompts de Sourcing (20 minutos)

**Objetivo de esta parte:** Utilizar Copilot para diseñar strings de búsqueda booleana y prompts de sourcing para LinkedIn Recruiter y bolsas de trabajo, aplicados a los dos roles generados en la Parte B.

---

#### Paso C-1: Generar strings de búsqueda booleana para el rol técnico

**Objetivo:** Crear strings de búsqueda booleana listos para usar en LinkedIn Recruiter y Google X-Ray Search para el perfil de Ingeniero/a de Machine Learning Sr.

**Instrucciones:**

1. Abre una **nueva conversación** en Copilot Chat.
2. Ingresa el siguiente prompt:

```
Actúa como un recruiter técnico especializado en perfiles 
de tecnología e inteligencia artificial.

Basándote en este perfil buscado:
- Rol: Ingeniero/a de Machine Learning Sr.
- Industria: Fintech / servicios financieros
- Ubicación: México (CDMX, Monterrey o Guadalajara)
- Stack técnico clave: Python, TensorFlow, Azure ML, SQL, Power BI
- Experiencia en: modelos de scoring crediticio o detección de fraude
- Modalidad: trabajo híbrido

Genera lo siguiente:

1. STRING BOOLEANA PARA LINKEDIN RECRUITER:
   - Una string booleana completa lista para copiar y pegar 
     en el campo de búsqueda de LinkedIn Recruiter
   - Usa operadores AND, OR, NOT correctamente
   - Incluye variaciones de títulos de puesto en inglés y español

2. STRING BOOLEANA PARA GOOGLE X-RAY (búsqueda en LinkedIn 
   desde Google):
   - Formato: site:linkedin.com/in/ [términos]
   - Incluye al menos 3 variaciones del título del puesto

3. PROMPT DE SOURCING PARA BOLSA DE TRABAJO (OCC/Computrabajo):
   - Palabras clave principales (5-7 términos)
   - Filtros recomendados (nivel, experiencia, ubicación)

Presenta cada sección claramente etiquetada y lista para 
usar directamente en cada plataforma.
```

3. Lee el output y evalúa si las strings booleanas usan correctamente los operadores (AND en mayúsculas, OR para variaciones, NOT para exclusiones).
4. Si las strings no incluyen suficientes variaciones de títulos, usa este refinamiento:

```
Agrega variaciones adicionales del título en inglés para 
la string de LinkedIn, incluyendo: "ML Engineer", 
"Data Scientist", "AI Engineer" y sus equivalentes en español.
```

5. Copia el output final y pégalo en tu documento Word bajo el encabezado `## STRINGS DE BÚSQUEDA: Ingeniero/a de Machine Learning Sr.`

**Salida esperada:** Tres strings/prompts de búsqueda diferenciados: uno para LinkedIn Recruiter, uno para Google X-Ray y uno para bolsas de trabajo locales, con operadores booleanos correctamente aplicados.

**Verificación:**
- La string de LinkedIn Recruiter contiene operadores AND, OR y/o NOT en mayúsculas.
- La string de Google X-Ray comienza con `site:linkedin.com/in/`.
- Las variaciones de título incluyen versiones en inglés y español.

---

#### Paso C-2: Generar prompts de sourcing para el rol de gestión

**Objetivo:** Diseñar un conjunto de prompts de sourcing para el perfil de Gerente de Desarrollo Organizacional, con énfasis en plataformas profesionales y redes de referidos.

**Instrucciones:**

1. En el **mismo hilo de conversación** del Paso C-1 (o en uno nuevo, según prefieras), ingresa:

```
Ahora genera estrategias de sourcing para un perfil diferente:

- Rol: Gerente de Desarrollo Organizacional
- Industria: Fintech / tecnología
- Ubicación: CDMX (presencial 3 días/semana)
- Experiencia requerida: 7+ años en RH, con enfoque en 
  desarrollo organizacional, gestión del cambio y People Analytics
- Nivel: Gerencia (reporta a Dirección de Capital Humano)

Genera:

1. STRING BOOLEANA PARA LINKEDIN RECRUITER:
   - Incluye variaciones: "OD Manager", "Organizational Development", 
     "Desarrollo Organizacional", "Gestión del Cambio", 
     "Change Management", "People Analytics"
   - Excluye perfiles puramente operativos de nómina o administración

2. MENSAJE DE ACERCAMIENTO (InMail) PARA CANDIDATO PASIVO:
   - Extensión: máximo 150 palabras
   - Tono: personalizado, no genérico, que despierte curiosidad
   - No revelar el nombre de la empresa todavía
   - Incluir un call-to-action claro

3. DESCRIPCIÓN CORTA PARA PUBLICACIÓN EN REDES SOCIALES 
   (LinkedIn post del reclutador):
   - Máximo 100 palabras
   - Tono dinámico, que genere engagement
   - Incluir 3 hashtags relevantes

Restricción: todos los textos deben estar en español.
```

2. Lee el output completo. Verifica que el mensaje de InMail no supera 150 palabras y que el post de LinkedIn incluye hashtags.
3. Si el InMail suena genérico, usa este refinamiento:

```
Reescribe el mensaje de InMail haciéndolo más específico: 
menciona que la empresa está en un proceso de transformación 
cultural hacia metodologías ágiles y que el rol tiene un 
impacto directo en la estrategia de talento del negocio. 
Mantén el límite de 150 palabras.
```

4. Copia el output final y pégalo en tu documento Word bajo el encabezado `## ESTRATEGIA DE SOURCING: Gerente de Desarrollo Organizacional`.

**Salida esperada:** String booleana para LinkedIn, mensaje de InMail personalizado (≤150 palabras) y post para redes sociales (≤100 palabras con hashtags), todo en español.

**Verificación:**
- El InMail no revela el nombre de la empresa y tiene un call-to-action explícito.
- El post de LinkedIn incluye exactamente 3 hashtags.
- La string booleana excluye perfiles de nómina/administración con el operador NOT.

---

#### Paso C-3: Comparar enfoques y documentar aprendizajes

**Objetivo:** Reflexionar sobre la diferencia de efectividad entre los prompts básicos y avanzados, documentando observaciones para uso futuro.

**Instrucciones:**

1. Al final de tu documento Word, agrega una sección con el título `## REFLEXIÓN: Aprendizajes de Prompting`.
2. Responde brevemente las siguientes preguntas (3-5 oraciones por pregunta) directamente en el documento:

```
a) ¿Cuál fue la diferencia más notable entre el prompt débil 
   (Paso A-2) y el prompt optimizado (Paso A-3)?

b) ¿En qué momento del proceso de prompting progresivo 
   (base → refinamiento → avanzado) notaste el mayor 
   salto en calidad del output?

c) ¿Qué elemento de los cuatro pilares (Rol, Contexto, 
   Tarea, Tono/Formato) tuvo mayor impacto en la calidad 
   de tus strings de búsqueda booleana?

d) ¿Qué ajustarías en tus prompts si repitieras este 
   ejercicio para un sector diferente (ej. manufactura 
   o retail)?
```

3. Guarda el documento Word con **Ctrl + S**.

**Salida esperada:** Sección de reflexión completada con respuestas propias del participante, guardada en el documento.

**Verificación:** El documento Word contiene las 4 respuestas de reflexión y está guardado correctamente en OneDrive.

---

### Parte D — Transferencia a Word y Uso de Copilot en Word (5 minutos)

**Objetivo de esta parte:** Usar Copilot directamente en Word para mejorar el formato y consistencia del documento entregable.

---

#### Paso D-1: Usar Copilot en Word para dar formato ejecutivo al documento

**Objetivo:** Aplicar Copilot en Word para pulir el documento final y asegurar consistencia de estilo.

**Instrucciones:**

1. Asegúrate de que tu documento `Lab01-Descriptivos-[TusIniciales].docx` esté abierto en Word.
2. Verifica que el documento contiene todas las secciones:
   - Contexto organizacional ficticio
   - Descriptivo: Ingeniero/a de Machine Learning Sr.
   - Descriptivo: Gerente de Desarrollo Organizacional
   - Strings de búsqueda: Rol técnico
   - Estrategia de sourcing: Rol de gestión
   - Reflexión de aprendizajes
3. En la cinta de opciones de Word, haz clic en el botón **"Copilot"** (generalmente en la pestaña "Inicio" o "Revisar").
4. En el panel de Copilot en Word, ingresa el siguiente prompt:

```
Resume en un párrafo ejecutivo (máximo 80 palabras) el 
propósito de este documento, mencionando los dos roles 
descritos y el enfoque de prompting aplicado. 
Colócalo al inicio del documento como introducción.
```

5. Acepta o ajusta la sugerencia de Copilot según tu criterio profesional.
6. Guarda el documento final con **Ctrl + S**.

> 💡 **Nota:** Copilot en Word puede tardar algunos segundos en procesar. Si no responde, verifica tu conexión a internet y que la licencia Copilot esté activa en tu cuenta.

**Salida esperada:** Documento Word completo con un párrafo de introducción ejecutiva generado por Copilot en Word, guardado en OneDrive.

**Verificación:** El documento abierto en Word muestra el párrafo introductorio al inicio, antes del contexto organizacional ficticio.

---

## Validación y Pruebas

Al finalizar todos los pasos, verifica que tu entregable cumple con los siguientes criterios de completitud:

### Lista de verificación del entregable

| Criterio | ✅ / ❌ |
|---|---|
| El archivo `Lab01-Descriptivos-[TusIniciales].docx` existe en `OneDrive > Copilot-RH-Labs` | |
| El documento contiene el contexto organizacional ficticio (sin datos reales) | |
| El descriptivo del rol técnico tiene las 6 secciones completas | |
| El descriptivo del rol de gestión tiene las 6 secciones completas | |
| Ambos descriptivos usan lenguaje inclusivo y no contienen rangos salariales | |
| Las strings booleanas usan operadores AND/OR/NOT correctamente | |
| El InMail de sourcing no supera 150 palabras | |
| El post de LinkedIn incluye 3 hashtags | |
| La sección de reflexión tiene respuestas a las 4 preguntas | |
| El documento tiene un párrafo introductorio ejecutivo al inicio | |

### Criterio de calidad de prompting (autoevaluación)

Evalúa tus prompts avanzados con esta rúbrica simplificada:

| Pilar | 1 — Ausente | 2 — Parcial | 3 — Completo |
|---|---|---|---|
| **Rol** asignado a Copilot | No se especifica | Se menciona vagamente | Rol específico con experiencia/contexto |
| **Contexto** organizacional | Sin contexto | Industria genérica | Industria + tamaño + momento + ubicación |
| **Tarea** específica | Genérica | Estructura básica | Estructura detallada con subsecciones |
| **Tono/Formato** | Sin indicación | Solo tono o solo formato | Tono + formato + restricciones explícitas |

> **Meta:** Todos tus prompts avanzados deben puntuar 3 en al menos 3 de los 4 pilares.

---

## Solución de Problemas

### Problema 1: Copilot Chat no muestra el ícono de escudo de protección empresarial

**Síntomas:** Al acceder a `copilot.microsoft.com`, la interfaz no muestra el ícono de escudo (🛡️) o la etiqueta "Protección de datos empresariales". En su lugar, puede aparecer una interfaz más simple o un aviso de cuenta personal.

**Causa probable:** El participante inició sesión con su cuenta personal de Microsoft (Outlook.com, Hotmail, etc.) en lugar de su cuenta corporativa de Microsoft 365, o el navegador Edge tiene una sesión personal activa como perfil predeterminado.

**Solución:**
1. Cierra la pestaña actual de Copilot Chat.
2. En Edge, verifica el perfil de usuario activo haciendo clic en el avatar en la esquina superior derecha del navegador.
3. Si el perfil activo es personal, cambia al perfil corporativo o crea uno nuevo:
   - Haz clic en el avatar → "Agregar perfil" → "Iniciar sesión" → usa tu correo corporativo `@[tudominio].com`.
4. Con el perfil corporativo activo, navega nuevamente a `https://copilot.microsoft.com`.
5. El ícono de escudo debe aparecer ahora. Si no aparece, contacta al administrador de TI para verificar que la licencia Copilot esté asignada a tu cuenta.

> ⚠️ **No continúes el laboratorio sin confirmar que la sesión es corporativa.** Ingresar datos de empresa en Copilot con cuenta personal puede comprometer la privacidad organizacional.

---

### Problema 2: Copilot en Word no responde o el botón "Copilot" no aparece en la cinta de opciones

**Síntomas:** Al abrir Word, el botón "Copilot" no está visible en la pestaña "Inicio" o "Revisar". Al hacer clic en él (si existe), no abre el panel lateral o muestra un mensaje de error como "Copilot no está disponible en este momento".

**Causa probable:** La versión de Microsoft Word instalada es anterior a la 2401 (no es Microsoft 365 Apps actualizado), o la licencia de Copilot no está correctamente asignada al usuario en el tenant, o hay un problema de sincronización de la licencia que requiere cerrar y reabrir la sesión.

**Solución:**
1. **Verificar versión de Word:** Ve a `Archivo → Cuenta → Acerca de Word`. La versión debe ser 2401 o superior. Si es anterior, ejecuta `Archivo → Cuenta → Opciones de actualización → Actualizar ahora`.
2. **Cerrar sesión y volver a iniciar:** En Word, ve a `Archivo → Cuenta → Cerrar sesión`. Espera 30 segundos y vuelve a iniciar sesión con tu cuenta corporativa.
3. **Verificar licencia:** Confirma con tu administrador de TI que la licencia "Microsoft 365 Copilot" (el complemento adicional, no solo M365 Apps) esté asignada a tu usuario en el portal de administración.
4. **Alternativa temporal:** Si el problema persiste durante el laboratorio, realiza el Paso D-1 directamente en Copilot Chat (usando el texto del documento como contexto) y pega el resultado manualmente en Word. Esto no afecta la calidad del entregable.

---

## Limpieza del Entorno

Al finalizar el laboratorio, realiza las siguientes acciones para mantener el entorno ordenado:

1. **Guardar el documento final:**
   - Confirma que `Lab01-Descriptivos-[TusIniciales].docx` está guardado en `OneDrive > Copilot-RH-Labs`.
   - Cierra el documento Word.

2. **Limpiar el historial de Copilot Chat (opcional según política de la organización):**
   - En Copilot Chat, revisa si tu organización requiere eliminar los hilos de conversación del laboratorio.
   - Si es necesario, elimina las conversaciones desde el panel de historial lateral.

3. **Cerrar pestañas del navegador:**
   - Cierra las pestañas de `copilot.microsoft.com` utilizadas durante el laboratorio.
   - Mantén abierta únicamente la sesión activa si tienes laboratorios subsecuentes en la misma sesión.

4. **Verificar sincronización de OneDrive:**
   - Confirma que el ícono de OneDrive en la barra de tareas muestra el estado "Sincronizado" (nube con palomita ✅).
   - Si el ícono muestra un error, haz clic derecho → "Ver sincronización" y espera a que complete.

> 💡 **No elimines la carpeta `Copilot-RH-Labs` ni los archivos generados.** Estos documentos son entregables acumulativos que se usarán en laboratorios posteriores del curso.

---

## Resumen

### Lo que aprendiste en este laboratorio

En este laboratorio aplicaste de manera práctica los fundamentos de la Lección 1.1, demostrando que la calidad del output de Copilot está directamente determinada por la calidad del prompt. Los logros concretos de esta sesión incluyen:

| Artefacto generado | Herramienta utilizada | Técnica aplicada |
|---|---|---|
| Descriptivo de puesto — Rol técnico (ML Sr.) | Copilot Chat | Prompting progresivo (3 etapas) |
| Descriptivo de puesto — Rol de gestión (DO) | Copilot Chat | Prompt avanzado directo con restricciones |
| Strings booleanas para LinkedIn y Google | Copilot Chat | Prompting con especificaciones de plataforma |
| InMail y post de sourcing | Copilot Chat | Prompting con límites de extensión y tono |
| Documento ejecutivo integrado | Copilot en Word | Generación de introducción con contexto |

### Conceptos clave reforzados

- **Los cuatro pilares del prompting efectivo** (Rol, Contexto, Tarea, Tono/Formato) no son teóricos: su aplicación produce diferencias medibles y observables en la calidad del output.
- **El prompting iterativo** (refinamiento en el mismo hilo) es más eficiente que comenzar conversaciones nuevas cuando el contexto ya está establecido.
- **La variabilidad de Copilot** es normal: dos participantes con el mismo prompt pueden obtener outputs diferentes. El valor está en el proceso de prompting y los criterios de evaluación aplicados, no en la uniformidad.
- **La supervisión humana es insustituible:** Copilot genera texto probable y coherente, pero el profesional de RH debe validar, ajustar y aprobar cada artefacto antes de usarlo en un proceso real.

### Próximos pasos

En el **Laboratorio 01-00-02** utilizarás los descriptivos de puesto generados hoy como insumo para diseñar guías de entrevista por competencias y scorecards de evaluación de candidatos, profundizando en el uso de Copilot para la etapa de selección. Antes de la próxima sesión, revisa los descriptivos generados y reflexiona: ¿qué ajustarías si los fueras a publicar en un proceso real de tu organización?

### Recursos adicionales

| Recurso | URL |
|---|---|
| Documentación oficial de Microsoft Copilot para M365 | https://learn.microsoft.com/es-es/copilot/microsoft-365/microsoft-365-copilot-overview |
| Guía de prompting responsable de Microsoft | https://learn.microsoft.com/es-es/azure/ai-services/openai/concepts/prompt-engineering |
| Principios de IA responsable de Microsoft | https://www.microsoft.com/es-es/ai/responsible-ai |
| Guía de búsqueda booleana para LinkedIn Recruiter | https://business.linkedin.com/talent-solutions/resources/talent-acquisition/boolean-search |
| SHRM: IA en Recursos Humanos | https://www.shrm.org/topics-tools/topics/artificial-intelligence |

---

> **Nota para el instructor:** Recuerde verificar que ningún participante haya utilizado datos personales reales durante el laboratorio. Al revisar los documentos entregados, confirme que el contexto organizacional y los perfiles de candidatos son completamente ficticios. En caso de encontrar datos reales, solicite al participante que elimine el archivo, limpie el historial de Copilot Chat y repita la sección correspondiente con datos ficticios.

---
*Lab 01-00-01 · Módulo 1 · Curso: Microsoft 365 Copilot aplicado a Recursos Humanos*
