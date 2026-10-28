---
title: 10. Gestión del Conocimiento
aliases:
  - Gestión del Conocimiento
project: Banco de Señales Biomédicas ("BioSignalsBank")
version: 1
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-10-22
---

# Plan de Gestión del Conocimiento

**Ámbito de Aplicación:** Marco universal corporativo para organizaciones de tecnología, equipos de desarrollo de software y gestión de proyectos  
**Objetivo Estratégico:** Guiar la captura, organización, retención, seguridad y reutilización del conocimiento explícito y tácito  
**Enfoque:** Docs-as-Code, Captura de Conocimiento Tácito, Error Logs, Gobernanza de Activos de IA y Control de Acceso (RBAC)

## 1. Marco Estratégico y Propósito

### 1.1. La Gestión del Conocimiento como Activo Competitivo

En la industria del software y la tecnología, cada proyecto genera un flujo constante de conocimiento: estimaciones de esfuerzo, decisiones de arquitectura, configuraciones de infraestructura, algoritmos de negocio, parches de seguridad y resolución de errores. Cuando este conocimiento se gestiona de forma sistemática desde el Día 0, se convierte en un activo de capital intelectual que permite:

- **Acelerar el tiempo de salida al mercado (_Time-to-Market_):** Reutilizando módulos, librerías, _prompts_ y patrones de arquitectura probados.
- **Precisión en la Estimación:** Utilizar datos históricos de proyectos previos para proyectar costos, plazos y requerimientos de recursos con menor margen de error.
- **Reducción de la Dependencia Personal (_Attrition Risk_):** Mitigar el impacto de la rotación de personal evitando que el saber técnico resida de forma exclusiva en la mente de individuos aislados.

### 1.2. La Información Desordenada (_Information Noise_)

Un error recurrente en las empresas tecnológicas es confundir "almacenar información" con "gestionar conocimiento". Acumular carpetas desestructuradas en la nube, canales de chat dispersos o espacios de wikis corporativas sin mantenimiento genera un fenómeno de **ruido de información**:

- **Información Duplicada y Contradictoria:** Coexistencia de múltiples versiones de un mismo procedimiento sin indicación de cuál es la vigente.
- **Obsolescencia no Detectada:** Guías de instalación de entornos (_setup_) que hacen referencia a versiones en desuso, provocando que los nuevos desarrolladores pierdan días intentando configurar su ambiente local.
- **Abandono de la Documentación:** Al volverse la búsqueda ineficiente y caótica, los equipos dejan de consultar y actualizar la documentación, recurriendo nuevamente a la interrupción informal o al re-trabajo.

### 1.3. Principios Rectores de la Estrategia

Para superar la desorganización, esta guía establece tres principios universales:

1. **Catalogar desde el Origen (_Knowledge-by-Design_):** El conocimiento no se documenta "al final del proyecto", sino que se captura como un subproducto natural del flujo de trabajo diario.
2. **Estructura en Bloques Escalables:** La información se organiza en macro-categorías lógicas e independientes del tamaño del proyecto o la cantidad de clientes.
3. **Mantenimiento Automatizado:** Se priorizan herramientas y mecanismos que validen y actualicen la documentación mediante automatizaciones y modelos de asistencia.

---

## 2. Estrategia de Gestión del Conocimiento Explícito

El **conocimiento explícito** es aquel que se encuentra codificado, estructurado y formalizado en soportes tangibles (archivos, repositorios, diagramas y especificaciones). Su gestión requiere una taxonomía clara y un enfoque de mantenimiento continuo.

### 2.1. Taxonomía Organizacional: Bloques de Conocimiento

Para garantizar que la información sea fácilmente localizable, la organización debe estructurar sus repositorios bajo una **macro-taxonomía modular en bloques**:

```
[Wiki Corporativa]  (conocimiento transversal, válido para todos los proyectos)
├── 00-indice-y-gobernanza/        (cómo se usa la wiki, dueños, ciclo de revisión)
├── 01-arquitectura-y-estandares/  (guías de estilo, patrones, esquemas globales, ADR corporativos)
├── 02-procesos-y-metodologia/     (control de cambios, flujo de ramas, roles, definición de "terminado")
├── 03-librerias-y-reutilizables/  (componentes UI, módulos backend, scripts)
├── 04-plantillas/                 (plantilla de repo, de ADR, de incidencia, de README)
├── 05-seguridad-y-cumplimiento/   (gestión de secretos, accesos, políticas)
├── 06-onboarding-y-glosario/      (guía de ingreso, términos, FAQ)
└── 07-activos-de-ia/
    ├── skills/
    ├── agentes/
    └── prompts/                   (cada uno con versión y dueño)

[Repositorio proyecto-a]  (proyecto-b usa EXACTAMENTE la misma estructura, creada desde la plantilla)
├── README.md                      (qué es, cómo levantarlo en 5 minutos, enlaces a /docs)
├── AGENTS.md                      (contexto del proyecto para asistentes de IA)
└── docs/
    ├── 00-indice.md
    ├── 01-especificaciones/       (requerimientos, alcance, historias de usuario)
    ├── 02-arquitectura/
    │   ├── c4/                    (diagramas como código: Mermaid/Structurizr)
    │   ├── base-de-datos/         (esquemas DDL, diagrama ER)
    │   └── adr/                   (0001-titulo.md, 0002-titulo.md…)
    ├── 03-despliegue-y-setup/     (ambientes, variables, CI/CD)
    ├── 04-calidad-y-pruebas/      (plan de pruebas, criterios de aceptación)
    └── 05-operacion-y-mantenimiento/
        ├── runbooks/              (cómo resolver problemas conocidos)
        ├── incidencias/           (postmortems, uno por archivo)
        └── bitacora-de-cambios.md
```

### 2.2. Filosofía _Docs-as-Code_ (Documentación junto al Código)

Para evitar la separación entre la documentación y la realidad del sistema, se adopta la práctica de **Docs-as-Code**:

- **Formatos Livianos:** Toda la documentación técnica se redacta en archivos Markdown (`.md`) almacenados dentro del mismo repositorio de código fuente en una carpeta `/docs/`.
- **Especificaciones Auto-generadas:** Las interfaces de programación (APIs REST) deben utilizar marcos que generen la especificación técnica de manera automática a partir del código (por ejemplo, OpenAPI / Swagger).
- **Actualización en el Flujo de Trabajo:** Ninguna historia de usuario o _Pull Request_ (PR) se considera completada (_Definition of Done_) si el cambio de código introducido no incluye la actualización correspondiente en su archivo `.md`.

### 2.3. Protocolo de Mantenimiento de Guías de _Onboarding_ y Entornos

Uno de los puntos más vulnerables en la gestión explícita es la degradación de las guías de configuración inicial (_setup_). Para garantizar que las guías de ambiente se mantengan vivas, se establece el siguiente protocolo:

1. **Instructivo Unificado (`SETUP.md`):** Cada proyecto debe incluir un único archivo `SETUP.md` en la raíz del repositorio con los pasos exactos para levantar el entorno local de desarrollo.
2. **Verificación por el Nuevo Integrante:** Cada vez que una persona se suma al equipo, su primera tarea obligatoria es seguir el `SETUP.md` al pie de la letra sin asistencia verbal. Si detecta un paso fallido o desactualizado, **es su responsabilidad corregir el documento y enviar la actualización**.
3. **Automatización con Contenedores:** Se debe reducir la fricción en la instalación mediante el uso de infraestructura como código (Docker / Docker-Compose), permitiendo que el entorno se ejecute con un único comando estandarizado.

---

## 3. Estrategia de Gestión del Conocimiento Tácito

El **conocimiento tácito** es aquel que reside en la mente de los profesionales: la experiencia práctica, la intuición técnica, las lecciones aprendidas ante situaciones complejas y el "saber hacer" (_know-how_). Al ser difícil de codificar directamente, la empresa debe implementar rutinas para transformarlo en conocimiento explícito o transferirlo entre personas.

### 3.1. Adaptación del Modelo SECI en Software

|Fase del Modelo SECI|Acción en el Equipo de Desarrollo|Resultado Obtenido|
|---|---|---|
|**Socialización** _(De Tácito a Tácito)_|Programación en Pareja (_Pair Programming_) y sesiones de trabajo colaborativo ante incidentes críticos.|Transferencia directa de lógica de resolución de problemas entre desarrolladores Senior y Junior.|
|**Exteriorización** _(De Tácito a Explícito)_|Redacción de Registros de Decisiones de Arquitectura (_ADR — Architecture Decision Records_) y artículos técnicos tras resolver un reto.|Conversión de la intuición técnica en un documento `.md` consultable.|
|**Combinación** _(De Explícito a Explícito)_|Consolidación de documentos individuales en guías generales, manuales de buenas prácticas o librerías de _prompts_.|Creación de un marco estándar corporativo reutilizable.|
|**Interiorización** _(De Explícito a Tácito)_|Lectura de guías, ejecución de ejercicios prácticos (_Spikes_) y estudio de decisiones de arquitectura previas.|Absorción del conocimiento por parte de nuevos integrantes, convirtiéndolo en nueva experiencia personal.|

### 3.2. Mecanismos Operativos para Retener el Conocimiento Humano

1. **Revisiones de Código Cruzadas (_Peer Code Reviews_):** Exigir que todo cambio de código sea revisado y aprobado mediante un _Pull Request_ por un compañero de equipo. Esto garantiza la difusión del conocimiento sobre la arquitectura y evita que solo una persona entienda un módulo particular.
2. **Sesiones de Transferencia Técnica (_Tech Talks_ / _Brown Bag Sessions_):** Espacios periódicos de 30 minutos donde un integrante expone cómo resolvió un desafío complejo, qué tecnologías evaluó y qué aprendizajes obtuvo.
3. **Retrospectivas de Sprint y Post-Mortems de Incidentes:** Al finalizar un hito o tras la ocurrencia de una falla grave en producción, el equipo realiza una sesión de _Post-Mortem_ sin buscar culpables (_blameless_), enfocándose en identificar las causas raíz y documentar la lección aprendida.
4. **Protocolo Obligatorio de Traspaso (_Offboarding / Handover_):** Cuando un integrante desvincula su participación de un proyecto o de la empresa, se activa un plan de transferencia de 5 días hábiles que incluye:
    - Mapeo de módulos bajo su responsabilidad exclusiva.
    - Actualización y cierre de documentación pendiente en el repositorio.

---

## 4. Sistema de Lecciones Aprendidas y Registro de Errores (_Error Log_)

Uno de los mayores desperdicios de productividad en ingeniería de software es la repetición de investigaciones sobre errores ya resueltos en el pasado por otros compañeros o equipos.

### 4.1. El Registro de Errores y Soluciones (_Troubleshooting & Error Log_)

La organización debe mantener un **Registro Centralizado de Errores** estructurado por categorías de fallas recurrentes:

- **Categorías Principales:**
    - `INFRA`: Fallas de contenedores, red, permisos o variables de entorno.
    - `DB`: Excepciones de migraciones SQL, bloqueos de tablas o rendimiento de consultas.
    - `API`: Errores de integración con servicios externos, autenticación o tokens expirados.
    - `BUILD`: Errores de compilación, empaquetado o incompatibilidad de dependencias.
    - `LOGIC`: Errores en algoritmos de negocio o manipulación de datos.

### 4.2. Plantilla Estándar para el Registro de un Error

Cada entrada en el catálogo de errores debe asentarse mediante el siguiente formato claro y estructurado:

```markdown
### [ERR-042] Excepción de Caducidad de Token JWT en Peticiones Concurrenciales
* **Fecha de Registro:** 22/10/2026
* **Categoría:** API / Autenticación
* **Entorno / Stack:** Node.js v20 / PostgreSQL / Middleware Auth
* **Síntoma / Mensaje de Error:** 
  `JsonWebTokenError: jwt expired` en peticiones paralelas tras 15 minutos de inactividad.
* **Causa Raíz Identificada:** 
  El middleware de autenticación no refrescaba el token antes de verificar peticiones asincrónicas simultáneas en el frontend.
* **Solución Aplicada:** 
  Implementación de un interceptor Axios en el cliente para manejar la cola de refresco (*Token Refresh Queue*) mediante promesas.
* **Acción Preventiva / Lección Aprendida:** 
  Se actualizó el archivo `AUTH_GUIDE.md` y se agregó una prueba unitaria que simula peticiones concurrentes con tokens a punto de expirar.
```

---

## 5. La Inteligencia Artificial como Nuevo Activo de Conocimiento

Las herramientas de asistencia basadas en Inteligencia Artificial Generativa y modelos de lenguaje han transformado la naturaleza del conocimiento en las empresas. Los _prompts_, instrucciones del sistema y configuraciones de agentes no son simples textos temporales, sino **propiedad intelectual y nuevo conocimiento corporativo**.

### 5.1. Gobernanza de Activos de IA (_Prompts_, _Skills_ y Agentes)

Los componentes de IA deben administrarse con el mismo rigor metodológico que el código fuente tradicional:

1. **Estructura Estándar de Archivos:** Cada activo de IA debe residir en el repositorio dentro de una estructura estandarizada:
    
    ```
    /ai-assets/
     ├── skills/
     │    └── <nombre-skill>/
     │         ├── SKILL.md            (Instrucciones de comportamiento del skill)
     │         └── metadata.json       (Nombre, versión, descripción y parámetros)
     ├── prompts/
     │    └── <categoria>/
     │         └── <nombre-prompt>.md  (Prompt depurado y probado)
     └── validation-scripts/           (Scripts automáticos para validar la estructura)
    ```
    
2. **Validación Automatizada por Scripts:** Se deben implementar scripts de validación que se ejecuten en el pipeline de integración continua para verificar que todo nuevo _skill_ o _prompt_ cumpla con:
    - Convención de nombres (_kebab-case_).
    - Presencia obligatoria de encabezados con descripción y ámbito de uso.
    - Ausencia de credenciales, claves privadas o datos confidenciales harcodeados.

### 5.2. Arquitecturas RAG (_Retrieval-Augmented Generation_) e Indización de Repositorios

Para explotar el historial de conocimiento de la empresa sin riesgo de alucinaciones ni fugas de información, se establecen las siguientes capacidades tecnológicas:

- **Bases de Datos Vectoriales con Contexto Local (RAG):** Implementar agentes de IA que consulten exclusivamente la base de conocimiento local estructurada (documentos `.md`, tickets de proyectos y código), respondiendo consultas precisas sobre decisiones técnicas pasadas.
- **Escaneo de Repositorios Históricos (_Enterprise Code Search_):** Utilizar herramientas de indexación que permitan a los desarrolladores buscar cómo se resolvió un desafío técnico en cualquier proyecto previo de la empresa antes de iniciar el desarrollo desde cero.

---

## 6. Clasificación de Seguridad, Confidencialidad y Control de Acceso (RBAC)

Toda estrategia de gestión del conocimiento debe proteger la propiedad intelectual y la privacidad de la información corporativa mediante controles de acceso estrictos.

### 6.1. Etiquetas de Sensibilidad de la Información

Toda documentación o activo de conocimiento debe clasificarse bajo uno de los cuatro niveles de sensibilidad:

1. **Público (Nivel 0):** Información destinada a difusión externa (documentación pública de APIs, artículos de blog técnicos).
2. **Interno (Nivel 1):** Acceso permitido a todos los empleados de la organización (guías de estilo, manuales generales, procesos de RRHH).
3. **Confidencial (Nivel 2):** Restringido exclusivamente al equipo asignado al proyecto (código fuente del cliente, diagramas de arquitectura interna, credenciales de entornos de pruebas).
4. **Restringido (Nivel 3):** Acceso altamente limitado a la alta dirección (datos financieros del proyecto, contratos, claves privadas de producción, datos personales de usuarios).

### 6.2. Control de Acceso Basado en Roles (RBAC) para Empleados e IA

- **Herramientas de IA y Permisos:** Los agentes de IA y sistemas RAG deben heredar los mismos permisos de acceso que el usuario que realiza la consulta. Bajo ninguna circunstancia un sistema de IA debe revelar información de Nivel 3 (Restringido) a un usuario que no posea las credenciales autorizadas.
- **Auditoría de Consultas:** Se deben mantener registros auditables de los accesos a la base de conocimiento corporativa para prevenir filtraciones no autorizadas.

---

## 7. Hoja de Ruta Operativa: Matriz de Implementación para un Nuevo Proyecto

Al iniciar cualquier nuevo proyecto de software dentro de la organización, el líder de proyecto y el equipo técnico deben ejecutar la siguiente **Matriz de Verificación de Gestión del Conocimiento** desde la fase de inicio hasta el cierre:

| Fase del Proyecto        | Acción Obligatoria de Gestión del Conocimiento                                                   | Entregable / Evidencia                                                     | Responsable               |
| ------------------------ | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- | ------------------------- |
| **Inicio (Día 0)**       | Crear la estructura de carpetas en el repositorio e instanciar la plantilla `SETUP.md`.          | Repositorio Git inicializado con carpeta `/docs/` y `SETUP.md`.            | Líder Técnico / PM        |
| **Planificación**        | Registrar la arquitectura inicial y publicar la especificación de API base.                      | Archivo `ARCHITECTURE.md`.                                                 | Arquitecto / Dev Backend  |
| **Desarrollo (Sprints)** | Validar que cada PR incluya actualización de docs y registrar errores complejos en el Error Log. | Pull Requests aprobadas con cambios en `.md` y entradas en `ERROR_LOG.md`. | Equipo de Desarrollo / QA |
| **Pruebas y QA**         | Realizar sesión de transferencia técnica (_Tech Talk_) para el equipo de soporte u operaciones.  | Sesión de demo grabada y publicada en la wiki interna.                     | Dev Senior / QA           |
| **Cierre / Despliegue**  | Realizar la sesión de Retrospectiva/Post-Mortem y registrar las lecciones aprendidas finales.    | Documento `LESSONS_LEARNED.md` archivado en el bloque del proyecto.        | PM / Todo el equipo       |
