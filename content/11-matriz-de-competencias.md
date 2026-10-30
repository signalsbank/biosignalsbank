---
project: BioSignal
version: 1.1
title: 11. Matriz de Competencias
aliases: Matriz de Competencias
---

> **Nota de uso:** este documento es un **catálogo (anexo) de perfiles, funciones y competencias**; **no constituye una matriz RACI** y no puede sustituirla. La asignación de responsabilidad por entregable/paquete (quién ejecuta **R**, aprueba **A**, es consultado **C** e informado **I**) se gestiona en la matriz RACI del plan integrador, con los 8 roles mapeados a las 6 personas del equipo y QA independiente del autor del código.

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
  - _Conocimientos:_ HTML5, CSS, JavaScript/TypeScript, framework: nextjs, Canvas/WebGL, Git.
  - _Habilidades:_ Optimización de rendimiento, resolución de problemas, trabajo colaborativo.
  - _Experiencia:_ +2 años en desarrollo frontend, no excluyente: con gráficos o datos en tiempo real.

## 3. Programador Backend (semi-senior)

- **Objetivo:** Construir la lógica del servidor: autenticación, ingesta EDF, anonimización y exposición de la API.
- **Responsabilidades:**
  - Implementar el RBAC y el cierre de sesión a los 30 minutos.
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
  - _Conocimientos:_ Lenguaje y framework: FastApi con python, APIs REST, autenticación/sesiones, seguridad web, formato EDF, Git.
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
  - _Conocimientos:_ SQL, modelado relacional, motor de base de datos: PostgreSQL, backup/recuperación, seguridad de datos.
  - _Habilidades:_ Análisis, rigurosidad, comunicación con el backend.
  - _Experiencia:_ +3 años en administración o diseño de bases de datos.

## 5. DevOps

- **Objetivo:** Automatizar y garantizar el despliegue estable de la plataforma en los servidores de la UNViMe.
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
  - _Experiencia:_ +1 años en despliegue y administración de servidores.

## 6. PM (Project Manager)

- **Objetivo:** Dirigir el proyecto para entregar BioSignal y calidad acordados.
- **Responsabilidades:**
  - Planificar, ejecutar, monitorear y cerrar el proyecto
  - Gestionar el alcance, los riesgos, las comunicaciones y los interesados.
- **Funciones:**
  - Elaborar el Acta de Constitución, el cronograma y la gestión de riesgos.
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
  - Realizar pruebas de carga (100 usuarios), latencia (≤ 2,5 s) y fluidez (≥ 30 FPS).
  - Realizar pruebas cross-browser y auditoría binaria de las cabeceras EDF.
  - Reportar los defectos y verificar sus correcciones.
- **Nivel de autoridad:** Puede aprobar o rechazar entregables según los criterios de calidad y recomendar al PM la liberación a producción.
- **Reporta a:** PM
- **Supervisa a:** Nadie
- **Requisitos:**
  - _Conocimientos:_ Técnicas de testing, pruebas de carga, DevTools, automatización de pruebas.
  - _Habilidades:_ Atención al detalle, pensamiento analítico, comunicación clara de defectos.
  - _Experiencia:_ +1 años en testing de aplicaciones web.
