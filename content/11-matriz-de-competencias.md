---
project: BioSignal
version: 1.2
title: 11. Matriz de Competencias
aliases:
  - "Matriz de Competencias"
  - "Competencias"
---

## Matriz resumen de competencias

| Rol                                             | Persona asignada                | Educación                                                                      | Formación                                                                       | Habilidades                                                           | Experiencia                                                       |
| :---------------------------------------------- | :------------------------------ | :----------------------------------------------------------------------------- | :------------------------------------------------------------------------------ | :-------------------------------------------------------------------- | :---------------------------------------------------------------- |
| **Diseñador [[XX-abreviaciones#UX/UI\|UX/UI]]** | Rocío Pereyra                   | Formación terciaria/universitaria en diseño, comunicación visual o equivalente | Curso de UX/UI, Figma y accesibilidad [[XX-abreviaciones#WCAG\|WCAG]]           | Pensamiento visual, empatía, comunicación                             | +1 año en proyectos web; deseable visualización de datos          |
| **Frontend**                                    | Rocío Pereyra / Martín Mosainer | Estudiante avanzado o graduado en sistemas, computación o equivalente          | Next.js/React, TypeScript, Canvas/WebGL                                         | Optimización, resolución de problemas, trabajo colaborativo           | +2 años en frontend; deseable gráficos o datos en tiempo real     |
| **Backend**                                     | Germán Herrera / Eber Chiecher  | Estudiante avanzado o graduado en sistemas, computación o equivalente          | FastAPI/Python, PostgreSQL y seguridad web                                      | Lógica, diseño de [[XX-abreviaciones#API\|API]], trabajo colaborativo | +2 años en backend; deseable datos biomédicos o archivos binarios |
| **[[XX-abreviaciones#DBA\|DBA]]**               | Eber Chiecher                   | Formación afín + base de datos                                                 | PostgreSQL, modelado, backup/restore                                            | Análisis, rigurosidad, comunicación                                   | +3 años en administración o diseño de bases de datos              |
| **DevOps**                                      | Eber Chiecher                   | Formación afín + infraestructura                                               | Docker, [[XX-abreviaciones#CI/CD\|CI/CD]], Linux, [[XX-abreviaciones#TLS\|TLS]] | Resolución de problemas, proactividad                                 | +1 año en despliegue y administración de servidores               |
| **[[XX-abreviaciones#PM\|PM]]**                 | Mateo Astudillo                 | Estudiante avanzado o graduado en ingeniería/sistemas                          | [[XX-abreviaciones#PMBOK\|PMBOK]] 7, riesgos y [[XX-abreviaciones#EVM\|EVM]]    | Liderazgo, negociación, comunicación                                  | +3 años en gestión de proyectos de software                       |
| **[[XX-abreviaciones#APM\|APM]]**               | Ignacio Ávila                   | Estudiante avanzado o graduado en ingeniería/sistemas                          | Gestión documental, Scrum y seguimiento                                         | Organización, comunicación escrita                                    | No excluyente; proyectos académicos o de software                 |
| **QA**                                          | Germán Herrera                  | Estudiante avanzado o graduado en sistemas, computación o equivalente          | Testing automatizado, Playwright, k6 y [[XX-abreviaciones#OWASP\|OWASP]]        | Atención al detalle, pensamiento analítico                            | +1 año en testing de aplicaciones web                             |

> Los roles se comparten por tratarse de un equipo de 6 personas: una misma persona puede cubrir más de un rol. La asignación es la utilizada en este proyecto y debe validarse con el equipo al inicio de cada fase.

## 1. Diseñador UX/UI

- **Objetivo:** Diseñar una interfaz clara y autoexplicativa que permita a un usuario sin formación previa buscar, abrir y configurar una señal en menos de 5 minutos.
- **Responsabilidades:**
  - Garantizar la usabilidad y la coherencia visual de la plataforma.
  - Asegurar el diseño adaptativo (escritorio ≥ 1024 px y móvil < 768 px).
- **Funciones:**
  - Crear wireframes, prototipos y guía de estilos.
  - Diseñar el visualizador multicanal, el selector de canales y la sección pública.
  - Entregar los assets y especificaciones al frontend.
- **Nivel de autoridad:** Decide sobre el diseño visual e interacción.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Principios de usabilidad, accesibilidad web, diseño responsive, herramienta: Figma.
  - _Habilidades:_ Pensamiento visual, comunicación, empatía con el usuario, trabajo en equipo.
  - _Experiencia:_ +1 año en proyectos web; no excluyente: visualización de datos.

## 2. Programador Frontend (semi-senior)

- **Objetivo:** Implementar la interfaz web y el visualizador interactivo de bioseñales con alto rendimiento.
- **Responsabilidades:**
  - Desarrollar el visualizador (paneo, zoom X/Y, escalas clínicas, selector de canales).
  - Garantizar la compatibilidad cross-browser y el diseño responsive.
- **Funciones:**
  - Maquetar las pantallas según el diseño UX/UI.
  - Implementar el renderizado por fragmentos (chunking) con Canvas/WebGL.
  - Escribir pruebas unitarias y corregir los defectos reportados por QA.
- **Nivel de autoridad:** Decide la implementación técnica del frontend (librerías, estructura de componentes) dentro de los lineamientos del proyecto.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ [[XX-abreviaciones#HTML5|HTML5]], [[XX-abreviaciones#CSS|CSS]], JavaScript/TypeScript, framework: Next.js, Canvas/WebGL, Git.
  - _Habilidades:_ Optimización de rendimiento, resolución de problemas, trabajo colaborativo.
  - _Experiencia:_ +2 años en desarrollo frontend, no excluyente: con gráficos o datos en tiempo real.

## 3. Programador Backend (semi-senior)

- **Objetivo:** Construir la lógica del servidor: autenticación, ingesta [[XX-abreviaciones#EDF|EDF]], anonimización y exposición de la API.
- **Responsabilidades:**
  - Implementar el [[XX-abreviaciones#RBAC|RBAC]] y el cierre de sesión a los 30 minutos.
  - Garantizar la sanitización irreversible de datos personales (Ley 25.326).
  - Cumplir con el tiempo de ingesta ≤ 30 s para archivos < 50 MB.
- **Funciones:**
  - Desarrollar el parser EDF/EDF+ y la validación de cabecera.
  - Crear los endpoints de gestión, baja lógica, auditoría y descarga.
  - Servir las señales por fragmentos.
  - Configurar HTTPS/TLS 1.3 junto con DevOps.
- **Nivel de autoridad:** Decide la arquitectura interna del backend y el diseño de la API, coordinando con el DBA y el frontend.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Lenguaje y framework: FastAPI con Python, APIs [[XX-abreviaciones#REST|REST]], autenticación/sesiones, seguridad web, formato EDF, Git.
  - _Habilidades:_ Lógica, trabajo colaborativo.
  - _Experiencia:_ +2 años en backend; no excluyente: datos biomédicos o archivos binarios.

## 4. DBA (Administrador de Base de Datos)

- **Objetivo:** Asegurar un almacenamiento de datos íntegro, eficiente y seguro para el catálogo de señales y los usuarios.
- **Responsabilidades:**
  - Diseñar y mantener el modelo de datos.
  - Garantizar la integridad, el rendimiento y los respaldos.
  - Cargar el dataset semilla (≥ 30 registros EDF).
- **Funciones:**
  - Modelar las tablas de metadatos (tipo de señal, patología, grupo etario, equipamiento, notas).
  - Optimizar consultas e índices para 100 usuarios concurrentes.
  - Configurar copias de seguridad y permisos de acceso.
- **Nivel de autoridad:** Decide sobre el esquema, los índices y las políticas de respaldo. Los cambios de estructura se coordinan con el backend.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ [[XX-abreviaciones#SQL|SQL]], modelado relacional, motor de base de datos: PostgreSQL, backup/recuperación, seguridad de datos.
  - _Habilidades:_ Análisis, rigurosidad, comunicación con el backend.
  - _Experiencia:_ +3 años en administración o diseño de bases de datos.

## 5. DevOps

- **Objetivo:** Automatizar y garantizar el despliegue estable de la plataforma en los servidores de la [[XX-abreviaciones#UNViMe|UNViMe]].
- **Responsabilidades:**
  - Gestionar la infraestructura, el despliegue y la seguridad del entorno.
- **Funciones:**
  - Configurar el servidor, el subdominio `*.unvime.edu.ar` y TLS 1.3.
  - Armar pipelines de integración y despliegue continuo (CI/CD).
  - Monitorear el rendimiento y los logs.
- **Nivel de autoridad:** Decide sobre las herramientas y la configuración de infraestructura. Los cambios en producción requieren la aprobación del PM.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Linux, Docker, CI/CD, Git, redes, HTTPS/TLS, herramientas open source de monitoreo.
  - _Habilidades:_ Resolución de problemas, proactividad, comunicación interinstitucional.
  - _Experiencia:_ +1 año en despliegue y administración de servidores.

## 6. PM (Project Manager)

- **Objetivo:** Dirigir el proyecto para entregar BioSignal y calidad acordados.
- **Responsabilidades:**
  - Planificar, ejecutar, monitorear y cerrar el proyecto
  - Gestionar el alcance, los riesgos, las comunicaciones y los interesados.
- **Funciones:**
  - Elaborar el [[02-acta-de-constitucion|Acta de Constitución]], el cronograma y la gestión de riesgos.
  - Coordinar al equipo y remover impedimentos.
  - Gestionar los cambios y reportar el avance a los interesados.
  - Gestionar las actas de despliegue y cierre.
- **Nivel de autoridad:** Autoridad plena sobre la planificación, la asignación de tareas y la gestión del equipo. Escala al patrocinador/comité las decisiones de alcance, plazo o presupuesto.
- **Reporta a:** Patrocinador del proyecto (UNViMe).
- **Supervisa a:** APM, diseñador UX/UI, frontend, backend, DBA, DevOps y QA
- **Requisitos:**
  - _Conocimientos:_ PMBOK 7, metodologías ágiles e híbridas, gestión de riesgos, ciclo de vida del software.
  - _Habilidades:_ Liderazgo, comunicación, negociación, toma de decisiones.
  - _Experiencia:_ Gestión de proyectos de software de al menos 3 años.

## 7. APM (Ayudante del Project Manager)

- **Objetivo:** Apoyar al PM en la planificación, el seguimiento y la documentación del proyecto.
- **Responsabilidades:**
  - Mantener actualizada la documentación de gestión.
  - Dar seguimiento al avance y a los riesgos.
- **Funciones:**
  - Registrar las reuniones, los acuerdos y los cambios.
  - Actualizar el cronograma, la matriz de trazabilidad y el registro de riesgos.
  - Preparar los reportes de estado.
  - Coordinar la logística con el equipo y los interesados.
- **Nivel de autoridad:** Limitado. Ejecuta las tareas delegadas por el PM y no toma decisiones de alcance, plazo ni asignación de recursos.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Fundamentos de gestión de proyectos, herramientas de planificación, documentación.
  - _Habilidades:_ Organización, comunicación escrita, proactividad.
  - _Experiencia:_ No excluyente; se valora haber participado en proyectos académicos o de software.

## 8. QA (Testing)

- **Objetivo:** Verificar que el producto cumpla los criterios de aceptación, con cero defectos críticos o bloqueantes.
- **Responsabilidades:**
  - Diseñar y ejecutar el plan de pruebas.
  - Emitir el Reporte Consolidado de QA.
- **Funciones:**
  - Realizar pruebas funcionales, de integración y de regresión.
  - Realizar pruebas de carga (100 usuarios), latencia (≤ 2,5 s) y fluidez (≥ 30 [[XX-abreviaciones#FPS|FPS]]).
  - Realizar pruebas cross-browser y auditoría binaria de las cabeceras EDF.
  - Reportar los defectos y verificar sus correcciones.
- **Nivel de autoridad:** Puede aprobar o rechazar entregables según los criterios de calidad y recomendar al PM la liberación a producción.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Técnicas de testing, pruebas de carga, DevTools, automatización de pruebas.
  - _Habilidades:_ Atención al detalle, pensamiento analítico, comunicación clara de defectos.
  - _Experiencia:_ +1 año en testing de aplicaciones web.

## Plan de Mejora de Competencias

Las brechas se detectan con la matriz anterior y con las evaluaciones de desempeño ([[13-evaluaciones-de-desempeño|documento 13]]). Cada acción se identifica como **PM-01…PM-06**, tiene un indicador verificable, un costo estimado y un documento propio de resultados en [[evaluacion-de-planes/index|Evaluación de Planes de Mejora]].

| ID    | Brecha detectada                                                                       | Acción de mejora                                                                            | Tipo                   | Responsable   | Plazo      | Costo (USD caja / ARS interno) | Indicador de eficacia                                                                                 | Resultados                                                                  |
| :---- | :------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------ | :--------------------- | :------------ | :--------- | :----------------------------- | :---------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| PM-01 | Germán: demoras en respuestas y revisiones; dificultad para equilibrar desarrollo y QA | Tutoría de priorización y acuerdo interno de revisión en ≤ 48 h                             | Tutoría                | PM + Germán   | 31/12/2026 | $0 / ARS 40.000                | 100 % de [[XX-abreviaciones#PR\|PR]] revisadas en ≤ 48 h; próximo [[XX-abreviaciones#RDS\|RDS]] ≥ 4,0 | [[evaluacion-de-planes/resultado-plan-01-tutoria-priorizacion-german\|Ver]] |
| PM-02 | Rocío: autonomía limitada en decisiones de [[XX-abreviaciones#UI\|UI]]                 | Asignarle un módulo completo con mentoría de [[XX-abreviaciones#UX\|UX]] y revisión semanal | Tutoría / reasignación | PM + Rocío    | 31/01/2027 | $0 / ARS 120.000               | 0 bloqueos por consultas evitables; RDS de autonomía ≥ 4,0                                            | [[evaluacion-de-planes/resultado-plan-02-autonomia-ui-rocio\|Ver]]          |
| PM-03 | Eber: documentación previa insuficiente en cambios de esquema                          | Usar plantilla de migración y avisar cambios con 48 h de anticipación                       | Capacitación           | Eber + PM     | 31/12/2026 | $0 / ARS 30.000                | 100 % de migraciones con up/down y aviso previo registrado                                            | [[evaluacion-de-planes/resultado-plan-03-migraciones-esquema-eber\|Ver]]    |
| PM-04 | PM: informes de riesgos con poco detalle                                               | Incorporar plantilla mensual de riesgos y dependencias con estado y responsable             | Tutoría                | PM + APM      | 30/11/2026 | $0 / ARS 60.000                | 100 % de informes con riesgos, dependencias y dueño                                                   | [[evaluacion-de-planes/resultado-plan-04-informes-riesgos-pm\|Ver]]         |
| PM-05 | Equipo: cobertura irregular de pruebas de integración                                  | Taller corto de pytest/Testcontainers y revisión en PR                                      | Capacitación           | Germán + Eber | 31/01/2027 | $0 / ARS 120.000               | Cobertura > 80 % en lógica crítica y 0 fallas en [[XX-abreviaciones#CI\|CI]]                          | [[evaluacion-de-planes/resultado-plan-05-pruebas-integradas\|Ver]]          |
| PM-06 | Equipo: documentación desigual entre áreas                                             | Guía única de documentación y chequeo en la Definition of Done                              | Formación interna      | APM           | 31/12/2026 | $0 / ARS 60.000                | 100 % de PR con documentación actualizada                                                             | [[evaluacion-de-planes/resultado-plan-06-guia-documentacion\|Ver]]          |
| —     | **Total**                                                                              | —                                                                                           | —                      | —             | —          | **$0 / ARS 430.000**           | —                                                                                                     | —                                                                           |

> **Base de costos:** todas las acciones son internas y se ejecutan con herramientas open source o licencias educativas, por lo que la **caja en USD es $0**. El costo interno se valoriza a **ARS 10.000/h** como referencia no erogable (contexto del proyecto, §9.3). Total planificado: **43 h · ARS 430.000 · USD 0**. Los valores ejecutados y la variación están en cada documento de resultados.

### Evaluación de eficacia

Cada plan tiene un documento de resultados con línea base, acciones ejecutadas, evidencia, resultado frente al indicador, costo ejecutado y decisión. El dictamen se rige por esta regla:

- **Eficaz:** cumple el 100 % de los indicadores en el plazo.
- **Eficaz con desvío:** cumple con demora o costo mayor al planificado.
- **Parcial:** cumple parte de los indicadores; se ajusta y se reevalúa.
- **No eficaz:** no cumple; se rediseña la acción.

El tablero consolidado, los seis documentos y las lecciones están en [[evaluacion-de-planes/index|Evaluación de Planes de Mejora]]. Al cierre (15/02/2027) las seis brechas quedaron cerradas: cuatro eficaces, una eficaz tras ajuste y una eficaz con desvío de plazo.

## Registro de Cambios

| Versión | Fecha      | Cambio                                                                                                                                                                                          | Responsable | Estado    |
| :------ | :--------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- | :-------- |
| v1.0    | —          | Versión inicial: catálogo de roles, funciones, responsabilidades y competencias                                                                                                                 | PM          | Histórico |
| v1.1    | 29/10/2026 | Separación explícita entre el catálogo de competencias y la matriz RACI; aclaración de uso como anexo. Tramitado como **RFC-009**                                                               | APM         | Aprobado  |
| v1.2    | 11/11/2026 | Incorporación del **Plan de Mejora de Competencias** PM-01…PM-06 con costos, indicadores, criterios de eficacia y documentos de resultados. Tramitado como **RFC-014**, que ratifica el RFC-009 | APM + PM    | Aprobado  |
