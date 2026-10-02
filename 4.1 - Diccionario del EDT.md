## 1.1 Gestión del Proyecto

### Paquete de Trabajo: 1.1.1 ^p-111

- **Código:** 1.1.1
- **Denominación:** Acta de constitución del proyecto
- **Objetivo:** Autorizar formalmente la existencia del proyecto y conferir al director de proyecto la autoridad para asignar recursos organizacionales.
- **Descripción:** Documento formal que sintetiza la justificación estratégica, objetivos medibles, requisitos de alto nivel, presupuesto asignado, hitos principales y partes interesadas (_stakeholders_) del sistema de señales biomédicas.
- **Prerequisitos:**
- **Actividades:**

| Código      | Actividad                        | Alcance                                                                                                                            | Cálculo de tiempo estimado (Fórmula / Criterio)                | Tiempo estimado | Costo estimado (h x $)          | Riesgo                                                                 | Probabilidad (1-5) | Impacto (1-5) | P x I | Mitigación (Preventiva)                                                                       | Respuesta al riesgo                                                                                                                                               | Tiempo adicional si ocurre | Costo de gestión del riesgo      | Costo de contingencia si ocurre   | Costo total |
| :---------- | :------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------- | :-------------- | :------------------------------ | :--------------------------------------------------------------------- | :----------------- | :------------ | :---- | :-------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------- | :------------------------------- | :-------------------------------- | :---------- |
| **1.1.1.A** | Reunión de inicio y relevamiento | Relevar expectativas preliminares, justificación del proyecto y necesidades iniciales con sponsor y representantes de GAB y UNViMe | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3     | 2h              | 2h x $10.000/h =<br>**$20.000** | Inasistencia de actores clave o falta de alineación en objetivos       | 2                  | 4             | 8     | Enviar minuta previa con temario y objetivos 48h antes (dedicación: 0.5h)                     | **Mitigar / Contingencia:** Reprogramar sesión extraordinaria focalizada (1h) con los actores ausentes y validar acuerdos clave vía minuta asincrónica            | 1.5h                       | 0.5h x $10.000/h =<br>**$5.000** | 1.5h x $10.000/h =<br>**$15.000** | **$40.000** |
| **1.1.1.B** | Redacción del documento          | Redactar el acta de constitución definiendo propósito, objetivos medibles, supuestos, restricciones e hitos globales               | Estimación por tres valores:<br>(TO: 4h + TM: 6h + TP: 8h) / 3 | 6h              | 6h x $10.000/h =<br>**$60.000** | Ambigüedad en la definición del alcance inicial o criterios de éxito   | 3                  | 3             | 9     | Utilizar plantilla formal de Project Charter con campos normalizados (dedicación: 1h)         | **Mitigar / Contingencia:** Realizar sesión de alineación con sponsor e interesados clave para consensuar criterios de aceptación y redefinir límites del alcance | 2h                         | 1h x $10.000/h =<br>**$10.000**  | 2h x $10.000/h =<br>**$20.000**   | **$90.000** |
| **1.1.1.C** | Negociación y aprobación         | Revisar observaciones con las partes interesadas, ajustar términos y formalizar la firma del sponsor                               | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3     | 2h              | 2h x $10.000/h =<br>**$20.000** | Que no se apruebe por discrepancias en las restricciones o presupuesto | 2                  | 4             | 8     | Enviar borrador 72h antes para resolver observaciones de forma asincrónica (dedicación: 0.5h) | **Negociar / Contingencia:** Conducir mesa de negociación técnica para ajustar supuestos críticos, posponer entregables no esenciales o recalibrar plazos         | 2h                         | 0.5h x $10.000/h =<br>**$5.000** | 2h x $10.000/h =<br>**$20.000**   | **$45.000** |

- **Fechas:** Semanas 1 a 2 (Hito: Firma de Acta).
- **Criterios de aceptación:** Documento firmado formalmente por el patrocinador con objetivos SMART y presupuesto base ratificado.
- **Supuestos:** Disponibilidad oportuna de la directiva para revisiones y firmas.

### Paquete de Trabajo: 1.1.2 ^p-112

- **Código:** 1.1.2
- **Denominación:** Especificación de requisitos de software (SRS)
- **Objetivo:** Levantar, analizar y documentar formalmente todos los requerimientos funcionales, no funcionales y regulatorios del sistema.
- **Descripción:** Documento de ingeniería de requisitos bajo estándar IEEE 830 / ISO/IEC/IEEE 29148 que detalla las necesidades técnicas para el manejo de registros biomédicos (ECG, EEG, EMG), formatos de archivo, seguridad, rendimiento y normativas de confidencialidad de datos de salud.
- **Prerequisitos:** 1.1.1 Acta de constitución del proyecto aprobada.
- **Actividades:**

| Código      | Actividad                        | Alcance                                                                                                     | Cálculo de tiempo estimado (Fórmula / Criterio)                                             | Tiempo estimado | Costo estimado (h x $)            | Riesgo                                                              | Probabilidad (1-5) | Impacto (1-5) | P x I | Mitigación (Preventiva)                                                                      | Respuesta al riesgo                                                                                                                                                | Tiempo adicional si ocurre | Costo de gestión del riesgo      | Costo de contingencia si ocurre   | Costo total  |
| :---------- | :------------------------------- | :---------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------ | :-------------- | :-------------------------------- | :------------------------------------------------------------------ | :----------------- | :------------ | :---- | :------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------- | :------------------------------- | :-------------------------------- | :----------- |
| **1.1.2.A** | Reunión con la UNViMe            | Identificar necesidades de los usuarios institucionales y requisitos funcionales académicos/administrativos | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3                                  | 2h              | 2h x $10.000/h =<br>**$20.000**   | Que no tengan las necesidades claras (que se requiera otra reunión) | 3                  | 3             | 9     | Enviar cuestionario de relevamiento y guía de necesidades previa (dedicación: 0.5h)          | **Contingencia:** Ejecutar sesión de relevamiento complementaria con dinámicas guiadas sobre casos de uso específicos y flujos operativos reales                   | 2h                         | 0.5h x $10.000/h =<br>**$5.000** | 2h x $10.000/h =<br>**$20.000**   | **$45.000**  |
| **1.1.2.B** | Reunión con GAB                  | Relevar requerimientos operativos, de negocio y especificaciones de procesos para la contraparte GAB        | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3                                  | 2h              | 2h x $10.000/h =<br>**$20.000**   | Conflictos de prioridad entre requerimientos de GAB y UNViMe        | 2                  | 3             | 6     | Definir matriz de priorización MoSCoW antes de iniciar la sesión (dedicación: 0.5h)          | **Mediar / Contingencia:** Taller conjunto de arbitraje con representantes de ambas partes para ponderar impacto funcional y congelar prioridades consensuadas     | 1.5h                       | 0.5h x $10.000/h =<br>**$5.000** | 1.5h x $10.000/h =<br>**$15.000** | **$40.000**  |
| **1.1.2.C** | Reunión con Equipo de desarrollo | Analizar viabilidad técnica, arquitectura preliminar, dependencias y esfuerzo de desarrollo                 | Estimación tres valores:<br>(TO: 3h + TM: 4h + TP: 5h) / 3                                  | 4h              | 4h x $10.000/h =<br>**$40.000**   | Subestimación de complejidad técnica o restricciones de integración | 2                  | 4             | 8     | Sesión previa de análisis de infraestructura y stack tecnológico (dedicación: 1h)            | **Mitigar / Contingencia:** Ejecutar prueba de concepto rápida (_spike/PoC_) sobre módulos críticos y recalibrar estimaciones técnicas con el equipo de desarrollo | 2h                         | 1h x $10.000/h =<br>**$10.000**  | 2h x $10.000/h =<br>**$20.000**   | **$70.000**  |
| **1.1.2.D** | Elaboración del documento        | Redactar la ERS formal con catálogo de requerimientos, criterios de aceptación y matriz de trazabilidad     | Descomposición de tareas:<br>Redacción: 6h + Matriz trazabilidad: 2h + Revisión interna: 2h | 10h             | 10h x $10.000/h =<br>**$100.000** | Especificaciones ambiguas o vacíos en criterios de aceptación       | 3                  | 4             | 12    | Revisión técnica cruzada por pares (peer review) previa al cierre (dedicación: 1h)           | **Corregir / Contingencia:** Taller intensivo de refinamiento y reescritura de requisitos bajo estructura formal (_Given-When-Then_ / criterios SMART) junto al TL | 3h                         | 1h x $10.000/h =<br>**$10.000**  | 3h x $10.000/h =<br>**$30.000**   | **$140.000** |
| **1.1.2.E** | Aprobación                       | Presentar el documento ante referentes de UNViMe y GAB para firma y congelamiento de línea base             | Estimación tres valores:<br>(TO: 0.5h + TM: 1h + TP: 1.5h) / 3                              | 1h              | 1h x $10.000/h =<br>**$10.000**   | Que no se apruebe por disconformidad en el alcance acordado         | 2                  | 4             | 8     | Validar actas parciales de requerimientos durante el proceso de redacción (dedicación: 0.5h) | **Negociar / Contingencia:** Revisar observaciones puntuales, transferir requerimientos en disputa a un backlog de fases futuras y proceder a la firma             | 2h                         | 0.5h x $10.000/h =<br>**$5.000** | 2h x $10.000/h =<br>**$20.000**   | **$35.000**  |

- **Fechas:** Semanas 2 a 4.
- **Criterios de aceptación:** Documento SRS aprobado formalmente por los líderes de investigación y equipo técnico sin ambigüedades.
- **Supuestos:** Acceso directo a profesionales del área biomédica para definir las características clínicas de las señales.

### Paquete de Trabajo: 1.1.3 ^p-113

- **Código:** 1.1.3
- **Denominación:** Plan para la dirección del proyecto
- **Objetivo:** Establecer la guía integral para planificar, ejecutar, monitorear, controlar y cerrar el proyecto.
- **Descripción:** Compendio de planes subsidiarios que consolidan la línea base del alcance (EDT/WBS y diccionario), cronograma maestro, estimación de costos, plan de gestión de calidad, plan de comunicaciones y matriz de gestión de riesgos.
- **Prerequisitos:** 1.1.1 Acta de constitución y 1.1.2 Especificación de requisitos.
- **Actividades:**

| Código      | Actividad                                    | Alcance                                                                                                   | Cálculo de tiempo estimado (Fórmula / Criterio)                | Tiempo estimado | Costo estimado (h x $)          | Riesgo                                                                     | Probabilidad (1-5) | Impacto (1-5) | P x I | Mitigación (Preventiva)                                                                               | Respuesta al riesgo                                                                                                                                                     | Tiempo adicional si ocurre | Costo de gestión del riesgo      | Costo de contingencia si ocurre   | Costo total |
| :---------- | :------------------------------------------- | :-------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------- | :-------------- | :------------------------------ | :------------------------------------------------------------------------- | :----------------- | :------------ | :---- | :---------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------- | :------------------------------- | :-------------------------------- | :---------- |
| **1.1.3.A** | Reunión con Equipo de Dirección del Proyecto | Definir estrategia de gestión de alcance, cronograma, costos, calidad, recursos, comunicaciones y riesgos | Estimación tres valores:<br>(TO: 3h + TM: 4h + TP: 5h) / 3     | 4h              | 4h x $10.000/h =<br>**$40.000** | Falta de acuerdo en roles, responsabilidades o metodologías de trabajo     | 2                  | 3             | 6     | Preparar borrador de matriz RACI y agenda estructurada previa a la sesión (dedicación: 0.5h)          | **Resolver / Contingencia:** Taller de clarificación de gobernanza, renegociación de cargas operativas y ajuste formal de la matriz RACI                                | 2h                         | 0.5h x $10.000/h =<br>**$5.000** | 2h x $10.000/h =<br>**$20.000**   | **$65.000** |
| **1.1.3.B** | Elaboración del documento de planificación   | Consolidar las líneas base (alcance, tiempo, costo) e integrar los planes de gestión subsidiarios         | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3     | 2h              | 2h x $10.000/h =<br>**$20.000** | Inconsistencias entre las líneas base y los planes subsidiarios de gestión | 2                  | 4             | 8     | Aplicar lista de verificación (checklist) de coherencia entre planes e hitos (dedicación: 0.5h)       | **Corregir / Contingencia:** Conciliación cruzada de dependencias, costos y cronogramas entre planes subsidiarios y actualización de la línea base integrada            | 1.5h                       | 0.5h x $10.000/h =<br>**$5.000** | 1.5h x $10.000/h =<br>**$15.000** | **$40.000** |
| **1.1.3.C** | Aprobación                                   | Presentación ejecutiva del plan integrado ante el sponsor para autorizar el inicio de la ejecución        | Estimación tres valores:<br>(TO: 0.5h + TM: 1h + TP: 1.5h) / 3 | 1h              | 1h x $10.000/h =<br>**$10.000** | Rechazo u objeciones al cronograma propuesto o a la asignación de recursos | 2                  | 4             | 8     | Realizar reunión preliminar de 30 min para acordar supuestos y restricciones clave (dedicación: 0.5h) | **Ajustar / Contingencia:** Aplicar técnicas de compresión del cronograma (_crashing_ / _fast-tracking_) o nivelación de recursos para presentar una alternativa viable | 1.5h                       | 0.5h x $10.000/h =<br>**$5.000** | 1.5h x $10.000/h =<br>**$15.000** | **$30.000** |

- **Fechas:** Semanas 4 a 5.
- **Criterios de aceptación:** Plan integral validado por el equipo de desarrollo y aprobado por el comité de proyecto.
- **Supuestos:** Estabilidad en la asignación del equipo de ingeniería durante el ciclo de vida.

### Paquete de Trabajo: 1.1.4 ^p-114

- **Código:** 1.1.4
- **Denominación:** Reportes de avance y seguimiento
- **Objetivo:** Comunicar periódicamente el desempeño del proyecto frente a las líneas base a los interesados.
- **Descripción:** Informes ejecutivos y operativos emitidos periódicamente que reflejan el avance porcentual, estado de hitos, desempeño del cronograma (SPI), control presupuestal (CPI), riesgos materializados y cambios aprobados.
- **Prerequisitos:** 1.1.3 Plan para la dirección del proyecto aprobado.
- **Actividades:**

| Código      | Actividad                             | Alcance                                                                                            | Cálculo de tiempo estimado (Fórmula / Criterio)                                    | Tiempo estimado | Costo estimado (h x $)          | Riesgo                                                                        | Probabilidad (1-5) | Impacto (1-5) | P x I | Mitigación (Preventiva)                                                                               | Respuesta al riesgo                                                                                                                                               | Tiempo adicional si ocurre | Costo de gestión del riesgo      | Costo de contingencia si ocurre | Costo total |
| :---------- | :------------------------------------ | :------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------- | :-------------- | :------------------------------ | :---------------------------------------------------------------------------- | :----------------- | :------------ | :---- | :---------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------- | :------------------------------- | :------------------------------ | :---------- |
| **1.1.4.A** | Recopilar información sobre el avance | Recolectar datos de tareas concluidas, horas incurridas y estado de entregables del equipo técnico | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3                         | 2h              | 2h x $10.000/h =<br>**$20.000** | Carga incompleta o desactualizada de horas y tareas en el tablero             | 3                  | 3             | 9     | Fijar límite semanal automático para reporte de horas en la herramienta de gestión (dedicación: 0.5h) | **Contingencia:** Conducir sesiones breves 1 a 1 de seguimiento con los miembros rezagados para regularizar la carga de tareas y horas en el sistema              | 1h                         | 0.5h x $10.000/h =<br>**$5.000** | 1h x $10.000/h =<br>**$10.000** | **$35.000** |
| **1.1.4.B** | Elaborar el reporte de avance         | Calcular métricas de valor ganado (EVM), contrastar cronograma real vs. plan y evaluar desvíos     | Descomposición de tareas:<br>Cálculo de desvíos: 1.5h + Redacción de informe: 1.5h | 3h              | 3h x $10.000/h =<br>**$30.000** | Detección tardía de desviaciones críticas en la ruta principal del cronograma | 2                  | 4             | 8     | Configurar alertas tempranas basadas en umbrales de variación de costo y tiempo (dedicación: 0.5h)    | **Mitigar / Contingencia:** Evaluar el impacto en la ruta crítica y diseñar de inmediato un plan de recuperación con reasignación y paralelización de actividades | 2h                         | 0.5h x $10.000/h =<br>**$5.000** | 2h x $10.000/h =<br>**$20.000** | **$55.000** |
| **1.1.4.C** | Comunicar el estado del proyecto      | Distribuir el informe ejecutivo y realizar la reunión periódica de estado con los interesados      | Estimación tres valores:<br>(TO: 0.5h + TM: 1h + TP: 1.5h) / 3                     | 1h              | 1h x $10.000/h =<br>**$10.000** | Desinterés o falta de lectura del reporte por parte de los interesados clave  | 2                  | 3             | 6     | Presentar resumen visual de una página (dashboard con semáforos) y solicitar acuse (dedicación: 0.5h) | **Contingencia:** Convocar a una llamada ejecutiva breve (15 min) focalizada exclusivamente en desvíos, bloqueantes y decisiones requeridas                       | 1h                         | 0.5h x $10.000/h =<br>**$5.000** | 1h x $10.000/h =<br>**$10.000** | **$25.000** |

- **Fechas:** Semanas 2 a 24 (Emisión quincenal recurrente).
- **Criterios de aceptación:** Entrega puntual de reportes con datos trazables y aprobados por la gerencia.
- **Supuestos:** Los miembros del equipo reportan sus avances y horas dedicadas con precisión.

### Paquete de Trabajo: 1.1.5 ^p-115

- **Código:** 1.1.5
- **Denominación:** Acta de cierre del proyecto
- **Objetivo:** Formalizar la culminación contractual, administrativa y operativa del proyecto, liberando los recursos asignados.
- **Descripción:** Documento de terminación que formaliza la aceptación final de todos los entregables, documenta las lecciones aprendidas del desarrollo del banco de señales, evalúa los resultados y transfiere el sistema al equipo de mantenimiento.
- **Prerequisitos:** 1.5 Sistema desplegado en producción y 1.4.2 Pruebas de aceptación concluidas.
- **Actividades:**

| Código      | Actividad               | Alcance                                                                                                        | Cálculo de tiempo estimado (Fórmula / Criterio)                | Tiempo estimado | Costo estimado (h x $)          | Riesgo                                                                                   | Probabilidad (1-5) | Impacto (1-5) | P x I | Mitigación (Preventiva)                                                                                  | Respuesta al riesgo                                                                                                                                          | Tiempo adicional si ocurre | Costo de gestión del riesgo      | Costo de contingencia si ocurre   | Costo total |
| :---------- | :---------------------- | :------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------- | :-------------- | :------------------------------ | :--------------------------------------------------------------------------------------- | :----------------- | :------------ | :---- | :------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------- | :------------------------------- | :-------------------------------- | :---------- |
| **1.1.5.A** | Verificar el producto   | Comprobar el cumplimiento de criterios de aceptación de entregables, verificar objetivos y auditar compromisos | Estimación tres valores:<br>(TO: 3h + TM: 4h + TP: 5h) / 3     | 4h              | 4h x $10.000/h =<br>**$40.000** | Identificar actividades pendientes o entregables no conformes                            | 3                  | 4             | 12    | Aplicar checklist de validación previa junto con actas de aceptación parciales (dedicación: 1h)          | **Resolver / Contingencia:** Elaborar lista de observaciones pendientes (_punch list_), acordar tolerancias y ejecutar plan express de subsanación técnica   | 3h                         | 1h x $10.000/h =<br>**$10.000**  | 3h x $10.000/h =<br>**$30.000**   | **$80.000** |
| **1.1.5.B** | Redacción del documento | Elaborar el documento final de cierre con balance de alcance, costo, tiempo, lecciones aprendidas y archivo    | Estimación tres valores:<br>(TO: 1h + TM: 2h + TP: 3h) / 3     | 2h              | 2h x $10.000/h =<br>**$20.000** | Omisión de lecciones aprendidas críticas o falta de documentación de soporte             | 2                  | 2             | 4     | Utilizar plantilla normalizada de cierre con sesión previa de retrospectiva (dedicación: 0.5h)           | **Completar / Contingencia:** Conducir sesión focalizada de rescate documental con los líderes técnicos y actualizar el repositorio final del proyecto       | 1h                         | 0.5h x $10.000/h =<br>**$5.000** | 1h x $10.000/h =<br>**$10.000**   | **$35.000** |
| **1.1.5.C** | Aprobación              | Presentar el acta final y obtener la firma de aceptación definitiva y desvinculación formal del sponsor        | Estimación tres valores:<br>(TO: 0.5h + TM: 1h + TP: 1.5h) / 3 | 1h              | 1h x $10.000/h =<br>**$10.000** | Resistencia de algún interesado en otorgar el cierre formal por disconformidades menores | 2                  | 3             | 6     | Anexar las actas de conformidad parcial firmadas previamente durante el ciclo de vida (dedicación: 0.5h) | **Negociar / Contingencia:** Sesión de mediación con el sponsor para acordar cierre formal condicionado o traspaso de observaciones al soporte/mantenimiento | 1.5h                       | 0.5h x $10.000/h =<br>**$5.000** | 1.5h x $10.000/h =<br>**$15.000** | **$30.000** |

- **Fechas:** Semana 24 (Cierre del proyecto).
- **Criterios de aceptación:** Firma conjunta de conformidad del cliente/patrocinador y director del proyecto.
- **Supuestos:** No existen reclamos pendientes ni tickets bloqueantes sin resolver.

## 1.2 Infraestructura y Entorno

### Paquete de Trabajo: 1.2.1 ^p-121

- **Código:** 1.2.1
- **Denominación:** Servidores y base de datos configurados
- **Objetivo:** Proveer la infraestructura de cómputo, almacenamiento seguro de archivos masivos y base de datos optimizada para señales biomédicas.
- **Descripción:** Aprovisionamiento y configuración de máquinas virtuales/contenedores, repositorios de objetos (S3/MinIO) para archivos binarios de señales, y base de datos relacional/híbrida (PostgreSQL) para indexación de metadatos clínicos con copias de respaldo y certificados TLS/SSL.
- **Prerequisitos:** 1.1.2 Requisitos no funcionales de arquitectura y almacenamiento aprobados.
- **Actividades:**

1. Aprovisionar instancias cloud o servidores locales.
2. Configurar el motor de base de datos y esquemas relacionales.
3. Habilitar almacenamiento masivo para señales crudas (_raw data_).
4. Configurar reglas de firewall, puertos seguros y políticas de cifrado en reposo.

- **Fechas:** Semanas 5 a 7.
- **Criterios de aceptación:** Servidores operativos con monitoreo 24/7, almacenamiento escalable accesible por API y conexión a base de datos con latencia menor a 50 ms.
- **Supuestos:** Créditos cloud o servidores físicos disponibles a tiempo.

### Paquete de Trabajo: 1.2.2 ^p-122

- **Código:** 1.2.2
- **Denominación:** Entornos de desarrollo y pruebas
- **Objetivo:** Establecer ambientes aislados, reproducibles y automatizados para la construcción, integración y verificación continua del software.
- **Descripción:** Implementación de pipelines de CI/CD (Integración y Despliegue Continuo), entornos de desarrollo local dockerizados y un ambiente de _staging/QA_ que simule producción con datos sintéticos o anonimizados de señales.
- **Prerequisitos:** 1.2.1 Servidores y base de datos configurados.
- **Actividades:**

1. Crear imágenes base de Docker para frontend, backend y procesamiento matemático.
2. Configurar repositorios de código y pipelines de integración continua.
3. Cargar set de señales biomédicas de prueba anonimizadas en el entorno de pruebas.

- **Fechas:** Semanas 6 a 8.
- **Criterios de aceptación:** Pipelines automáticos que ejecuten compilación, análisis estático y despliegue en ambiente QA tras cada _merge_.
- **Supuestos:** Licencias y herramientas DevOps disponibles sin restricciones operativas.

#### Paquete de Trabajo: 1.2.3 ^p-123
- **Código:** 1.2.3
- **Denominación:** Aprovisionamiento y carga de dataset semilla 
- **Objetivo:**
- **Descripción:** 
- **Prerequisitos:**
- **Actividades:**

- **Fechas:** 
- **Criterios de aceptación:** 
- **Supuestos:** 
## 1.3 Software: Banco de Señales

### 1.3.1 Módulo de autenticación y seguridad

#### Paquete de Trabajo: 1.3.1.1 ^p-1311

- **Código:** 1.3.1.1
- **Denominación:** Interfaz de inicio de sesión
- **Objetivo:** Permitir el ingreso seguro y controlado de los usuarios a la plataforma mediante verificación de identidad.
- **Descripción:** Pantalla responsiva de autenticación que valida usuario y contraseña contra el servicio de identidad, emite tokens de sesión seguros (JWT/OAuth2) e implementa mecanismos de protección contra ataques de fuerza bruta.
- **Prerequisitos:** 1.2.2 Entornos de desarrollo y pruebas disponibles.
- **Actividades:**

1. Diseñar la interfaz de usuario UI/UX según lineamientos de accesibilidad.
2. Desarrollar componentes frontend y consumir endpoints de autenticación.
3. Implementar bloqueo temporal de cuenta tras múltiples intentos fallidos.

- **Fechas:** Semanas 8 a 9.
- **Criterios de aceptación:** Tiempo de respuesta de autenticación menor a 1 segundo, tokens transmitidos únicamente por HTTPS y bloqueo efectivo tras 5 intentos erróneos.
- **Supuestos:** Protocolo de cifrado robusto para contraseñas (Argon2 o bcrypt) estandarizado en backend.

#### Paquete de Trabajo: 1.3.1.2 ^p-1312

- **Código:** 1.3.1.2
- **Denominación:** Interfaz de registro de usuarios
- **Objetivo:** Proveer el mecanismo de creación de cuentas para investigadores, personal de salud y estudiantes.
- **Descripción:** Formulario web para captura de datos personales, filiación académica/institucional y credenciales deseadas, con verificación de correo electrónico (_double opt-in_) y validación de políticas de contraseñas complejas.
- **Prerequisitos:** 1.2.2 Entornos operativos y 1.3.1.1 Componentes base de autenticación.
- **Actividades:**

1. Diseñar el formulario con validación de campos en tiempo real.
2. Integrar pasarela/servicio de envío de correos con enlaces de activación temporal.
3. Implementar mecanismo de protección contra registros masivos automatizados (Captcha).

- **Fechas:** Semanas 9 a 10.
- **Criterios de aceptación:** Cuenta creada exitosamente sólo tras confirmación mediante token enviado por correo dentro de los 30 minutos de vigencia.
- **Supuestos:** Servicio de correo transaccional configurado y con alta tasa de entregabilidad.

#### Paquete de Trabajo: 1.3.1.3 ^p-1313

- **Código:** 1.3.1.3
- **Denominación:** Interfaz de recuperación de credenciales
- **Objetivo:** Facilitar el restablecimiento autónomo de contraseñas olvidadas resguardando la integridad de las cuentas.
- **Descripción:** Flujo de recuperación compuesto por solicitud mediante correo registrado, generación de token único de un solo uso con expiración y formulario de cambio de clave.
- **Prerequisitos:** 1.3.1.1 y 1.3.1.2 completados.
- **Actividades:**

1. Construir la vista de solicitud de restablecimiento y vista de nueva clave.
2. Desarrollar servicio backend de generación e invalidación de tokens seguros.
3. Auditar eventos de restablecimiento en los logs de seguridad.

- **Fechas:** Semanas 10 a 11.
- **Criterios de aceptación:** Enlace de restablecimiento con vigencia máxima de 15 minutos e invalidación automática tras el primer uso.
- **Supuestos:** No se revelará en la interfaz si un correo ingresado existe o no en el sistema (evitar enumeración de usuarios).

#### Paquete de Trabajo: 1.3.1.4 ^p-1314

- **Código:** 1.3.1.4
- **Denominación:** Sistema de control de acceso por roles (RBAC)
- **Objetivo:** Garantizar que los usuarios accedan únicamente a los datos y funciones según su perfil asignado.
- **Descripción:** Mecanismo de autorización granular que define y aplica permisos para roles: Administrador, Investigador Clínico, Usuario Estándar y Auditor, asegurando que sólo personal acreditado acceda a datos sensibles.
- **Prerequisitos:** 1.3.1.1 Interfaz de inicio de sesión terminada.
- **Actividades:**

1. Diseñar la matriz de roles y permisos granulares.
2. Implementar middlewares de control de acceso a nivel de API backend y directivas en frontend.
3. Construir panel de asignación de roles exclusivo para administradores.

- **Fechas:** Semanas 10 a 12.
- **Criterios de aceptación:** Bloqueo estricto (código HTTP 403 Forbidden) para cualquier acción no permitida por la matriz de roles; aprobación de pruebas de elevación de privilegios.
- **Supuestos:** Los perfiles institucionales están previamente homologados con las normativas éticas correspondientes.

### 1.3.2 Módulo de gestión de señales

#### Paquete de Trabajo: 1.3.2.1 ^p-1321

- **Código:** 1.3.2.1
- **Denominación:** Formulario y procesador de carga (alta)
- **Objetivo:** Permitir la carga e ingesta controlada de registros biomédicos al repositorio con extracción automática de características técnicas.
- **Descripción:** Componente web de carga de archivos (con soporte de arrastrar y soltar) conectado a un motor de procesamiento que valida la integridad del archivo, detecta el formato (EDF, CSV, PhysioNet, etc.), extrae canales, frecuencia de muestreo y duración, y almacena el archivo binario y sus metadatos.
- **Prerequisitos:** 1.2.1 Almacenamiento configurado y 1.3.1.4 Control de roles operativo.
- **Actividades:**

| Código    | Actividad                 | Alcance                                                                                                                                    | Cálculo de tiempo                                                                                                                                      | Tiempo est. | Costo estimado | Riesgo                                                                             | P   | I   | P×I | Mitigación                                                                  | Tiempo prevención | Costo gestión | Tiempo adicional | Costo contingencia | Duración total | Costo total |
| --------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | -------------- | ---------------------------------------------------------------------------------- | --- | --- | --- | --------------------------------------------------------------------------- | ----------------- | ------------- | ---------------- | ------------------ | -------------- | ----------- |
| 1.3.2.1.A | Diseño de la página       | Maquetas de la pantalla de carga: zona de arrastrar y soltar, selector de archivo, barra de progreso y mensajes de error                   | Tres valores: (8 + 12 + 16) / 3 = 12 h                                                                                                                 | 12 h        | $120.000       | Requisitos del flujo de carga poco claros que obligan a rediseñar                  | 3   | 2   | 6   | Validar las maquetas con el equipo/tutor antes de implementar               | 1 h               | $10.000       | 4 h              | $40.000            | 17 h           | $170.000    |
| 1.3.2.1.B | Implementación de UI      | Componente web de carga con arrastrar y soltar, previsualización de metadatos detectados y estados (cargando, éxito, error)                | Tres valores: (26 + 32 + 38) / 3 = 32 h                                                                                                                | 32 h        | $320.000       | Incompatibilidad del arrastrar y soltar entre navegadores                          | 3   | 3   | 9   | Usar una librería de componentes probada y probar en al menos 2 navegadores | 3 h               | $30.000       | 10 h             | $100.000           | 45 h           | $450.000    |
| 1.3.2.1.C | Funcionalidad de subida   | Procesador backend que valida integridad, detecta el formato (EDF), extrae canales, frecuencia de muestreo y duración, y guarda el binario | Descomposición: validación de integridad 10 h + detección de formato 8 h + extracción de características 12 h + almacenamiento del binario 10 h = 40 h | 40 h        | $400.000       | Archivos de hasta 500 MB que saturan la memoria o superan el tiempo máximo de 20 s | 3   | 5   | 15  | Lectura por streaming/bloques y prueba de carga con un archivo de 500 MB    | 4 h               | $40.000       | 14 h             | $140.000           | 58 h           | $580.000    |
| 1.3.2.1.D | Funcionalidad de registro | Alta del registro en la base de datos: guarda los metadatos extraídos, los vincula al binario y registra usuario y fecha                   | Tres valores: (24 + 30 + 36) / 3 = 30 h                                                                                                                | 30 h        | $300.000       | Inconsistencia entre metadatos y archivo si falla la operación a mitad de camino   | 2   | 4   | 8   | Guardar en una transacción atómica con rollback                             | 2 h               | $20.000       | 8 h              | $80.000            | 40 h           | $400.000    |

- **Criterios de aceptación:** Ingesta exitosa de archivos de hasta 500 MB en menos de 20 segundos con lectura correcta de cabecera y canales.
- **Supuestos:** Los usuarios proporcionan archivos conformes a especificaciones estándar de señales biomédicas.

#### Paquete de Trabajo: 1.3.2.2 ^p-1322

- **Código:** 1.3.2.2
- **Denominación:** Interfaz de edición de metadatos (modificación)
- **Objetivo:** Facilitar la edición, enriquecimiento y categorización clínica de las señales almacenadas.
- **Descripción:** Interfaz administrativa que permite a los investigadores autorizados modificar datos contextuales de las señales (edad del paciente, diagnóstico según CIE-10/SNOMED, derivaciones utilizadas, medicamentos o eventos marcadores), registrando auditoría de cada modificación.
- **Prerequisitos:** 1.3.2.1 Formulario y procesador de carga funcional.
- **Actividades:**

| Código    | Actividad                             | Alcance                                                                                                                  | Cálculo de tiempo                                                                                                                                              | Tiempo est. | Costo estimado | Riesgo                                                                  | P   | I   | P×I | Mitigación                                                                                         | Tiempo prevención | Costo gestión | Tiempo adicional | Costo contingencia | Duración total | Costo total |
| --------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------------- | ----------------------------------------------------------------------- | --- | --- | --- | -------------------------------------------------------------------------------------------------- | ----------------- | ------------- | ---------------- | ------------------ | -------------- | ----------- |
| 1.3.2.2.A | Diseño de la página                   | Maqueta del formulario de edición y de la vista de historial de cambios                                                  | Tres valores: (9 + 12 + 15) / 3 = 12 h                                                                                                                         | 12 h        | $120.000       | Catálogos de diagnósticos mal definidos que obligan a rehacer el diseño | 3   | 3   | 9   | Definir un catálogo cerrado reducido antes de diseñar                                              | 1 h               | $10.000       | 4 h              | $40.000            | 17 h           | $170.000    |
| 1.3.2.2.B | Implementar la UI                     | Formulario con selectores de catálogos cerrados, validación de campos y pantalla de historial de modificaciones          | Tres valores: (22 + 28 + 34) / 3 = 28 h                                                                                                                        | 28 h        | $280.000       | Formulario con muchos campos que genera retrabajo                       | 3   | 3   | 9   | Reutilizar componentes de 1.3.2.1.B y hacer una revisión intermedia                                | 2 h               | $20.000       | 8 h              | $80.000            | 38 h           | $380.000    |
| 1.3.2.2.C | Funcionalidad de editar los metadatos | Backend que actualiza metadatos, aplica los catálogos y genera el registro de auditoría (autor, fecha, campo modificado) | Descomposición: actualización de metadatos 14 h + validación contra catálogos 10 h + registro de auditoría 14 h + prueba de integridad del binario 10 h = 48 h | 48 h        | $480.000       | La edición corrompe o reescribe la señal cruda original                 | 2   | 5   | 10  | Metadatos en tabla separada, binario de solo lectura y prueba de integridad (hash) antes y después | 5 h               | $50.000       | 12 h             | $120.000           | 65 h           | $650.000    |

- **Criterios de aceptación:** Cambios reflejados de inmediato en las consultas; generación obligatoria del registro de autor, fecha y campo modificado.
- **Supuestos:** La edición de metadatos no corrompe ni reescribe la señal biológica cruda original.

#### Paquete de Trabajo: 1.3.2.3 ^p-1323

- **Código:** 1.3.2.3
- **Denominación:** Mecanismo de baja lógica (baja)
- **Objetivo:** Ocultar registros obsoletos o erróneos del catálogo público sin destruir la información física, preservando la trazabilidad.
- **Descripción:** Lógica de software que implementa la desactivación de registros mediante banderas de estado (`is_deleted = true`, fecha y motivo), excluyéndolos de las búsquedas habituales pero permitiendo su eventual auditoría o restauración por administradores.
- **Prerequisitos:** 1.3.2.1 Formulario de alta y 1.3.1.4 Roles de usuario configurados.
- **Actividades:**

| Código    | Actividad                    | Alcance                                                                                                                    | Cálculo de tiempo                                                                                                            | Tiempo est. | Costo estimado | Riesgo                                                      | P   | I   | P×I | Mitigación                                                 | Tiempo prevención | Costo gestión | Tiempo adicional | Costo contingencia | Duración total | Costo total |
| --------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ----------- | -------------- | ----------------------------------------------------------- | --- | --- | --- | ---------------------------------------------------------- | ----------------- | ------------- | ---------------- | ------------------ | -------------- | ----------- |
| 1.3.2.3.A | Diseño de la página          | Maqueta del botón de baja, el cuadro de confirmación con motivo y la vista de registros dados de baja para administradores | Tres valores: (2 + 3 + 4) / 3 = 3 h                                                                                          | 3 h         | $30.000        | Diseño del motivo de baja poco claro (riesgo menor)         | 1   | 2   | 2   | Aceptar; reutilizar el estilo de los diálogos ya diseñados | 0 h               | $0            | 1 h              | $10.000            | 4 h            | $40.000     |
| 1.3.2.3.B | Implementar la UI            | Botón de baja con confirmación y motivo obligatorio, y listado de bajas con opción de restaurar (solo administradores)     | Tres valores: (6 + 8 + 10) / 3 = 8 h                                                                                         | 8 h         | $80.000        | Baja accidental de un registro equivocado                   | 3   | 3   | 9   | Confirmación con motivo obligatorio y opción de restaurar  | 1 h               | $10.000       | 3 h              | $30.000            | 12 h           | $120.000    |
| 1.3.2.3.C | Funcionalidad de baja lógica | Baja lógica, guarda fecha y motivo, excluye bajas de las búsquedas y permite la restauración por administradores           | Descomposición: bandera y migración 4 h + registro de fecha y motivo 4 h + filtro en búsquedas 5 h + restauración 5 h = 18 h | 18 h        | $180.000       | Registros dados de baja que siguen apareciendo en consultas | 3   | 4   | 12  | Filtro único en la capa de consulta y pruebas de búsqueda  | 2 h               | $20.000       | 4 h              | $40.000            | 24 h           | $240.000    |

- **Fechas:** Semanas 14 a 15.
- **Criterios de aceptación:** El registro desaparece inmediatamente de las búsquedas generales pero permanece intacto en base de datos con justificación del borrado.
- **Supuestos:** Cumplimiento de políticas de retención de datos científicos que prohíben la pérdida irreversible de registros.

### 1.3.3 Módulo de consulta y visualización

#### Paquete de Trabajo: 1.3.3.1 ^p-1331

- **Código:** 1.3.3.1
- **Denominación:** Motor de búsqueda y filtrado por metadatos
- **Objetivo:** Proveer a los usuarios una herramienta ágil y precisa para localizar registros de señales bajo múltiples criterios.
- **Descripción:** Mecanismo de consulta avanzada que indexa metadatos y permite filtrar registros biomédicos por tipo de señal (ECG, EEG, EMG), patología asociada, edad, género, frecuencia de muestreo, cantidad de derivaciones y fecha de captura.
- **Prerequisitos:** 1.3.2.1 y 1.3.2.2 completados con datos indexados.
- **Actividades:**

1. Crear índices compuestos y de texto completo en la base de datos.
2. Diseñar la barra de búsqueda y el panel de filtros facetados en el frontend.
3. Implementar paginación optimizada en backend.

- **Fechas:** Semanas 15 a 17.
- **Criterios de aceptación:** Tiempo de respuesta de consulta inferior a 500 ms sobre un catálogo de al menos 50.000 registros indexados.
- **Supuestos:** Los metadatos de las señales se encuentran completos y normalizados.

#### Paquete de Trabajo: 1.3.3.2 ^p-1332

- **Código:** 1.3.3.2
- **Denominación:** Renderizador interactivo de señales
- **Objetivo:** Visualizar de forma gráfica e interactiva las series temporales de señales biomédicas en el navegador sin retrasos.
- **Descripción:** Componente web de alto rendimiento basado en Canvas/WebGL que permite visualizar múltiples canales simultáneos, realizar acercamientos (_zoom in/out_), paneos temporales, ajuste de amplitud y colocación de marcadores/calipers para mediciones de intervalos (como complejos QRS o trenes de pulsos).
- **Prerequisitos:** 1.3.2.1 Procesador de señales y 1.3.3.1 Motor de búsqueda listos.
- **Actividades:**

1. Implementar algoritmo de submuestreo visual (LTTB - _Largest-Triangle-Three-Buckets_) para reducir la carga de puntos sin alterar la morfología de la señal.
2. Desarrollar el visor gráfico interactivo con soporte multicanal sincronizado.
3. Incorporar herramientas interactivas de medición de amplitud y tiempo sobre la gráfica.

- **Fechas:** Semanas 16 a 19.
- **Criterios de aceptación:** Visualización fluida a 60 FPS con capacidad de renderizar señales de hasta 1.000.000 de muestras sin congelamiento del navegador.
- **Supuestos:** Los navegadores de los clientes soportan estándares modernos de HTML5 y WebGL.

#### Paquete de Trabajo: 1.3.3.3 ^p-1333

- **Código:** 1.3.3.3
- **Denominación:** Herramienta de exportación de registros
- **Objetivo:** Permitir la descarga de señales biomédicas y sus metadatos en formatos estándar compatibles con entornos de procesamiento científico.
- **Descripción:** Servicio de empaquetado y conversión que permite exportar registros seleccionados en formatos universales (CSV, JSON, EDF y MATLAB `.mat`), acompañados de un archivo complementario con los metadatos clínicos y descriptores técnicos.
- **Prerequisitos:** 1.3.3.1 Motor de búsqueda y 1.3.2.1 Procesador de señales.
- **Actividades:**

1. Desarrollar módulos backend para la conversión al vuelo entre formatos de señales.
2. Implementar compresión de archivos por lotes (ZIP).
3. Integrar registro de descargas en la bitácora de auditoría.

- **Fechas:** Semanas 18 a 20.
- **Criterios de aceptación:** Exportación completada sin pérdida de precisión de punto flotante en las muestras y archivos validados con librerías estándar (ej. MNE-Python, WFDB).
- **Supuestos:** Capacidad de almacenamiento temporal en servidor suficiente para generar paquetes de descarga grandes.

## 1.4 Aseguramiento de Calidad

### Paquete de Trabajo: 1.4.1 ^p-141

- **Código:** 1.4.1
- **Denominación:** Reporte de pruebas unitarias
- **Objetivo:** Validar el correcto funcionamiento de los componentes algorítmicos y funciones individuales de forma aislada.
- **Descripción:** Informe técnico que documenta el diseño, ejecución y resultados de las baterías de pruebas automatizadas sobre la lógica de negocio: algoritmos de procesamiento de señales, validadores de formatos, parseo de metadatos y reglas de negocio del RBAC.
- **Prerequisitos:** Módulos de desarrollo de la sección 1.3 implementados.
- **Actividades:**

1. Redactar suites de pruebas unitarias con frameworks estándar (PyTest / Jest / JUnit).
2. Ejecutar análisis de cobertura de código (_code coverage_).
3. Consolidar métricas y generar el reporte formal de ejecución.

- **Fechas:** Semanas 19 a 21.
- **Criterios de aceptación:** Cobertura de código superior al 80% en lógica crítica de negocio y 100% de pruebas unitarias ejecutadas satisfactoriamente (cero fallas).
- **Supuestos:** Los componentes fueron desarrollados siguiendo principios de código desacoplado y testeable.

### Paquete de Trabajo: 1.4.2 ^p-142

- **Código:** 1.4.2
- **Denominación:** Reporte de pruebas de integración y aceptación
- **Objetivo:** Validar el comportamiento de los módulos integrados y certificar la conformidad del sistema frente a las necesidades clínicas y científicas del usuario final.
- **Descripción:** Informe que certifica la ejecución de pruebas extremo a extremo (E2E), pruebas de estrés y rendimiento, y las pruebas de aceptación de usuario (UAT) realizadas directamente por un grupo de prueba conformado por médicos e investigadores.
- **Prerequisitos:** 1.4.1 Reporte de pruebas unitarias aprobado y despliegue en entorno de pruebas (1.2.2).
- **Actividades:**

1. Ejecutar pruebas automatizadas de integración de API y base de datos.
2. Conducir pruebas de carga para evaluar la respuesta ante múltiples solicitudes de renderizado.
3. Coordinar sesiones UAT con médicos e investigadores documentando incidencias.
4. Redactar el reporte final de hallazgos y cierre de observaciones.

- **Fechas:** Semanas 21 a 23.
- **Criterios de aceptación:** Cero defectos críticos o bloqueantes abiertos, aprobación formal por parte del 100% de los evaluadores UAT designados.
- **Supuestos:** Disponibilidad del personal clínico para participar en los talleres de prueba.

## 1.5 Despliegue Final

### Paquete de Trabajo: 1.5 ^p-15

- **Código:** 1.5
- **Denominación:** Sistema desplegado en ambiente de producción
- **Objetivo:** Poner en marcha y dejar en régimen operativo el sistema integral del Banco de Señales Biomédicas accesible para la comunidad usuaria.
- **Descripción:** Ejecución de la puesta en producción en la infraestructura final, que incluye la migración de bases de datos, verificación de dominios, instalación de certificados de seguridad, configuración de copias de seguridad automáticas, monitoreo de disponibilidad y ejecución de pruebas de humo (_smoke testing_).
- **Prerequisitos:** 1.2.1 Infraestructura productiva lista y 1.4.2 Pruebas de aceptación formalmente aprobadas.
- **Actividades:**

1. Ejecutar el pipeline de despliegue a producción de la versión final estable (_release candidate_).
2. Ejecutar scripts de inicialización y migración definitiva de datos.
3. Verificar políticas de seguridad, encabezados HTTP y certificados SSL.
4. Realizar prueba de humo de todos los flujos clave (ingreso, carga, búsqueda, renderizado y descarga).

- **Fechas:** Semanas 23 a 24 (Hito: Puesta en Producción).
- **Criterios de aceptación:** Sistema 100% accesible vía web pública/institucional, tiempo de disponibilidad inicial de 99.9%, sin errores en logs y prueba de humo superada al 100%.
- **Supuestos:** Disponibilidad de la ventana de mantenimiento y red sin bloqueos perimetrales.
