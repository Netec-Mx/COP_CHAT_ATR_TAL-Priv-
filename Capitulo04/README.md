# Práctica 4 — Creación de Tablero de Control de Ejecución, Seguimiento e Indicadores de Capacitación

## 1. Metadatos del Laboratorio

| Atributo | Detalle |
| :--- | :--- |
| **Duración** | 60 minutos |
| **Complejidad** | Intermedia |
| **Audiencia** | Gerentes de Reclutamiento, Consultores de Atracción de Talento, Coordinadores de Capacitación y Líderes de Desarrollo Organizacional |
| **Tecnologías** | Microsoft Copilot (M365 / Interfaz de Chat) y Microsoft Excel / Word |
| **Enfoque** | Diseño e implementación de indicadores clave de rendimiento (KPIs) de recursos humanos, consolidación automatizada de datos para People Analytics, y formulación de estrategias basadas en datos para mitigar la rotación de personal en plantas de producción continua. |

---

## 2. Description Corta

Este laboratorio práctico de 60 minutos capacita a los profesionales de Recursos Humanos en el uso estratégico de Microsoft Copilot para medir el impacto de la formación en la empresa de recubrimientos de forma ágil. Mediante dinámicas directas de copiado y pegado, los estudiantes estructurarán una base de seguimiento operativa en Excel, generarán un tablero resumen consolidado automáticamente por la IA, definirán los indicadores financieros clave (como el ROI y la tasa de retención temprana) y diseñarán un plan autónomo para mitigar la deserción de personal en el piso de planta.

---

## 3. Objetivos del Laboratorio

Al finalizar este laboratorio, el estudiante será capaz de:
* **Estructurar matrices de datos para People Analytics** en hojas de cálculo utilizando formatos de transferencia inmediata.
* **Consolidar tableros de control ejecutivos (Dashboards)** mediante el procesamiento guiado por IA, eliminando la formulación manual.
* **Interpretar KPIs críticos de recursos humanos** (ROI, Tasa de Aprobación, Eficacia de Onboarding) bajo un enfoque financiero y de negocio.
* **Estructurar planes de retención y fidelización de talento** basados en alertas cuantitativas extraídas del piso de producción.

---

## 4. Prerrequisitos

* Cuenta activa de **Microsoft 365** con acceso a **Microsoft Copilot**.
* Aplicación de **Microsoft Word** abierta con un documento en blanco guardado como `Manual_People_Analytics_Fidelizacion.docx`.
* Aplicación de **Microsoft Excel** abierta y lista para trabajar.

---

## 5. Procedimiento Paso a Paso

### Paso 1: Creación de la Base de Datos de Seguimiento en Excel

Para medir de manera formal el avance del programa de capacitación diseñado en los capítulos anteriores, el coordinador de desarrollo organizacional necesita consolidar la información en una base de datos limpia que registre a los operarios en proceso de onboarding.

1. Abra el chat general de **Microsoft Copilot**.
2. Introduzca el siguiente prompt avanzado para generar la tabla de datos:

```
Actúa como un Especialista en People Analytics y Administrador de Sistemas de Información de RH. Necesito poblar una matriz de datos en español para dar seguimiento técnico a la ejecución del 'Programa de Onboarding de Prensas de Gran Formato'. 

Genera una tabla de datos formal y limpia (no uses formato CSV de texto plano con comas). Devuelve la información estructurada en formato de tabla visual de Markdown (usando barras verticales | y guiones) para que al seleccionarla, copiarla y pegarla directamente en Excel, cada dato se posicione de forma automática en su celda correspondiente.

Las columnas de la tabla deben ser exactamente:
ID_Empleado | Nombre_Operador | Fecha_Ingreso | Estatus_Onboarding | Calificacion_Teorica_Dia2 | Calificacion_Practica_Dia5

Pobla la matriz con exactamente 4 registros completos con escenarios de una planta de recubrimientos cerámicos:
1. OPR-001 | Carlos Mendoza | 2026-07-01 | Certificado | 96 | 98
2. OPR-002 | Laura Jimenez | 2026-07-07 | En Proceso | 72 | 
3. OPR-003 | Miguel Torres | 2026-06-30 | Plan de Refuerzo | 68 | 54
4. OPR-004 | Andrea Rojas | 2026-07-09 | En Proceso | | 

Entrégame únicamente la tabla estructurada, sin introducciones ni textos conversacionales.
```

3. Seleccione la tabla visual devuelta por Copilot arrastrando el cursor sobre las celdas y cópiela (`Ctrl+C`).
4. Abra **Microsoft Excel**, seleccione la celda A1 de la primera hoja y pegue directamente (`Ctrl+V`). Verifique que los datos se distribuyan de forma inmediata en columnas independientes. Nombre a esta pestaña `Datos_Base` y guarde el archivo como `Control_Analytics_Capacitacion.xlsx`.

---

### Paso 2: Generación Directa de Indicadores y Resumen del Tablero

Para optimizar el tiempo y evitar configuraciones manuales de fórmulas o gráficos dinámicos complejos, utilizaremos las capacidades de cálculo de Copilot para procesar los registros anteriores y consolidar el Tablero de Control de forma inmediata.

1. En la misma ventana de chat de Copilot, introduzca el siguiente prompt para generar el resumen consolidado del tablero:

```
Actúa como un Especialista en Reportes de Recursos Humanos. Basado en los 4 registros de operadores generados en el paso anterior, necesito que realices el procesamiento analítico de los datos y estructures una tabla de resumen ejecutivo consolidada. 

Devuelve la información en formato de tabla visual de Markdown (usando barras verticales | y guiones) para que pueda seleccionarla, copiarla y pegarla directamente en una nueva pestaña de Excel sin necesidad de estructurar fórmulas adicionales.

La tabla de indicadores resumidos debe mostrar exactamente:
- Métrica / Variable | Valor Consolidado | Nota de Interpretación para el Reclutador
- Total de Operadores Registrados | 4 | Volumen total en la cohorte actual de julio 2026.
- Operadores Certificados Exitosamente | 1 | Representa el 25% del grupo (Caso OPR-001).
- Operadores en Proceso Activo | 2 | Requieren seguimiento en sus próximas evaluaciones teóricas/prácticas.
- Operadores en Plan de Refuerzo | 1 | Mandatorio asignar tutoría técnica en el piso de prensas.
- Promedio de Calificación Teórica (Día 2) | 78.6 | Calculado sobre los perfiles evaluados a la fecha.
- Promedio de Calificación Práctica (Día 5) | 76.0 | Alerta moderada; se requiere monitoreo del instructor de planta.

Entrégame únicamente la tabla estructurada con los números calculados, sin saludos ni introducciones.
```

2. Seleccione la tabla resumida devuelta por Copilot arrastrando el cursor sobre ella y cópiela (`Ctrl+C`).
3. Vuelva a su archivo de Excel `Control_Analytics_Capacitacion.xlsx`, cree una segunda pestaña llamada `Dashboard_Resumen`, seleccione la celda A1 y pegue los datos (`Ctrl+V`). Verifique que las métricas queden perfectamente distribuidas en filas y columnas listas para su lectura ejecutiva.

---

### Paso 3: Configuración Institucional del Diccionario de KPIs

La dirección general exige plasmar en el manual estratégico de Recursos Humanos las definiciones formales, fórmulas de negocio y objetivos organizacionales de las métricas que alimentan los tableros de control de la compañía.

1. Introduzca el siguiente prompt en la interfaz de Copilot para automatizar la redacción del marco analítico:

```
Actúa como un Director de Recursos Humanos (HR Business Partner). Necesito definir conceptualmente los indicadores clave de rendimiento para evaluar la efectividad de la capacitación y onboarding en nuestra planta de porcelánicos.

Por favor, devuélveme un bloque de texto formal y administrativo estructurado de la siguiente manera:
1. **Métrica 1: Tasa de Retención Temprana de Operadores (Primeros 90 días):** Define su fórmula y explica cómo este indicador impacta los costos operativos por paro de hornos debido a curvas de aprendizaje incompletas.
2. **Métrica 2: Retorno de Inversión (ROI) de Capacitación:** Redacta la fórmula estándar adaptada a Recursos Humanos y describe un ejemplo conceptual aplicado a la fábrica de cerámica (cómo el costo invertido en entrenar operarios se paga al reducir las toneladas de material roto o scrap en crudo).
3. **Métrica 3: Índice de Eficacia de Onboarding:** Fórmula basada en el porcentaje de operadores que logran la certificación operativa al primer intento de evaluación en el Día 5.

Genera las descripciones directamente en español con un enfoque riguroso de negocios, listo para copiar a Word.
```

2. Copie las descripciones de los KPIs generadas por la IA e incorpórelas en su documento de Word (`Manual_People_Analytics_Fidelizacion.docx`) bajo el título `## Diccionario de KPIs de People Analytics`.
3. Copie también en este documento el cuadro de indicadores consolidados que pegó en Excel en el Paso 2 bajo el título `## Reporte del Tablero de Control de Capacitación`.

---

### Paso 4: Reto de Aplicación Autónoma – Plan de Mitigación de Rotación Basado en Datos

**Instrucciones para el estudiante:** Los reportes trimestrales de analítica revelan un patrón alarmante: el **65% de los operarios de la línea de Piedra Natural** abandona la compañía de manera voluntaria entre el segundo y el tercer mes posterior a su ingreso. Las encuestas de salida sugieren que el problema radica en la falta de incentivos de crecimiento claros y el estrés por la manipulación de cargas pesadas de bloques de mármol.

#### El Desafío:
Aplicando técnicas de diagnóstico estratégico y fidelización de talento, redacte un prompt de forma totalmente autónoma en Copilot para formular un plan de retención enfocado en este foco rojo de la operación:

1. **Estructura del Requerimiento Autónomo:**
   - Ordene a Copilot que asuma el rol de un Especialista en Retención de Talento y Cultura Organizacional.
   - Solicite el diseño de un **Plan de Fidelización y Carrera Corta** enfocado específicamente en revertir la rotación temprana detectada por el análisis de datos en la línea de Piedra Natural.
2. **Componentes del Plan Basado en Datos:** Debe exigir en su instrucción que la propuesta de la IA abarque: un ajuste en la estructura de onboarding técnico enfocado en ergonomía y seguridad física, un programa de mentoría ("Operario Sombra Veterano") con un bono de éxito por retención, y la estructuración visual de una ruta de crecimiento salarial progresiva ligada a la certificación de habilidades avanzadas.
3. **Prueba de Verificación:** El estudiante debe comprobar que el entregable resultante proponga soluciones viables para una industria fabril pesada, alejándose de beneficios de oficina que no aplican al piso de producción y demostrando que las decisiones de retención de talento se guían por los hallazgos cuantitativos de People Analytics.

---

## 6. Conceptos Clave para Recordar

* **People Analytics:** Método de gestión de recursos humanos basado en la recopilación, análisis y modelado de datos cuantitativos sobre el comportamiento y rendimiento de los colaboradores para optimizar las decisiones de negocio.
* **Retorno de Inversión (ROI) en Capacitación:** Indicador financiero que mide el beneficio económico directo obtenido por la organización en comparación con el costo monetario invertido en la ejecución de los programas de formación.
* **Tiempo de Rampa (Time to Ramp):** El periodo cronológico que le toma a un nuevo colaborador pasar de la improductividad inicial del ingreso al estándar de rendimiento y velocidad requerido de forma oficial en su puesto de trabajo.

---

## 7. Resultado Esperado del Estudiante

Para validar la correcta conclusión de esta práctica de 60 minutos, el estudiante consolidará los siguientes componentes:

1. **Archivo `Control_Analytics_Capacitacion.xlsx` (Excel):**
   * Pestaña `Datos_Base` con la matriz de operadores del Paso 1.
   * Pestaña `Dashboard_Resumen` con el cuadro consolidado interactivo del Paso 2.
2. **Archivo `Manual_People_Analytics_Fidelizacion.docx` (Word):**
   * Documento institucionalizado con el diccionario de KPIs financieros (Paso 3) y el reporte de control copiado.
3. **Evidencia del Reto Autónomo:**
   * El diseño metodológico del Plan de Mitigación de Rotación Temprana del Paso 4 anexado como conclusión final en el documento de Word, consolidando su destreza en la dirección analítica del talento en el sector de acabados de construcción.
