# **Documento de requisitos**

## **Proyecto BioSignal — Banco de Señales Biomédicas**

**Universidad Nacional de Villa Mercedes (UNViMe)** — Carrera de Bioingeniería  
*Elaborado conforme a IEEE Std 830-1998 e ISO/IEC/IEEE 29148:2018*

* **Versión:** 1.0  
* **Fecha:** 1 de septiembre de 2026  
* **Director del Proyecto:** Mateo Tomás Astudillo  
* **Asistente de PM:** Ignacio Nicolás Ávila Gelbes

## **Control de Versiones**

| Campo | Detalle |
| :---- | :---- |
| Versión | 1.0 |
| Fecha | 01/09/2026 |
| Autor | Ignacio Nicolás Ávila Gelbes (Asistente de PM) |
| Revisado por | Mateo Tomás Astudillo (Director del Proyecto) |
| Estado | Borrador para aprobación del Patrocinador |
| Documento base | Acta de Constitución del Proyecto BioSignal (01/08/2026) |

## **1. Introducción**

### **1.1 Propósito del documento**

El presente documento tiene como propósito especificar de manera completa, clasificada y verificable los requisitos del proyecto BioSignal — Banco de Señales Biomédicas de la Universidad Nacional de Villa Mercedes (UNViMe) — a partir de las necesidades declaradas en el Acta de Constitución del Proyecto. Su elaboración sigue las buenas prácticas de la norma IEEE Std 830-1998 para especificaciones de requisitos de software (estructura del documento y atributos de calidad de cada requisito) y el marco de clasificación de tipos de requisitos definido por la norma ISO/IEC/IEEE 29148:2018 (requisitos de negocio, de interesados, de la solución, de transición, del proyecto y de calidad).

### **1.2 Alcance**

Este documento cubre la totalidad de los requisitos identificados para el desarrollo, despliegue y puesta en operación de la plataforma web BioSignal, destinada a la carga, gestión, visualización interactiva y anotación académica de señales biomédicas ".edf". No cubre el diseño detallado de la solución (arquitectura de software, modelo de datos, diagramas UML), el cual se desarrolla en documentos técnicos posteriores derivados de esta especificación.

### **1.3 Definiciones, Acrónimos y Abreviaturas**

| Término | Definición |
| :---- | :---- |
| BR | Business Requirement — Requisito de negocio. |
| StR | Stakeholder Requirement — Requisito de interesado. |
| SyR | System/Solution Requirement — Requisito de la solución (subdividido en RF y RNF). |
| RF / RNF | Requisito Funcional / Requisito No Funcional. |
| TR | Transition Requirement — Requisito de transición y preparación operativa. |
| PR | Project Requirement — Requisito del proyecto. |
| QR | Quality Requirement — Requisito de calidad. |
| EDF | European Data Format, formato estándar para el registro de señales biomédicas. |
| WFDB | WaveForm DataBase, biblioteca de PhysioNet para lectura de señales fisiológicas. |
| UNViMe | Universidad Nacional de Villa Mercedes. |
| ECS / EM | Escuela de Ciencias de la Salud / Escuela de Medicina de la UNViMe. |
| Scribe | Módulo de anotación y marcado de eventos fisiológicos sobre la señal. |
| QA | Quality Assurance — Aseguramiento de la calidad. |
| Verif. (I/A/D/T) | Método de verificación del requisito: Inspección, Análisis, Demostración o Prueba (Test). |

### **1.4 Referencias normativas**

* IEEE Std 830-1998 — IEEE Recommended Practice for Software Requirements Specifications.  
* ISO/IEC/IEEE 29148:2018 — Systems and software engineering — Life cycle processes — Requirements engineering.  
* Acta de Constitución del Proyecto BioSignal, UNViMe, 1 de agosto de 2026 (documento base).

### **1.5 Visión general del documento — metodología de clasificación**

Siguiendo ISO/IEC/IEEE 29148:2018, los requisitos se clasifican en seis categorías jerárquicas, presentadas en las Secciones 3 a 8 de este documento:

* **Requisitos del Negocio (BR):** expresan el propósito estratégico y el valor institucional que persigue la UNViMe con el proyecto.  
* **Requisitos de los Interesados (StR):** expresan las necesidades de cada parte interesada, agrupadas por interesado.  
* **Requisitos de la Solución (SyR):** traducen las necesidades anteriores en capacidades concretas del sistema, divididos en Funcionales (RF) y No Funcionales (RNF).  
* **Requisitos de Transición y Preparación Operativa (TR):** condiciones necesarias para pasar de la solución desarrollada a su operación real (migración de datos, despliegue, capacitación).  
* **Requisitos del Proyecto (PR):** restricciones de plazo, costo, esfuerzo y cronograma que enmarcan la ejecución del proyecto.  
* **Requisitos de Calidad (QR):** atributos de calidad transversales exigidos a la solución y al proceso, alineados con los criterios de éxito del Acta de Constitución.

Cada requisito incluye, conforme a IEEE 830, un identificador único, una descripción verificable, el o los interesados de origen, una prioridad y un criterio de aceptación medible, detallados en la Sección 9 y en el glosario de verificación de la Sección 10.

## **2. Descripción General**

### **2.1 Perspectiva del producto**

BioSignal es una plataforma web nueva e independiente. No sustituye software médico certificado ni sistemas de captura en tiempo real desde equipamiento biomédico; su función es educativa, complementando la formación práctica de Bioingeniería, Ciencias de la Salud y Medicina mediante un repositorio propio de señales, superando la limitación de carga personalizada que presenta LightWAVE de PhysioNet.

### **2.2 Interesados del proyecto**

| Código | Interesado |
| :---- | :---- |
| INT-01 | Patrocinador Institucional — Universidad Nacional de Villa Mercedes (UNViMe), autoridades directivas. |
| INT-02 | Colaboradores de carga de datos — Estudiantes y Docentes de la Carrera de Bioingeniería. |
| INT-03 | Usuarios finales / clientes académicos — Estudiantes y Docentes de la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM). |
| INT-04 | Equipo de Gestión y Desarrollo del Proyecto — Director de Proyecto, Asistente de PM y Desarrolladores. |

### **2.3 Restricciones generales**

* Plazo obligatorio de finalización: 27 de noviembre de 2026.  
* Costo directo de infraestructura: $0 USD, priorizando servidores institucionales o capas gratuitas de despliegue cloud.  
* Soporte exclusivo de archivos ".edf"; funcionamiento 100% en navegador, sin plugins ni clientes de escritorio.  
* Anonimización absoluta e irreversible de todo dato personal o clínico de pacientes reales.

### **2.4 Supuestos y dependencias**

* Los usuarios finales disponen de conexión a internet estable y navegadores web actualizados.  
* Las escuelas de la UNViMe proveerán oportunamente archivos de señal biomédica de prueba debidamente anonimizados.  
* La infraestructura de servidor/alojamiento provista por la UNViMe estará disponible y configurada a tiempo.

## **3. Requisitos del Negocio (BR)**

| ID | Descripción del Requisito | Interesado | Prioridad | Verif. | Criterio de Aceptación |
| :---- | :---- | :---- | :---- | :---- | :---- |
| BR-01 | La plataforma debe permitir a la UNViMe gestionar su propio catálogo local de señales biomédicas, reemplazando o complementando el uso del sistema externo LightWAVE de PhysioNet. | INT-01 | Alta | D | La plataforma opera de forma autónoma en producción, sin dependencia de LightWAVE, validado por el Patrocinador antes del 27/11/2026. |
| BR-02 | El proyecto debe generar una herramienta puente entre la formación técnica de Bioingeniería y la práctica docente de Ciencias de la Salud y Medicina. | INT-01, INT-02, INT-03 | Alta | D | La plataforma es adoptada como herramienta de trabajo práctico en al menos una cátedra de ECS y una de EM durante el ciclo lectivo 2026. |
| BR-03 | La solución debe desarrollarse y desplegarse bajo un esquema de costo directo $0 USD, sin comprometer presupuesto institucional en infraestructura comercial. | INT-01 | Alta | I | No se registran gastos de infraestructura de terceros al momento del cierre del proyecto. |
| BR-04 | El proyecto debe concluir dentro del período comprendido entre el 1 de agosto y el 27 de noviembre de 2026, en sincronía con el cierre del calendario académico lectivo. | INT-01, INT-04 | Alta | I | Acta de cierre del proyecto firmada en fecha igual o anterior al 27/11/2026. |

## **4. Requisitos de los Interesados (StR)**

### **INT-01 — Patrocinador Institucional (UNViMe)**

| ID     | Descripción del Requisito                                                                                  | Interesado | Prioridad | Verif. | Criterio de Aceptación                                                        |
| :----- | :--------------------------------------------------------------------------------------------------------- | :--------- | :-------- | :----- | :---------------------------------------------------------------------------- |
| StR-01 | El sistema debe operar sobre infraestructura gratuita o institucional, sin costos recurrentes de terceros. | INT-01     | Alta      | I      | Comprobante de costo $0 de infraestructura verificado al cierre del proyecto. |

### **INT-02 — Colaboradores de Bioingeniería (creadores de datos)**

| ID | Descripción del Requisito | Interesado | Prioridad | Verif. | Criterio de Aceptación |
| :---- | :---- | :---- | :---- | :---- | :---- |
| StR-02 | Se debe disponer de un repositorio web único para almacenar y organizar señales biomédicas fisiológicas. | INT-02 | Alta | D | Repositorio operativo con catálogo navegable de señales antes del 10/11/2026. |
| StR-03 | Se debe contar con una interfaz de administración para cargar y editar metadatos del registro (frecuencia de muestreo, canales, unidades). | INT-02 | Alta | T | Un usuario Administrador completa la carga de metadatos de un archivo en un tiempo medio inferior a 3 minutos. |
| StR-04 | El sistema debe validar automáticamente la compatibilidad de formato ".edf" al momento de la carga, informando errores de forma clara. | INT-02 | Alta | T | El 100% de los archivos con formato no soportado son rechazados con un mensaje de error explicativo antes de completar la carga. |

### **INT-03 — Usuarios Finales (Escuela de Ciencias de la Salud y Escuela de Medicina)**

| ID | Descripción del Requisito | Interesado | Prioridad | Verif. | Criterio de Aceptación |
| :---- | :---- | :---- | :---- | :---- | :---- |
| StR-05 | Se debe poder acceder a las señales clínicas directamente desde un navegador web, sin instalar software ni complementos. | INT-03 | Alta | D | El acceso y la visualización de una señal se logran desde Chrome, Firefox o Edge sin instalación adicional. |
| StR-06 | Se debe poder visualizar de forma interactiva los registros gráficos de las señales (zoom, paneo, escala). | INT-03 | Alta | D | El usuario aplica zoom y desplazamiento sobre una señal cargada sin recarga de página. |

### **INT-04 — Equipo de Gestión y Desarrollo del Proyecto**

| ID | Descripción del Requisito | Interesado | Prioridad | Verif. | Criterio de Aceptación |
| :---- | :---- | :---- | :---- | :---- | :---- |
| StR-07 | (CAMBIAR) El equipo debe poder ejecutar el proyecto dentro de un esfuerzo acumulado de entre 260 y 360 horas hombre. | INT-04 | Alta | I | Registro de horas acumuladas al cierre del proyecto dentro del rango establecido. |

## **5. Requisitos de la Solución (SyR)**

### **5.1 Requisitos Funcionales (RF)**

| ID | Descripción del Requisito | Interesado | Prioridad | Verif. | Criterio de Aceptación |
| :---- | :---- | :---- | :---- | :---- | :---- |
| RF-01 | El sistema debe implementar control de acceso diferenciado por roles: Consultor y Administrador. | INT-02, INT-03 | Alta | T | Un usuario Administrador accede a funciones de carga y catálogo; un usuario Estudiante/Docente accede solo a visualización y anotación. |
| RF-02 | El sistema debe permitir la carga de archivos biomédicos en formatos ".edf". | INT-02 | Alta | T | El sistema acepta y procesa correctamente al menos un archivo válido de cada formato soportado. |
| RF-03 | El sistema debe extraer automáticamente la frecuencia de muestreo y el número de canales del archivo cargado. | INT-02 | Alta | T | Los metadatos extraídos coinciden con los valores reales del archivo de prueba en el 100% de los casos evaluados. |
| RF-04 | El visor gráfico debe ofrecer desplazamiento (paneo) sobre el eje temporal de la señal. | INT-03 | Alta | D | El usuario se desplaza a lo largo de todo el registro sin pérdida de datos visibles. |
| RF-05 | El visor gráfico debe ofrecer zoom temporal sobre la señal. | INT-03 | Alta | D | El usuario aumenta o disminuye el nivel de detalle temporal manteniendo la fluidez de renderizado. |
| RF-06 | El visor gráfico debe permitir el ajuste de amplitud de la señal visualizada. | INT-03 | Media | D | El usuario modifica la escala vertical de la onda sin distorsionar los datos originales. |
| RF-07 | El visor gráfico debe permitir la selección de canales a visualizar cuando el registro contenga múltiples canales. | INT-03 | Baja | D | El usuario muestra u oculta canales individuales de un registro multicanal. |
| RF-08 | El sistema debe permitir la exportación/descarga de registros de señales en formato estandarizado EDF. | INT-02, INT-03 | Media | T | El archivo exportado en formato EDF es válido y reproducible en un lector EDF estándar. |

### **5.2 Requisitos No Funcionales (RNF)**

| ID     | Descripción del Requisito                                                                                                                                 | Interesado     | Prioridad | Verif. | Criterio de Aceptación                                                                                     |
| :----- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- | :-------- | :----- | :--------------------------------------------------------------------------------------------------------- |
| RNF-01 | Rendimiento (renderizado): el visor debe renderizar al menos 100 muestras en simultaneo con una latencia de carga inicial menor a 10 segundos.            | INT-03         | Alta      | T      | Pruebas de carga confirman ambos umbrales sobre un registro de referencia estándar.                        |
| RNF-02 | Compatibilidad: el sistema debe ser funcional en las últimas versiones de los navegadores modernos.                                                       | INT-03         | Alta      | T      | Pruebas funcionales completas ejecutadas exitosamente en los tres navegadores soportados.                  |
| RNF-03 | Privacidad: el sistema debe garantizar la anonimización absoluta e irreversible de cualquier dato personal o clínico antes del almacenamiento definitivo. | INT-01, INT-02 | Alta      | A      | Auditoría de datos almacenados no revela identificadores personales en el 100% de los registros evaluados. |
| RNF-04 | Disponibilidad: el sistema debe estar disponible durante el horario académico habitual sin interrupciones no planificadas.                                | INT-01, INT-03 | Media     | A      | Tiempo de actividad (uptime) registrado durante el período de uso académico sin incidentes críticos.       |

## **6. Requisitos de Transición y Preparación Operativa (TR)**

| ID    | Descripción del Requisito                                                                                                                                   | Interesado     | Prioridad | Verif. | Criterio de Aceptación                                                                                       |
| :---- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- | :-------- | :----- | :----------------------------------------------------------------------------------------------------------- |
| TR-01 | Se debe buscar un conjunto de señales de prueba desde el Hito 1, para no depender exclusivamente de la entrega de datos reales por parte de las facultades. | INT-04         | Alta      | D      | Al finalizar el Hito 1, el sistema cuenta con al menos un conjunto de señales de prueba cargado y navegable. |
| TR-02 | Se deben cargar y categorizar al menos 50 conjuntos de señales biomédicas (reales o de referencia) con sus metadatos antes del 10 de noviembre de 2026.    | INT-02         | Alta      | I      | El catálogo del sistema contiene 50 o más conjuntos de señales publicados y accesibles.                      |
| TR-03 | Se debe desplegar la plataforma en el servidor de producción definitivo (institucional o cloud gratuito) antes del cierre del proyecto.                     | INT-01, INT-04 | Alta      | D      | La URL de producción responde correctamente y aloja la versión Release 1.0.                                  |

## **7. Requisitos del Proyecto (PR)**

| ID    | Descripción del Requisito                                                                                                                                                   | Interesado     | Prioridad | Verif. | Criterio de Aceptación                                                                                  |
| :---- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------- | :-------- | :----- | :------------------------------------------------------------------------------------------------------ |
| PR-01 | El proyecto debe completarse dentro del período comprendido entre el 1 de agosto y el 27 de noviembre de 2026.                                                             | INT-01, INT-04 | Alta      | I      | Fecha de cierre formal igual o anterior al 27/11/2026.                                                  |
| PR-02 | El esfuerzo total de desarrollo acumulado debe mantenerse entre 260 y 360 horas de trabajo.                                                                                 | INT-04         | Alta      | I      | Registro de horas del equipo al cierre del proyecto dentro del rango definido.                          |
| PR-03 | El proyecto debe ejecutarse sin incurrir en costos de infraestructura de terceros (presupuesto de $0 en infraestructura comercial).                                         | INT-01         | Alta      | I      | No se registran gastos de infraestructura comercial al cierre del proyecto.                             |
| PR-04 | El cronograma de hitos (Hito 1 a Hito 5) debe cumplirse dentro de los períodos definidos, con un retraso acumulado no mayor al 30% del cronograma total.                   | INT-01, INT-04 | Alta      | I      | La fecha real de cada hito no excede el 30% de desviación acumulada respecto al cronograma planificado. |
| PR-05 | La disponibilidad de horas del equipo debe planificarse considerando el calendario académico y los períodos de exámenes, con margen de flexibilidad entre los Hitos 2 y 3. | INT-04         | Baja      | I      | El cronograma contempla explícitamente semanas de menor dedicación durante los períodos de exámenes.    |

## **8. Requisitos de Calidad (QR)**

| ID    | Descripción del Requisito                                                                                                                       | Interesado             | Prioridad | Verif. | Criterio de Aceptación                                                                                  |
| :---- | :---------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------- | :-------- | :----- | :------------------------------------------------------------------------------------------------------ |
| QR-01 | Todos los módulos entregados deben superar las pruebas de QA con cero fallas críticas antes de la fecha límite.                                 | INT-01, INT-04         | Alta      | I      | Reporte de QA del Hito 5 sin fallas críticas abiertas.                                                  |
| QR-02 | Seguridad de datos: los datos clínicos almacenados deben cumplir con anonimización irreversible conforme a normativas éticas de salud vigentes. | INT-01, INT-02, INT-03 | Alta      | A      | Ningún registro almacenado permite reidentificar a un paciente, verificado mediante auditoría de datos. |
| QR-03 | Portabilidad: la plataforma debe funcionar de manera equivalente en los navegadores modernos, sin diferencias funcionales perceptibles.         | INT-03                 | Media     | T      | Las pruebas cruzadas de funcionalidad no muestran diferencias entre navegadores.                        |
| QR-04 | Eficiencia operativa: el tiempo medio de carga por archivo para los colaboradores debe ser inferior a 3 minutos.                                | INT-02                 | Baja      | T      | El promedio medido en pruebas de usuario es igual o inferior a 3 minutos por archivo.                   |

## **9. Clasificación y Trazabilidad**

### **9.1 Clasificación por interesado**

| Interesado                                   | Requisitos que lo involucran (cantidad e IDs)                                                              |
| :------------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| INT-01 — Patrocinador Institucional (UNViMe) | (16) BR-01, BR-02, BR-03, BR-04, StR-01, RNF-03, RNF-04, TR-03, PR-01, PR-03, PR-04, QR-01, QR-02          |
| INT-02 — Colaboradores de Bioingeniería      | (12) BR-02, StR-02, StR-03, StR-04, RF-01, RF-02, RF-03, RF-08, RNF-03, TR-02, QR-02, QR-04                |
| INT-03 — Usuarios Finales (ECS / EM)         | (18) BR-02, StR-05, StR-06, RF-01, RF-04, RF-05, RF-06, RF-07, RF-08, RNF-01, RNF-02, RNF-04, QR-02, QR-03 |
| INT-04 — Equipo de Gestión y Desarrollo      | (11) BR-04, StR-07, TR-01, TR-03, PR-01, PR-02, PR-04, PR-05, QR-01                                        |

### **9.2 Clasificación por prioridad**

La prioridad de cada requisito se estableció en función de su criticidad para el cumplimiento de los objetivos SMART y los criterios de éxito por interesado definidos en el Acta de Constitución (Sección 6): **Alta** (indispensable para el cierre exitoso del proyecto), **Media** (necesario, pero sin bloquear la entrega si se posterga) y **Baja** (deseable, mejora la solución sin condicionar su aceptación).

| Prioridad | Requisitos (cantidad e IDs)                                                                                                                                                                                  |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Alta (33) | BR-01, BR-02, BR-03, BR-04, StR-01, StR-02, StR-03, StR-04, StR-05, StR-06, StR-07, RF-01, RF-02, RF-03, RF-04, RF-05, RNF-01, RNF-02, RNF-03, TR-01, TR-02, TR-03, PR-01, PR-02, PR-03, PR-04, QR-01, QR-02 |
| Media (7) | RF-06, RF-08, RNF-04, QR-03                                                                                                                                                                                  |
| Baja (4)  | RF-07, PR-05, QR-04                                                                                                                                                                                          |

### **9.3 Distribución por categoría de requisito**

| Categoría (ISO/IEC/IEEE 29148)                       | Cantidad de requisitos |
| :---------------------------------------------------- | :--------------------- |
| Requisitos del Negocio (BR)                           | 4                      |
| Requisitos de los Interesados (StR)                   | 7                      |
| Requisitos de la Solución — Funcionales (RF)          | 8                      |
| Requisitos de la Solución — No Funcionales (RNF)      | 4                      |
| Requisitos de Transición y Preparación Operativa (TR) | 3                      |
| Requisitos del Proyecto (PR)                          | 5                      |
| Requisitos de Calidad (QR)                            | 4                      |
| **TOTAL**                                             | **35**                 |

## **10. Criterios de Verificación y Validación**

| Código | Método de verificación                                                                                                       |
| :----- | :--------------------------------------------------------------------------------------------------------------------------- |
| I      | Inspección — revisión documental o de artefactos entregados (actas, manuales, comprobantes, registros).                      |
| A      | Análisis — evaluación técnica, cálculo o auditoría (p. ej. auditoría de anonimización de datos).                             |
| D      | Demostración — ejecución guiada de una funcionalidad ante un evaluador, sin instrumentación formal.                          |
| T      | Prueba (Test) — ejecución de casos de prueba con medición cuantitativa de resultados (rendimiento, tiempos, tasas de error). |

La validación integral de los requisitos de prioridad Alta se realiza durante el Hito 5 (QA, Optimización y Entrega Final, 11/Nov–27/Nov 2026), condición de aprobación establecida en la Sección 13 del Acta de Constitución: superación de las pruebas de QA con cero fallas críticas.

## **11. Aprobación del Documento**
Con la firma del presente documento, el Patrocinador y el Director del Proyecto validan la completitud y corrección de los requisitos aquí especificados como base formal para el diseño y desarrollo de la plataforma BioSignal.

| Firma                                  | Rol                                        | Fecha |
| :------------------------------------- | :----------------------------------------- | :---- |
| [Nombre del Representante de UNViMe] | Representante Institucional (Patrocinador) |       |
| Astudillo, Mateo Tomás                 | Director del Proyecto (PM)                 |       |
| Ávila Gelbes, Ignacio Nicolás          | Asistente de PM                            |       |
