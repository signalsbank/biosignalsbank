---
project: BioSignal
version: 2
title: 2. Acta de Constitución
aliases:
  - Acta de Constitución
authors: Mateo Astudillo, Ignacio Ávila
---

# **Acta de Constitución del Proyecto**

**Nombre del Proyecto:** BioSignal — Banco de Señales Biomédicas de la Universidad Nacional de Villa Mercedes (UNViMe)

## 1. Director del Proyecto y Equipo del Proyecto

### Director y Asistente del Proyecto

- **Director del Proyecto:** Astudillo, Mateo Tomás
- **Asistente del Director del Proyecto:** Ávila Gelbes, Ignacio Nicolás

### Responsabilidad y Nivel de Autoridad del Director del Proyecto

- **Autoridad:**
  - Asignación y redistribución de tareas dentro del equipo.
  - Punto de contacto formal para escalamiento de riesgos y coordinación con las autoridades de la UNViMe.
- **Responsabilidad:**
  - Gestionar el proyecto

### Equipo del Proyecto

| Nombre                            | Rol y Responsabilidad                      |
| :-------------------------------- | :----------------------------------------- |
| **Astudillo, Mateo Tomás**        | Director del Proyecto (PM)                 |
| **Ávila Gelbes, Ignacio Nicolás** | Asistente del Director del Proyecto        |
| **Herrera, Germán Ezequiel**      | Desarrollador Backend / QA                 |
| **Mosainer, Martín David**        | Desarrollador Full-Stack / Soporte Técnico |
| **Chiecher, Eber Blas**           | Desarrollador Backend / Infraestructura    |
| **Pereyra, Rocío Valentina**      | Desarrolladora Frontend                    |

## 2. Patrocinadores y Autorizadores

- **Patrocinador Institucional (Sponsor):** Universidad Nacional de Villa Mercedes (UNViMe), a través de la Escuela de Ingeniería y Ciencias Ambientales (EICA), representada por su director, Ing. Alejandro Rosas.

## 3. Necesidades del Cliente

- **Necesidad del grupo de administradores de Bioingeniería:**
  - **Plataforma de carga centralizada:** Disponer de un repositorio único para almacenar y organizar señales biomédicas fisiológicas.
  - **Gestión de datos:** Interfaz de administración para cargar datos del registro (frecuencia de muestreo, canales, unidades).
  - **Compatibilidad con EDF (European Data Format):** Compatibilidad ".edf" para asegurar que el visor gráfico pueda interpretarlos sin errores.
- **Necesidad del Usuario Final / Consumidor (Estudiantes y Docentes de Medicina y Salud):**
  - **Entorno web:** Acceso directo vía navegador web a señales clínicas reales para ejercitación académica.
  - **Visualización interactiva:** Capacidad de analizar registros gráficos.

## 4. Restricciones del Proyecto

- **Restricciones de Tiempo y Calendario:**
  - El proyecto debe finalizar el **15 de febrero de 2027** para adaptarse al cierre del calendario académico lectivo.
- **Restricciones Económicas y de Recursos:**
  - Despliegue bajo esquema de desembolso directo de **$0 USD** en infraestructura comercial (moneda declarada), priorizando el uso de servidores institucionales de la UNViMe o plataformas _cloud_ en capas gratuitas (ej. Vercel).
- **Restricciones Técnicas:**
  - Soporte exclusivo para archivos biomédicos estándar .edf (European Data Format).
  - Funcionamiento en navegadores web modernos sin instalación de plugins, clientes de escritorio ni extensiones.
- **Restricciones Legales:**
  - Anonimización absoluta e irreversible de cualquier dato personal o clínico de pacientes reales en cumplimiento con normativas éticas de salud.

## 5. Propósito del Proyecto

Mejorar la experiencia de los estudiantes y docentes de carreras a la salud a la hora de analizar señales biomédicas.

## 6. Objetivos Medibles del Proyecto y Criterios de Éxito

| ID       | Objetivo                            | Métrica                                                                                                                        | Fecha      | Verificación                    |
| :------- | :---------------------------------- | :----------------------------------------------------------------------------------------------------------------------------- | :--------- | :------------------------------ |
| **O-01** | Autenticación y RBAC con dos roles  | 2 roles (Administrador / Consultor); expiración de sesión Admin a los 30 min; 0 hallazgos críticos de elevación de privilegios | 18/12/2026 | Pruebas de seguridad y QA       |
| **O-02** | Ingesta, sanitización y baja lógica | 30 EDF (15 ECG + 15 EEG); 0 % de PII residual en cabecera, TALs y metadatos; ≤ 30 s por archivo < 50 MB                        | 15/01/2027 | Auditoría binaria + benchmark   |
| **O-03** | Visualizador interactivo            | 32 canales; ≥ 30 FPS; ≤ 2,5 s hasta el primer segmento interactivo en ≥ 10 Mbps; 100 usuarios concurrentes                     | 29/01/2027 | Lighthouse, DevTools, k6/JMeter |
| **O-04** | Exportación y acceso público        | Descarga de EDF sanitizado; señal demo sintética o anonimizada; enlace a admisiones                                            | 29/01/2027 | Prueba funcional + inspección   |
| **O-05** | Desplegar en producción             | Dominio `*.unvime.edu.ar`; TLS 1.3; backup/restore probado; smoke test 100 %                                                   | 12/02/2027 | Acta TIC + QA                   |
| **O-06** | Cerrar el proyecto                  | 0 defectos críticos/bloqueantes; acta de cierre firmada;                                                                       | 15/02/2027 | Sponsor + PM                    |
| **O-07** | Cumplir la línea base de gestión    | Variación de esfuerzo/costo ≤ 10 %; 100 % de cambios registrados                                                               | 15/02/2027 | EVM + Change Log                |

### Criterios de Éxito por Parte Interesada

| Parte Interesada                                  | Criterio de Éxito Específico                                                            | Tipo                            | Evidencia                |
| :------------------------------------------------ | :-------------------------------------------------------------------------------------- | :------------------------------ | :----------------------- |
| **Patrocinador (EICA / Autoridades)**             | Sistema en producción con desembolso directo de **$0 USD** y acta de aceptación firmada | Proyecto                        | Actas + registro de caja |
| **GAB (Grupo de Bioingeniería)**                  | 30 EDF catalogados, 0 % de PII residual, metadatos completos                            | Producto                        | Inventario + auditoría   |
| **Estudiantes y docentes (ECS / EM)**             | 50 usuarios completan "buscar–abrir–configurar" en **< 5 minutos** (RNF-09)             | Beneficio (se mide post-cierre) | UAT + guías de cátedra   |
| **Dirección TIC (UNViMe)**                        | Despliegue, monitoreo, backup y restore verificados                                     | Producto                        | Checklist de transición  |
| **Equipo de Desarrollo del Proyecto (PM y Devs)** | Concluir el alcance planificado dentro del rango de 260 a 360 horas de trabajo          | Proyecto                        | EVM + retrospectivas     |

## 7. Requisitos de Alto Nivel

### 1. Objetivos del Negocio y Justificación

- **Autonomía y Soberanía de Datos:** Proveer a la UNViMe de una plataforma propia y centralizada para almacenar, catalogar y gobernar registros biomédicos bajo control institucional directo.
- **Integración Académica y Curricular:** Incorporar la plataforma como herramienta pedagógica formal en cátedras de procesamiento de bioseñales a partir del primer semestre de 2027.
- **Divulgación Institucional:** Servir como canal público interactivo para visibilizar la oferta académica de Bioingeniería y carreras de la salud afines.
- **Comunidad Académica (Docentes y Estudiantes):** Acceso ágil a un banco de casos clínicos para docencia y práctica.
- **Grupo de Investigación (GAB):** Infraestructura segura y estandarizada para centralizar, preservar y organizar registros biomédicos hospitalarios.
- **Seguridad y Control de Acceso:** Autenticación por roles (Administrador y Consultor) y un portal público demostrativo sin autenticación.
- **Ingesta y Anonimización Conforme a la Ley:** Carga y validación estructural de registros en formato estándar `.edf`/`.edf+`, con anonimización irreversible obligatoria de datos sensibles del paciente (Ley 25.326).
- **Visualizador de Bioseñales:** Interfaz interactiva multicanal con capacidades de zoom, paneo, calibración de escalas clínicas estándar.
- **Gestión y Exportación:** Catalogación con metadatos docentes/clínicos y descarga de archivos autorizados.
- **Fecha Deseada:** Puesta en producción el **12 de febrero de 2027** (Hito H7) y cierre formal del proyecto el **15 de febrero de 2027**, para el inicio del ciclo lectivo.

## 8. Descripción, Límites y Entregables Claves

### **Descripción**

El proyecto **"BioSignal"** consiste en desarrollar una plataforma web para la carga, gestión y visualización de bancos de señales biomédicas. El sistema permitirá a los Estudiantes de Bioingeniería (EB) cargar señales propias en formato ".edf" para que la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM) las utilicen interactivamente con fines didácticos, superando la limitación del sistema LightWAVE de PhysioNet que no permite la carga personalizada de registros.

### **Límites (Alcance)**

- **Incluye:**
  - Módulo de administración para carga y catálogo de registros.
  - Visualizador interactivo en navegador.
  - Módulo de descarga de archivos en formato EDF sanitizado.
- **Excluye:**
  - Módulo de anotaciones clínicas, etiquetado de eventos o herramientas de medición/calibradores sobre la señal.
  - Registro público de usuarios y recuperación autónoma de credenciales (las cuentas las crea el Administrador).
  - Roles adicionales al Administrador y Consultor.
  - Exportación a formatos distintos de EDF/EDF+ (CSV, JSON, MATLAB).
  - Conexión física o captura en tiempo real desde equipamiento de hardware biomédico.
  - Módulos de diagnóstico automático, algoritmos de detección clínica o toma de decisiones médicas (uso 100% educativo).
  - Sustitución de software de procesamiento médico avanzado certificado para uso hospitalario.

### **Entregables Clave**

**Entregables de Producto (EP):**

1. **EP-01 — Autenticación y control de acceso por roles (RBAC):** Administrador y Consultor; sesión Admin expira a los 30 min.
2. **EP-02 — Ingesta, sanitización y baja lógica:** carga EDF/EDF+, validación, anonimización irreversible y baja lógica auditada.
3. **EP-03 — Visualizador interactivo de señales:** render ≥ 30 FPS, paneo, zoom y escalas clínicas.
4. **EP-04 — Acceso público y enlace institucional:** señal demo y banner a admisiones.
5. **EP-05 — Exportación de registros:** archivo EDF sanitizado e íntegro.
6. **EP-06 — Dataset semilla:** 30 EDF catalogados (15 ECG + 15 EEG).

**Entregables de Proyecto (EJ):**

1. **EJ-01 — Acta de Constitución** aprobada y versionada.
2. **EJ-02 — ERS + Matriz de Trazabilidad** aprobadas.
3. **EJ-03 — Repositorios de código** versionados con CI.
4. **EJ-04 — Reporte consolidado de QA.**
5. **EJ-05 — Acta de despliegue** en producción.
6. **EJ-06 — Acta de cierre** con lecciones aprendidas.

## 9. Riesgos, Supuestos y Dependencias

- **Supuestos:**
  - Los usuarios finales disponen de conexión a internet estable y dispositivos con navegadores web modernos.
  - El grupo de administradores de Bioingeniería proveerán archivos de señal biomédica de prueba debidamente anonimizados de manera oportuna.
- **Restricciones:**
  - Desarrollo estrictamente acotado al rango de 260 a 360 horas de esfuerzo dentro de la línea base aprobada: **02/11/2026 al 15/02/2027 (15 semanas)**.
- **Dependencias:**
  - Disponibilidad y configuración de la infraestructura de servidor/alojamiento provista por la UNViMe.
- **Riesgos Principales:**
  - **R1 (Retraso en entrega de datos):** Demora en la provisión de archivos EDF reales por parte del grupo de administradores de Bioingenieria para la etapa de pruebas. _Mitigación:_ Obtener señales de otras fuentes desde el Hito 1.
  - **R2 (Rendimiento del visualizador):** Latencia o congelamiento del navegador al graficar registros muy extensos. _Mitigación:_ Utilizar parseo por bloques (chunking) y renderizado acelerado con HTML5 Canvas/WebGL.
  - **R3 (Disponibilidad del equipo):** Reducción de horas de desarrollo durante períodos de exámenes. _Mitigación:_ Planificar un margen de flexibilidad en el cronograma entre los Hitos 2 y 3.

## 10. Cronograma de Hitos de Aceptación

| Hito de Aceptación                            | Fecha Objetivo                  | Criterio de Salida                                                             |
| :-------------------------------------------- | :------------------------------ | :----------------------------------------------------------------------------- |
| **H1 — Acta aprobada**                        | 02/11/2026                      | Acta firmada; glosario y línea base v1.0                                       |
| **H2 — Requisitos aprobados**                 | 13/11/2026                      | ERS + RTM + criterios de aceptación firmados                                   |
| **H3 — Autenticación/RBAC aceptado**          | 18/12/2026                      | 2 roles; sesión 30 min; 0 hallazgos críticos de elevación de privilegios       |
| **H4 — Ingesta y sanitización aceptadas**     | 15/01/2027                      | 30 EDF cargados; 0 % de PII residual; ≤ 30 s por archivo < 50 MB               |
| **H5 — Visualizador y exportación aceptados** | 29/01/2027                      | 32 canales; ≥ 30 FPS; ≤ 2,5 s; exportación EDF sanitizada                      |
| **H6 — QA/UAT cerrado**                       | 05/02/2027                      | 0 defectos críticos/bloqueantes; UAT aprobada                                  |
| **H7 — Despliegue y cierre**                  | 12/02/2027 (cierre: 15/02/2027) | Producción en `*.unvime.edu.ar`; TLS 1.3; backup/restore probado; acta firmada |

## 11. Estimación de Costos y Recursos

### **Presupuesto y Sostenibilidad**

- **Desembolso de caja (Presupuesto Financiero):** **$0 USD** (moneda declarada: USD). Sin erogaciones monetarias en infraestructura comercial: se utilizan servidores institucionales de la UNViMe o plataformas _cloud_ en capas gratuitas (ej. Vercel/Render).
- **Costo interno de esfuerzo (no erogable):** se controla en **ARS** con valor hora de referencia de **$10.000 ARS/h**, dentro del rango de 260–360 h declarado como límite del proyecto.
- **Insumos en especie / sin cargo:** los servicios ya provistos o donados (VPS de pruebas, dominio institucional, pentesting, diseño UI/UX, dataset, herramientas de IA) se tratan como **aportes en especie** y se registran en el plan de adquisiciones; no constituyen desembolso de caja.

## 12. Interesados Clave (Stakeholders)

1. **Patrocinador Institucional (Sponsor):** Escuela de Ingeniería y Ciencias Ambientales (EICA) - Alejandro Rosas.
2. **Colaboradores de Carga de Datos:** Grupo de administradores de Bioingeniería (GAB).
3. **Usuarios Finales / Clientes Académicos:** Estudiantes y Cuerpo Docente de la Escuela de Ciencias de la Salud (ECS) y Escuela de Medicina (EM).
4. **Proveedores de Infraestructura:** Dirección de Informática / TIC de la UNViMe.
5. **Equipo de Gestión y Desarrollo:** Director del Proyecto (Mateo Astudillo), Asistente de PM (Ignacio Ávila Gelbes) y Desarrolladores (Germán Herrera, Martín Mosainer, Eber Chiecher, Rocío Pereyra).

## 13. Requisitos de Aprobación del Proyecto

- **Criterios de Aprobación Final:**
  - Funcionamiento correcto y validado de los **6 entregables de producto (EP-01 a EP-06) y los 6 entregables de proyecto (EJ-01 a EJ-06)** descritos en la Sección 8.
  - Superación exitosa de las pruebas de QA.
- **Autoridad que Otorga la Aprobación:**
  - Director de la Escuela de Ingeniería y Ciencias Ambientales (EICA), Alejandro Rosas, en conjunto con el Director del Proyecto (Mateo Tomás Astudillo).

## 14. Criterios de Salida y Cierre del Proyecto

- **Cierre Normal / Exitoso:**
  - Despliegue completado de la versión Release 1.0 en el entorno de producción de la universidad antes del **12 de febrero de 2027** (Hito H7 — Despliegue), con cierre formal el **15 de febrero de 2027**.
  - Firma formal del Acta de Cierre por parte del Patrocinador y el Director del Proyecto.
- **Cierre Anticipado / Cancelación (Criterios de Salida):**
  - Imposibilidad técnica no solucionable para renderizar registros biomédicos en el navegador web respetando los estándares de tiempo y rendimiento.
  - Suspensión institucional del proyecto por parte de la UNViMe.
  - Falta prolongada e insuperable de disponibilidad de datos iniciales o infraestructura de servidores que impida la ejecución del proyecto con un retraso superior al 30% del cronograma total.

## 15. Registro de Cambios

| Versión | Fecha      | Cambio                                                                                                                                                     | Responsable | Estado    |
| :------ | :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- | :-------- |
| v1      | —          | Versión inicial                                                                                                                                            | PM          | Histórico |
| v2.0    | 29/10/2026 | Nombre canónico BioSignal, objetivos O-01…O-07, scorecard de éxito, entregables EP/EJ, hitos de aceptación H1–H7, presupuesto (caja vs. esfuerzo) y fechas | PM          | Aprobado  |
