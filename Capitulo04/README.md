# Práctica 4 — Creación de Tablero de Control de Ejecución, Seguimiento e Indicadores de Capacitación

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel Bloom** | Crear (Create) |
| **Módulo** | Módulo 4 — Planes de Carrera, People Analytics y Reporte Ejecutivo |
| **Práctica número** | 4 de 4 (Laboratorio de cierre integrador) |
| **Tecnologías principales** | Copilot en Excel · Copilot en Word · Copilot Chat · Copilot en Outlook · Teams (opcional) |

---

## 2. Descripción General

Esta práctica de cierre integra los artefactos generados en las prácticas anteriores para construir un sistema completo de seguimiento y reporte ejecutivo de talento. El participante construirá en Excel un tablero de control (*dashboard*) con al menos seis KPIs de capacitación asistido por Copilot, generará un reporte ejecutivo de People Analytics en Word y redactará un correo de presentación a la dirección en Outlook. El laboratorio culmina con una reflexión sobre el valor estratégico de Copilot como habilitador de decisiones basadas en datos en Recursos Humanos, conectando directamente con los conceptos de planes de carrera, feedback continuo y seguimiento de talento clave estudiados en la Lección 4.1.

> ⚠️ **Recordatorio de privacidad:** Todos los datos utilizados en esta práctica son ficticios. **Nunca ingrese información personal real de colaboradores o candidatos en Copilot Chat.** Verifique que accede con su cuenta corporativa (el ícono de escudo debe estar visible en la interfaz de Copilot).

---

## 3. Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] **Construir** un tablero de control (dashboard) en Excel con Copilot, integrando al menos 6 KPIs de capacitación con indicadores tipo semáforo (RAG status), gráficas dinámicas y segmentaciones por área y período.
- [ ] **Generar** un reporte ejecutivo de People Analytics de 3-4 páginas en Word usando Copilot, que traduzca datos de RH en narrativas de impacto con hallazgos, comparativas de avance y recomendaciones estratégicas.
- [ ] **Diseñar** un sistema de seguimiento de talento clave con Copilot Chat, aplicando la Matriz 9-Box y generando planes de acción individualizados con alertas de riesgo de fuga de talento.
- [ ] **Sintetizar** información dispersa de múltiples fuentes en un reporte integrado, utilizando Copilot en Outlook para redactar comunicación ejecutiva de alto impacto.

---

## 4. Prerrequisitos

### 4.1 Conocimiento Previo

| Área | Requisito |
|---|---|
| **Prácticas anteriores** | Haber completado las Prácticas 1, 2 y 3 del curso; contar con todos los entregables en la carpeta `Copilot-RH-Labs` en OneDrive |
| **KPIs de RH** | Comprensión básica de métricas de capacitación (cubierta en el material del Módulo 4) |
| **Excel** | Manejo básico de tablas, fórmulas simples y gráficas |
| **Lección 4.1** | Haber revisado los conceptos de Planes de Carrera, Feedback Continuo y Seguimiento de Talento Clave (Matriz 9-Box, modelo COIN, HiPos) |
| **Copilot Chat** | Familiaridad con la construcción de prompts contextualizados (practicada en laboratorios previos) |

### 4.2 Acceso y Licencias

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 | ✅ Activa con licencia Copilot asignada |
| Microsoft Excel (versión 2401 o superior) | ✅ Instalado con Copilot habilitado |
| Microsoft Word (versión 2401 o superior) | ✅ Instalado con Copilot habilitado |
| Microsoft Outlook (nueva versión o clásico con complemento Copilot) | ✅ Instalado con Copilot habilitado |
| Microsoft Teams 2.0 | ✅ Instalado (opcional para actividad de cierre) |
| OneDrive for Business | ✅ Sincronizado; carpeta `Copilot-RH-Labs` disponible |
| Dataset de indicadores ficticios (`Lab04_Dataset_Capacitacion.xlsx`) | ✅ Descargado y guardado en `Copilot-RH-Labs` (proporcionado por el instructor) |

---

## 5. Entorno del Laboratorio

### 5.1 Especificaciones de Hardware Recomendadas

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 / AMD Ryzen 5 (8.ª gen) | Intel Core i7 / AMD Ryzen 7 |
| RAM | 8 GB | 16 GB (múltiples apps abiertas simultáneamente) |
| Almacenamiento libre | 5 GB | 10 GB |
| Resolución de pantalla | 1366 × 768 px | 1920 × 1080 px (tableros completos sin scroll) |
| Conexión a internet | 10 Mbps bajada / 5 Mbps subida | 25 Mbps (sin latencia en Copilot) |

### 5.2 Configuración Inicial del Entorno

Ejecute los siguientes pasos de configuración **antes** de iniciar el laboratorio:

**Paso 0-A — Verificar licencia y sesión corporativa:**
1. Abra el navegador Microsoft Edge (versión 120 o superior).
2. Navegue a [https://copilot.microsoft.com](https://copilot.microsoft.com) e inicie sesión con su cuenta corporativa.
3. Confirme que el **ícono de escudo/protección** esté visible en la interfaz. Esto garantiza que las conversaciones permanecen dentro del tenant de su organización.
4. Si el ícono no aparece, cierre sesión, cierre el navegador y vuelva a iniciar sesión con su cuenta corporativa (no personal).

**Paso 0-B — Preparar la carpeta de trabajo:**
```
Ruta OneDrive: Copilot-RH-Labs/
Archivos requeridos:
  - Lab04_Dataset_Capacitacion.xlsx   ← proporcionado por el instructor
  - (Opcional) Entregables de Prácticas 1, 2 y 3 como referencia
```

**Paso 0-C — Abrir las aplicaciones necesarias:**
Abra simultáneamente (puede usar el Taskbar o Alt+Tab para alternar):
- Microsoft Excel → archivo `Lab04_Dataset_Capacitacion.xlsx`
- Microsoft Word → documento en blanco nuevo
- Microsoft Outlook → bandeja de entrada
- Copilot Chat → [https://copilot.microsoft.com](https://copilot.microsoft.com) (pestaña en Edge)

**Paso 0-D — Verificar que el dataset esté en formato Tabla:**
> ⚠️ **Nota crítica:** Copilot en Excel requiere que los datos estén en formato **Tabla** (no rango simple) para funcionar correctamente. Verifique este punto antes de continuar.

1. En Excel, haga clic en cualquier celda del dataset.
2. Verifique que en la cinta aparezca la pestaña **"Diseño de tabla"** (*Table Design*). Si no aparece:
   - Seleccione todo el rango de datos.
   - Vaya a **Insertar → Tabla** (o presione `Ctrl + T`).
   - Confirme que "La tabla tiene encabezados" esté marcado → **Aceptar**.
3. Asigne el nombre `TblCapacitacion` a la tabla desde el campo **"Nombre de tabla"** en la pestaña Diseño de tabla.

---

## 6. Instrucciones Paso a Paso

El laboratorio se organiza en **tres bloques** y una **actividad de cierre integradora**:

| Bloque | Actividad | Tiempo estimado |
|---|---|---|
| **Bloque A** | Construcción del Tablero de Control en Excel | 20 min |
| **Bloque B** | People Analytics y Reporte Ejecutivo en Word | 20 min |
| **Bloque C** | Seguimiento de Talento Clave con Copilot Chat | 10 min |
| **Cierre** | Correo ejecutivo en Outlook + Reflexión integradora | 10 min |

---

### BLOQUE A — Tablero de Control de Indicadores de Capacitación en Excel

**Objetivo del bloque:** Construir un dashboard funcional con al menos 6 KPIs de capacitación, indicadores tipo semáforo (RAG status), gráficas dinámicas y segmentaciones por área, puesto y período, utilizando Copilot en Excel como asistente de fórmulas y visualización.

---

#### Paso A-1: Explorar el Dataset y Activar Copilot en Excel

**Objetivo:** Familiarizarse con la estructura del dataset y abrir el panel de Copilot en Excel.

**Instrucciones:**

1. En Excel, con el archivo `Lab04_Dataset_Capacitacion.xlsx` abierto, revise las columnas disponibles en la tabla `TblCapacitacion`. El dataset ficticio incluye las siguientes columnas de referencia:

```
Columnas del dataset (referencia):
| Colaborador | Área | Puesto | Período | Horas_Capacitación_Realizadas |
| Horas_Capacitación_Planeadas | Costo_Real | Costo_Planeado | 
| Satisfacción_Aprendizaje (1-5) | Brechas_Identificadas | Brechas_Cerradas |
| Beneficio_Estimado_USD | Estado_Colaborador |
```

2. Haga clic en la pestaña **"Inicio"** de la cinta de opciones.
3. Localice el botón **"Copilot"** en el extremo derecho de la cinta (ícono de estrella/chispa) y haga clic en él. Se abrirá el panel lateral de Copilot.
4. Si el botón no aparece, verifique que la tabla esté correctamente formateada (vea Paso 0-D) y que su licencia Copilot esté activa.

**Resultado esperado:** El panel lateral de Copilot en Excel está abierto y muestra el prompt de entrada listo para recibir instrucciones.

**Verificación:** El panel lateral muestra el mensaje de bienvenida de Copilot y reconoce la tabla `TblCapacitacion` como fuente de datos activa.

---

#### Paso A-2: Generar las Fórmulas de los 6 KPIs con Copilot

**Objetivo:** Usar Copilot en Excel para calcular automáticamente los seis KPIs de capacitación requeridos.

**Instrucciones:**

1. En el panel de Copilot en Excel, ingrese el siguiente prompt para generar las fórmulas de KPI. Copie y pegue el texto exacto:

```
Prompt para Copilot en Excel:

"Usando los datos de la tabla TblCapacitacion, ayúdame a calcular 
los siguientes 6 KPIs de capacitación. Para cada uno, genera la fórmula 
Excel correspondiente y explica brevemente qué mide:

1. % de Cumplimiento del Plan: (Horas_Capacitación_Realizadas / 
   Horas_Capacitación_Planeadas) * 100
2. Horas Promedio de Capacitación por Colaborador: promedio de 
   Horas_Capacitación_Realizadas por colaborador único
3. Costo por Hora Capacitada: Costo_Real total / 
   Horas_Capacitación_Realizadas total
4. Índice de Satisfacción del Aprendizaje: promedio de 
   Satisfacción_Aprendizaje (escala 1-5)
5. % de Brechas Cerradas: (Brechas_Cerradas / Brechas_Identificadas) * 100
6. ROI Estimado de Capacitación: ((Beneficio_Estimado_USD - Costo_Real) 
   / Costo_Real) * 100

Presenta los resultados en una nueva hoja llamada 'KPIs_Dashboard'."
```

2. Presione **Enter** o haga clic en el botón de envío.
3. Copilot generará las fórmulas sugeridas. Revise cada una y haga clic en **"Insertar columna"** o **"Agregar a hoja"** según la opción que presente Copilot para cada fórmula.
4. Si Copilot no crea la hoja automáticamente, cree manualmente una hoja nueva llamada `KPIs_Dashboard` (clic derecho en la pestaña de hoja → Insertar → Hoja de cálculo) y pegue allí los resultados.

> 💡 **Nota de variabilidad:** Copilot puede presentar las fórmulas en formatos ligeramente distintos entre participantes. Lo importante es que el resultado numérico sea correcto. Valide los cálculos manualmente con al menos dos registros del dataset.

**Resultado esperado:** La hoja `KPIs_Dashboard` contiene los seis KPIs calculados con sus valores numéricos correspondientes al dataset ficticio.

**Verificación:** Los valores de los KPIs son coherentes con los datos del dataset. Por ejemplo, el % de Cumplimiento del Plan no debería superar el 150 % ni ser inferior al 0 %. El Índice de Satisfacción debe estar entre 1 y 5.

---

#### Paso A-3: Crear Indicadores Tipo Semáforo (RAG Status)

**Objetivo:** Implementar un sistema de semáforo visual (Rojo/Ámbar/Verde) para cada KPI usando formato condicional asistido por Copilot.

**Instrucciones:**

1. En el panel de Copilot en Excel, ingrese el siguiente prompt:

```
Prompt para Copilot en Excel:

"En la hoja KPIs_Dashboard, agrega una columna de estado RAG 
(Rojo/Ámbar/Verde) para cada KPI usando las siguientes reglas:

- % Cumplimiento del Plan: Verde ≥ 90%, Ámbar 70-89%, Rojo < 70%
- Horas Promedio por Colaborador: Verde ≥ 20h, Ámbar 10-19h, Rojo < 10h
- Costo por Hora Capacitada: Verde ≤ $50 USD, Ámbar $51-$80, Rojo > $80
- Índice de Satisfacción: Verde ≥ 4.0, Ámbar 3.0-3.9, Rojo < 3.0
- % Brechas Cerradas: Verde ≥ 80%, Ámbar 60-79%, Rojo < 60%
- ROI Estimado: Verde ≥ 150%, Ámbar 80-149%, Rojo < 80%

Usa una fórmula SI anidada para generar el texto 'Verde', 'Ámbar' 
o 'Rojo' en la columna Estado. Luego aplica formato condicional 
para colorear las celdas con los colores correspondientes."
```

2. Aplique las fórmulas SI sugeridas por Copilot en la columna **"Estado_RAG"** de la hoja `KPIs_Dashboard`.
3. Para aplicar el formato condicional de colores:
   - Seleccione la columna `Estado_RAG`.
   - Vaya a **Inicio → Formato condicional → Nueva regla**.
   - Cree tres reglas: una para "Verde" (fondo verde claro), una para "Ámbar" (fondo amarillo) y una para "Rojo" (fondo rojo claro).
   - Alternativamente, solicite a Copilot: `"Aplica formato condicional a la columna Estado_RAG para colorear Verde en verde (#C6EFCE), Ámbar en amarillo (#FFEB9C) y Rojo en rojo (#FFC7CE)."` y siga las instrucciones que genere.

**Resultado esperado:** La hoja `KPIs_Dashboard` muestra una columna `Estado_RAG` con texto y color de fondo que indica el semáforo de cada KPI de manera visual e inmediata.

**Verificación:** Al menos un KPI muestra estado Verde, al menos uno muestra Ámbar o Rojo (el dataset está diseñado para mostrar variabilidad). Si todos los KPIs están en Verde, revise los umbrales con el instructor.

---

#### Paso A-4: Generar Gráficas Dinámicas y Segmentaciones

**Objetivo:** Crear visualizaciones del dashboard con gráficas dinámicas y segmentaciones por área y período usando Copilot.

**Instrucciones:**

1. En el panel de Copilot en Excel, ingrese el siguiente prompt:

```
Prompt para Copilot en Excel:

"Crea las siguientes visualizaciones para el dashboard de capacitación:

1. Un gráfico de barras agrupadas que muestre el % de Cumplimiento 
   del Plan por Área funcional.
2. Un gráfico de líneas que muestre la evolución del Índice de 
   Satisfacción del Aprendizaje por Período.
3. Un gráfico de dispersión que relacione el Costo por Hora 
   Capacitada con el % de Brechas Cerradas por colaborador.

Coloca los tres gráficos en la hoja KPIs_Dashboard. 
Usa títulos descriptivos en cada gráfico."
```

2. Copilot generará sugerencias de gráficos. Haga clic en **"Agregar a hoja"** para insertar cada gráfico en `KPIs_Dashboard`.
3. Agregue **segmentaciones de datos** (*slicers*) para filtrar por área y período:
   - Haga clic en cualquier gráfico o tabla dinámica.
   - Vaya a **Insertar → Segmentación de datos** (*Slicer*).
   - Seleccione los campos `Área` y `Período`.
   - Posicione los slicers en la parte superior del dashboard.
4. Ajuste el tamaño y posición de los gráficos para crear un layout organizado y profesional.

> 💡 **Consejo de diseño:** Para un dashboard ejecutivo, use no más de 3 colores corporativos, mantenga los gráficos alineados en cuadrículas y asegúrese de que todos los títulos sean descriptivos (qué mide + unidad de medida).

**Resultado esperado:** La hoja `KPIs_Dashboard` presenta un dashboard visual con los 6 KPIs, sus estados RAG y al menos 3 gráficas dinámicas con segmentaciones funcionales por área y período.

**Verificación:** Al cambiar la selección en los slicers de Área o Período, los gráficos se actualizan automáticamente reflejando los datos filtrados.

**Guarde el archivo** con `Ctrl + S` antes de continuar. Nombre sugerido: `Lab04_Dashboard_Capacitacion_[SusIniciales].xlsx`.

---

### BLOQUE B — People Analytics y Reporte Ejecutivo en Word

**Objetivo del bloque:** Usar Copilot Chat para analizar los datos del tablero y generar insights narrativos, y posteriormente usar Copilot en Word para redactar un reporte ejecutivo de 3-4 páginas con hallazgos clave, comparativas de avance, recomendaciones estratégicas y próximos pasos.

---

#### Paso B-1: Generar Insights de People Analytics con Copilot Chat

**Objetivo:** Usar Copilot Chat para interpretar los KPIs del dashboard y transformar datos numéricos en narrativas de impacto para la dirección.

**Instrucciones:**

1. Cambie a la pestaña de **Copilot Chat** en Edge ([https://copilot.microsoft.com](https://copilot.microsoft.com)).
2. Verifique que el ícono de escudo esté visible (modo protegido con cuenta corporativa).
3. Ingrese el siguiente prompt, adaptando los valores numéricos a los resultados reales que obtuvo en su dashboard del Bloque A:

```
Prompt para Copilot Chat:

"Actúa como un analista senior de People Analytics. 
Tengo los siguientes resultados del tablero de control 
de capacitación de mi organización (datos ficticios del período Q3-Q4):

- % Cumplimiento del Plan: 78% (Estado: Ámbar)
- Horas Promedio por Colaborador: 18.5 horas (Estado: Ámbar)
- Costo por Hora Capacitada: $62 USD (Estado: Ámbar)
- Índice de Satisfacción del Aprendizaje: 4.2 / 5.0 (Estado: Verde)
- % de Brechas Cerradas: 65% (Estado: Ámbar)
- ROI Estimado de Capacitación: 187% (Estado: Verde)

Con base en estos datos, genera:
1. Un párrafo de resumen ejecutivo (5-7 oraciones) que describa 
   el estado actual de la capacitación y su impacto en el negocio.
2. Tres hallazgos clave con su interpretación estratégica.
3. Dos alertas de riesgo que la dirección debe conocer.
4. Tres recomendaciones accionables con responsable sugerido 
   (RH, Liderazgo o Dirección) y plazo de implementación."
```

> 📝 **Instrucción importante:** Reemplace los valores del prompt con los valores reales de su dashboard. Si algún KPI tiene un valor diferente, actualice tanto el número como el estado RAG correspondiente.

4. Copilot Chat generará el análisis narrativo. **Copie el resultado completo** (seleccionar todo el texto → `Ctrl + C`).
5. Abra el **Bloc de notas** o un documento temporal en Word y pegue el resultado para conservarlo mientras trabaja en el reporte.

**Resultado esperado:** Copilot Chat genera un análisis narrativo estructurado con resumen ejecutivo, hallazgos, alertas y recomendaciones basadas en los KPIs del dashboard.

**Verificación:** El análisis incluye al menos los 4 elementos solicitados (resumen, hallazgos, alertas, recomendaciones) y conecta los datos numéricos con implicaciones estratégicas para el negocio.

---

#### Paso B-2: Estructurar el Reporte Ejecutivo con Copilot en Word

**Objetivo:** Usar Copilot en Word para generar la estructura y el contenido base del reporte ejecutivo de 3-4 páginas.

**Instrucciones:**

1. Cambie a **Microsoft Word** con el documento en blanco que abrió en la configuración inicial.
2. Haga clic en el botón **"Copilot"** en la cinta de opciones (pestaña Inicio o en el área de redacción, según su versión). Se abrirá el panel de Copilot o aparecerá el prompt flotante.
3. En algunos casos, Copilot en Word se activa con el botón en la barra de herramientas; en otros, con el ícono que aparece al inicio de un párrafo vacío. Use la opción disponible en su versión.
4. Ingrese el siguiente prompt en el panel de Copilot en Word:

```
Prompt para Copilot en Word:

"Redacta un reporte ejecutivo de 3 a 4 páginas titulado 
'Reporte de Impacto del Programa de Capacitación y Desarrollo 
de Talento — Período Q3-Q4' para ser presentado a la Dirección General. 

El reporte debe incluir las siguientes secciones:
1. Resumen Ejecutivo (máximo media página): estado general 
   del programa con los KPIs principales.
2. Análisis de Indicadores de Capacitación: tabla comparativa 
   de los 6 KPIs con meta, resultado real y estado RAG.
3. Hallazgos Clave y Tendencias: tres hallazgos con análisis 
   de causa-efecto.
4. Análisis de Talento Clave: estado del seguimiento de 
   colaboradores de alto potencial (HiPos), incluyendo 
   distribución en Matriz 9-Box y riesgos de retención detectados.
5. Recomendaciones Estratégicas: tres recomendaciones con 
   responsable, plazo e indicador de éxito.
6. Próximos Pasos: plan de acción para el siguiente trimestre.

Usa un tono ejecutivo, directo y orientado a la toma de decisiones. 
Todos los datos son ficticios para fines de práctica."
```

5. Copilot generará el borrador del reporte. Haga clic en **"Mantener"** o **"Keep"** para insertar el contenido en el documento.
6. Integre el análisis narrativo generado en el Paso B-1: copie los hallazgos, alertas y recomendaciones de Copilot Chat y péguelos en las secciones correspondientes del reporte, refinando la redacción para mantener coherencia de estilo.
7. Aplique el siguiente refinamiento usando Copilot en Word:

```
Prompt de refinamiento en Word:

"Revisa la sección de Recomendaciones Estratégicas y asegúrate 
de que cada recomendación incluya: (a) descripción de la acción, 
(b) responsable (RH, Liderazgo Directo o Dirección General), 
(c) plazo de implementación (corto: 0-3 meses, mediano: 3-6 meses), 
y (d) KPI de seguimiento que permita medir el éxito de la acción. 
Mantén el tono ejecutivo."
```

8. Guarde el documento como `Lab04_Reporte_Ejecutivo_[SusIniciales].docx` en la carpeta `Copilot-RH-Labs`.

**Resultado esperado:** Un documento Word de 3-4 páginas con las 6 secciones completas, tono ejecutivo, datos de los KPIs integrados y recomendaciones con estructura de responsable/plazo/KPI.

**Verificación:** El reporte contiene las 6 secciones requeridas, la tabla de KPIs refleja los valores reales de su dashboard (Bloque A) y las recomendaciones tienen los cuatro elementos solicitados (acción, responsable, plazo, KPI de seguimiento).

---

### BLOQUE C — Seguimiento de Talento Clave con Copilot Chat

**Objetivo del bloque:** Diseñar un sistema de seguimiento de talento clave con Copilot Chat, aplicando la Matriz 9-Box y generando planes de acción individualizados con alertas de riesgo de fuga de talento, conectando con los conceptos de la Lección 4.1.

---

#### Paso C-1: Generar Análisis de Talento Clave con Matriz 9-Box

**Objetivo:** Usar Copilot Chat para construir un análisis de talento clave basado en la Matriz 9-Box y generar recomendaciones de acción por cuadrante.

**Instrucciones:**

1. Regrese a **Copilot Chat** en Edge.
2. Ingrese el siguiente prompt (los perfiles son completamente ficticios):

```
Prompt para Copilot Chat:

"Actúa como un consultor de gestión del talento. 
Tengo los siguientes 5 colaboradores ficticios en mi revisión 
de talento del período Q3-Q4:

1. Alejandro V. — Ingeniero de Software Senior, 
   Potencial: Alto, Desempeño: Medio (85% de objetivos)
2. Mariana L. — Analista de Marketing Digital, 
   Potencial: Alto, Desempeño: Alto (102% de objetivos)
3. Roberto S. — Coordinador de Operaciones, 
   Potencial: Medio, Desempeño: Bajo (62% de objetivos)
4. Sofía P. — Especialista de RH, 
   Potencial: Alto, Desempeño: Medio (88% de objetivos)
5. Carlos M. — Gerente de Ventas Regional, 
   Potencial: Medio, Desempeño: Alto (97% de objetivos)

Para cada colaborador:
a) Indica su posición en la Matriz 9-Box.
b) Genera un plan de acción de 90 días con tres acciones 
   de desarrollo específicas.
c) Identifica el nivel de riesgo de fuga de talento 
   (Alto/Medio/Bajo) y la acción de retención recomendada.
d) Propone el tipo de feedback que debe recibir cada uno 
   (Reconocimiento, Correctivo, Desarrollo o 360°) 
   usando los modelos SBI o COIN según corresponda."
```

3. Copilot Chat generará el análisis completo. Revise los resultados y evalúe si las recomendaciones son coherentes con el perfil de cada colaborador ficticio.
4. Aplique el siguiente prompt de seguimiento para profundizar en el colaborador con mayor riesgo de fuga:

```
Prompt de seguimiento en Copilot Chat:

"Del análisis anterior, toma al colaborador con mayor riesgo 
de fuga de talento. Genera:
1. Un mensaje de feedback usando el modelo COIN (Contexto, 
   Observación, Impacto, Siguiente paso) que su líder directo 
   podría usar en una conversación one-on-one.
2. Una propuesta de plan de carrera de 12 meses con objetivos 
   SMART, hitos trimestrales y recursos de desarrollo sugeridos.
3. Un párrafo de alerta ejecutiva (3-4 oraciones) para incluir 
   en el reporte de talento a la dirección."
```

5. **Copie el párrafo de alerta ejecutiva** generado y agréguelo a la sección "Análisis de Talento Clave" del reporte Word del Bloque B.

**Resultado esperado:** Copilot Chat genera un análisis completo de los 5 colaboradores ficticios con posición en Matriz 9-Box, planes de acción, niveles de riesgo de retención y tipos de feedback recomendados. Para el colaborador de mayor riesgo, genera adicionalmente un mensaje COIN, un plan de carrera y una alerta ejecutiva.

**Verificación:** El análisis de la Matriz 9-Box es coherente (ningún colaborador con desempeño bajo puede tener recomendación de "retención inmediata" sin un plan de mejora asociado). Los mensajes de feedback aplican correctamente el modelo COIN con los cuatro elementos: Contexto, Observación, Impacto y Siguiente paso.

---

### ACTIVIDAD DE CIERRE — Correo Ejecutivo en Outlook y Reflexión Integradora

**Objetivo del bloque:** Usar Copilot en Outlook para redactar un correo ejecutivo de presentación del reporte a la dirección, y reflexionar sobre el valor estratégico de Copilot como habilitador de decisiones basadas en datos en RH.

---

#### Paso D-1: Redactar el Correo Ejecutivo con Copilot en Outlook

**Objetivo:** Usar Copilot en Outlook para sintetizar los hallazgos del reporte en un correo ejecutivo de presentación a la dirección general.

**Instrucciones:**

1. Abra **Microsoft Outlook** y cree un **nuevo correo electrónico** (`Ctrl + N` o botón "Nuevo correo").
2. En el campo "Para:", escriba una dirección ficticia de ejemplo: `direccion.general@empresa-ficticia.com`
3. En el campo "Asunto:", escriba: `Reporte de Impacto del Programa de Capacitación Q3-Q4 — Solicitud de Revisión`
4. Haga clic en el botón **"Copilot"** dentro del área de redacción del correo (ícono de estrella/chispa que aparece en la barra de herramientas del correo nuevo).
5. En el panel de Copilot en Outlook, seleccione la opción **"Borrador con Copilot"** (*Draft with Copilot*) e ingrese el siguiente prompt:

```
Prompt para Copilot en Outlook:

"Redacta un correo ejecutivo formal para la Dirección General 
presentando el Reporte de Impacto del Programa de Capacitación 
y Desarrollo de Talento del período Q3-Q4. 

El correo debe:
- Tener una apertura que destaque el logro más relevante 
  (ROI de capacitación del 187% y satisfacción de 4.2/5.0).
- Resumir en 3 puntos los hallazgos clave del período.
- Mencionar que se adjunta el reporte completo con 
  recomendaciones estratégicas y el tablero de indicadores.
- Solicitar un espacio de 20 minutos en agenda para 
  presentar los resultados y discutir los próximos pasos.
- Cerrar con un tono de colaboración estratégica, 
  no solo de reporte operativo.
- Extensión: máximo 250 palabras. Tono: ejecutivo y propositivo."
```

6. Copilot generará el borrador del correo. Revíselo y haga clic en **"Mantener"** para insertarlo en el cuerpo del mensaje.
7. Aplique el refinamiento de tono si es necesario usando la opción **"Ajustar"** (*Adjust*) en el panel de Copilot:
   - Seleccione **"Más directo"** si el correo es demasiado extenso.
   - Seleccione **"Más formal"** si el tono no es suficientemente ejecutivo.
8. **No envíe el correo.** Guárdelo como borrador (`Ctrl + S`) para evidencia del laboratorio.

**Resultado esperado:** Un correo ejecutivo en Outlook de máximo 250 palabras, con tono formal y propositivo, que presenta los resultados clave del programa de capacitación y solicita un espacio en agenda para la presentación a dirección.

**Verificación:** El correo incluye: mención del ROI y satisfacción, tres puntos de hallazgos, referencia a los adjuntos (reporte + dashboard) y solicitud de reunión. El tono es ejecutivo, no operativo.

---

#### Paso D-2 (Opcional) — Síntesis de Reunión en Microsoft Teams

**Objetivo:** Usar Copilot en Teams para simular la síntesis de una reunión de seguimiento de talento.

> ℹ️ **Esta actividad es opcional** y requiere acceso a una reunión de Teams grabada o la funcionalidad de Copilot en Teams para generar resúmenes. Si no dispone de una grabación, puede usar Copilot Chat para simular el ejercicio.

**Instrucciones (versión simulada con Copilot Chat):**

1. En Copilot Chat, ingrese el siguiente prompt:

```
Prompt para Copilot Chat (simulación de síntesis de reunión Teams):

"Simula ser el resumen automático generado por Copilot en Teams 
para una reunión de 30 minutos de 'Revisión de Talento Q3-Q4' 
con los siguientes participantes ficticios: 
Directora de RH (María González), Gerente de Capacitación 
(Luis Herrera) y Director General (Roberto Mendoza).

Los temas discutidos fueron:
- Presentación del dashboard de KPIs de capacitación.
- Análisis de los 5 colaboradores de alto potencial.
- Aprobación del presupuesto adicional para cerrar brechas.
- Definición de próximos pasos para el Q1 del siguiente año.

Genera: (1) resumen ejecutivo de la reunión (5 oraciones), 
(2) lista de decisiones tomadas, 
(3) lista de compromisos con nombre del responsable y fecha límite."
```

2. Revise el resultado y reflexione sobre cómo esta funcionalidad de Teams reduciría el tiempo de documentación post-reunión en su organización.

**Resultado esperado:** Copilot Chat genera una síntesis estructurada que simula el formato de resumen automático de Teams con decisiones y compromisos claramente identificados.

---

#### Paso D-3: Reflexión Integradora

**Objetivo:** Consolidar el aprendizaje del laboratorio y del módulo mediante una reflexión estructurada sobre el valor estratégico de Copilot en RH.

**Instrucciones:**

1. En un documento Word nuevo (o al final del reporte ejecutivo), responda brevemente las siguientes preguntas de reflexión. Puede usar Copilot Chat como interlocutor para estructurar sus ideas, pero las respuestas deben ser propias:

```
Preguntas de reflexión:

1. ¿Qué KPI del dashboard considera más estratégico para 
   presentar ante la dirección y por qué?

2. En el seguimiento de talento clave (Bloque C), ¿qué elemento 
   del análisis generado por Copilot Chat le resultó más útil 
   para la toma de decisiones? ¿Qué ajustaría del output?

3. ¿Cómo cambiaría el flujo de trabajo de su equipo de RH 
   si utilizara Copilot para construir este tipo de reportes 
   de manera regular? ¿Qué procesos actuales podría reemplazar 
   o acelerar?

4. ¿Qué consideraciones éticas y de privacidad son más 
   relevantes al usar Copilot para el seguimiento de 
   talento clave en su organización?
```

2. Guarde sus respuestas como `Lab04_Reflexion_[SusIniciales].docx` en `Copilot-RH-Labs`.

---

## 7. Validación y Pruebas

Al finalizar el laboratorio, verifique que cuenta con los siguientes entregables en su carpeta `Copilot-RH-Labs`:

| # | Entregable | Criterio de validación |
|---|---|---|
| 1 | `Lab04_Dashboard_Capacitacion_[Iniciales].xlsx` | Hoja `KPIs_Dashboard` con 6 KPIs calculados, columna RAG, 3 gráficas dinámicas y slicers funcionales por Área y Período |
| 2 | `Lab04_Reporte_Ejecutivo_[Iniciales].docx` | 3-4 páginas con 6 secciones completas; recomendaciones con estructura acción/responsable/plazo/KPI; alerta de talento clave integrada |
| 3 | Borrador de correo en Outlook | Correo guardado como borrador; ≤250 palabras; menciona ROI, hallazgos clave y solicita reunión |
| 4 | `Lab04_Reflexion_[Iniciales].docx` | Respuestas a las 4 preguntas de reflexión |

### Lista de Verificación Final

```
✅ La tabla TblCapacitacion en Excel tiene formato de Tabla (no rango simple)
✅ Los 6 KPIs muestran valores numéricos correctos y coherentes con el dataset
✅ El semáforo RAG aplica correctamente los umbrales definidos
✅ Los slicers de Área y Período actualizan los gráficos dinámicamente
✅ El reporte Word incluye datos reales del dashboard (no valores de ejemplo)
✅ El análisis de Matriz 9-Box es coherente con los perfiles ficticios
✅ Los mensajes de feedback aplican el modelo COIN con los 4 elementos
✅ El correo en Outlook está guardado como borrador (NO enviado)
✅ El ícono de escudo estuvo visible durante toda la sesión en Copilot Chat
✅ Ningún dato personal real fue ingresado en Copilot en ningún momento
```

---

## 8. Solución de Problemas

### Problema 1: Copilot en Excel no responde o no reconoce la tabla

**Síntomas:**
- El botón de Copilot en Excel aparece atenuado (gris) y no se puede hacer clic.
- Copilot en Excel muestra el mensaje: *"Copilot works best with data in a table format"* o un mensaje similar indicando que no puede analizar los datos.
- El panel de Copilot se abre pero no genera fórmulas ni respuestas útiles.

**Causa probable:**
Los datos del dataset no están en formato **Tabla** de Excel (requisito indispensable para que Copilot en Excel funcione). Esto ocurre cuando el archivo se abre como rango de celdas sin convertir, o cuando la tabla no tiene un nombre asignado. También puede ocurrir si la hoja activa no es la que contiene los datos.

**Solución:**
1. Haga clic en cualquier celda dentro del rango de datos.
2. Presione `Ctrl + T` → confirme que "La tabla tiene encabezados" está marcado → **Aceptar**.
3. En la pestaña **Diseño de tabla**, asigne el nombre `TblCapacitacion` en el campo "Nombre de tabla" (extremo izquierdo de la cinta).
4. Cierre y vuelva a abrir el panel de Copilot.
5. Si el problema persiste, guarde el archivo, ciérrelo completamente y vuelva a abrirlo.
6. Verifique que su licencia Copilot esté activa navegando a [https://copilot.microsoft.com](https://copilot.microsoft.com) con su cuenta corporativa.

---

### Problema 2: Copilot Chat genera análisis de talento con información inconsistente o contradictoria

**Síntomas:**
- Un colaborador con desempeño "Alto" en el prompt aparece en un cuadrante de bajo desempeño en la Matriz 9-Box generada.
- Las recomendaciones de acción no corresponden al perfil del colaborador (por ejemplo, se sugiere "plan de mejora de desempeño" para un colaborador de alto potencial y alto desempeño).
- El nivel de riesgo de fuga asignado parece arbitrario o no justificado.

**Causa probable:**
Copilot Chat es un modelo no determinista; puede interpretar el contexto del prompt de manera diferente en cada sesión, especialmente cuando el prompt incluye múltiples perfiles en un solo mensaje. La ambigüedad en los descriptores ("potencial alto", "desempeño medio") puede generar clasificaciones inconsistentes si no se proporcionan criterios numéricos o cualitativos claros.

**Solución:**
1. **Refine el prompt** añadiendo criterios explícitos de clasificación. Ejemplo:
```
Prompt refinado:

"Usa la siguiente escala para la Matriz 9-Box:
- Desempeño: Bajo = <70% objetivos, Medio = 70-89%, Alto = ≥90%
- Potencial: Bajo = sin evidencia de crecimiento en 12 meses, 
  Medio = 1-2 competencias de liderazgo demostradas, 
  Alto = ≥3 competencias de liderazgo + disposición declarada de crecer.
Con esta escala, reclasifica a los 5 colaboradores y regenera el análisis."
```
2. Si la inconsistencia persiste en un colaborador específico, analícelo en un **prompt separado** en lugar de incluir los 5 perfiles juntos.
3. Recuerde que la variabilidad de outputs es una característica del modelo. Evalúe la **calidad del razonamiento** y la **coherencia interna** del análisis, no la uniformidad con el resultado de otros participantes.
4. Aplique su **juicio profesional de RH** para validar y corregir cualquier clasificación que no sea coherente con el perfil del colaborador ficticio.

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realice las siguientes acciones:

```
Acciones de limpieza:

1. GUARDAR todos los archivos en OneDrive (Copilot-RH-Labs/):
   - Lab04_Dashboard_Capacitacion_[Iniciales].xlsx
   - Lab04_Reporte_Ejecutivo_[Iniciales].docx
   - Lab04_Reflexion_[Iniciales].docx
   - El borrador del correo queda guardado en Outlook automáticamente.

2. CERRAR el panel de Copilot en Excel y Word 
   (clic en la X del panel lateral).

3. ELIMINAR el historial de conversación de Copilot Chat 
   si la política de su organización así lo requiere:
   Copilot Chat → ícono de historial → Eliminar conversación de hoy.

4. CERRAR las pestañas adicionales en Edge 
   (mantener solo las aplicaciones necesarias abiertas).

5. VERIFICAR que ningún dato personal real haya sido ingresado 
   en ninguna herramienta de Copilot durante la sesión.

6. COMPARTIR los entregables con el instructor según las 
   instrucciones del curso (enlace de OneDrive o envío directo).
```

> ⚠️ **Importante:** No elimine los archivos de la carpeta `Copilot-RH-Labs`. Estos entregables son la evidencia del portafolio de competencias del curso y serán utilizados en la evaluación final.

---

## 10. Resumen

### Lo que construyó en este laboratorio

En esta práctica de cierre integró competencias de los cuatro módulos del curso para construir un sistema completo de seguimiento y reporte ejecutivo de talento:

| Bloque | Lo que construyó | Herramienta |
|---|---|---|
| **A** | Dashboard de 6 KPIs con semáforo RAG, gráficas dinámicas y segmentaciones | Copilot en Excel |
| **B** | Reporte ejecutivo de People Analytics de 3-4 páginas con hallazgos y recomendaciones | Copilot Chat + Copilot en Word |
| **C** | Análisis de Matriz 9-Box, planes de acción y alertas de retención para 5 HiPos ficticios | Copilot Chat |
| **Cierre** | Correo ejecutivo de presentación a dirección + reflexión integradora | Copilot en Outlook |

### Conceptos Clave Reforzados

- **Dashboard de KPIs de capacitación:** El tablero de control no es un fin en sí mismo, sino un habilitador de conversaciones estratégicas. Los indicadores tipo semáforo (RAG) permiten a la dirección identificar áreas de atención en segundos.
- **People Analytics narrativo:** Los datos solo generan impacto cuando se traducen en historias de negocio. Copilot Chat actúa como puente entre los números del dashboard y las decisiones de la dirección.
- **Seguimiento de talento clave:** La Matriz 9-Box, los modelos de feedback (COIN, SBI) y los planes de carrera son herramientas que Copilot puede acelerar significativamente, pero que requieren siempre el juicio y la relación humana del profesional de RH.
- **Comunicación ejecutiva:** El correo de presentación y el reporte ejecutivo son el "último kilómetro" del trabajo de RH: si los datos no se comunican con claridad e impacto, el trabajo de análisis pierde valor ante la dirección.

### Reflexión Final sobre el Rol de Copilot en RH

Copilot no reemplaza al profesional de Recursos Humanos; amplifica su capacidad de impacto. La ventaja competitiva no reside en quien usa Copilot, sino en quien sabe **qué pedirle, cómo validar sus outputs y cómo traducir sus resultados en decisiones de negocio**. El dominio del prompting contextualizado, la validación crítica de los resultados y la integración de múltiples herramientas son las competencias que diferencian al profesional de RH del futuro.

---

### Recursos de Referencia

| Recurso | URL |
|---|---|
| Microsoft Copilot — Adopción y casos de uso en RH | [https://adoption.microsoft.com/en-us/copilot/](https://adoption.microsoft.com/en-us/copilot/) |
| Gallup — State of the Global Workplace | [https://www.gallup.com/workplace/349484/state-of-the-global-workplace.aspx](https://www.gallup.com/workplace/349484/state-of-the-global-workplace.aspx) |
| SHRM — Gestión del desempeño y feedback continuo | [https://www.shrm.org/topics-tools/topics/performance-management](https://www.shrm.org/topics-tools/topics/performance-management) |
| Deloitte — High-Impact Talent Management | [https://www2.deloitte.com/us/en/insights/topics/talent/high-impact-talent-management.html](https://www2.deloitte.com/us/en/insights/topics/talent/high-impact-talent-management.html) |
| Harvard Business Review — The Feedback Fallacy (modelo SBI) | [https://hbr.org/2019/03/the-feedback-fallacy](https://hbr.org/2019/03/the-feedback-fallacy) |
| Microsoft — Copilot en Excel: Guía de inicio | [https://support.microsoft.com/en-us/office/get-started-with-copilot-in-excel](https://support.microsoft.com/en-us/office/get-started-with-copilot-in-excel) |

---

*Laboratorio 04-00-01 — Módulo 4: Planes de Carrera, People Analytics y Reporte Ejecutivo*
*Curso: Microsoft 365 Copilot aplicado a Recursos Humanos*
