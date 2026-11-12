---
title: 10. Gestión del Conocimiento
aliases:
  - "Gestión del Conocimiento"
  - "Gestión de Conocimiento"
  - "Conocimiento"
project: BioSignal
version: 2.0
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-11-09
---

# Gestión del Conocimiento Organizacional

**Estrategia elegida:** **Wiki organizacional + Docs-as-Code**.
**Alcance:** todos los proyectos de la organización; BioSignal se usa como caso de aplicación.
**Principio:** el conocimiento se captura mientras se trabaja, no al final del proyecto.

## 1. La estrategia

La organización mantiene una **wiki central** con estándares, plantillas y activos reutilizables. Cada proyecto tiene su propia documentación en el repositorio, escrita en Markdown y versionada con Git. Las dos capas se conectan mediante enlaces, etiquetas e identificadores estables.

No se crea una wiki nueva por proyecto ni se duplica el estándar en cada carpeta. La wiki central es la referencia común; el repositorio del proyecto es la fuente de verdad de ese proyecto.

```text
Wiki organizacional (conocimiento transversal)
        │  estándares, plantillas, componentes, lecciones
        ▼
Proyecto A ── docs/ + README + SETUP + ADR + ERROR_LOG
Proyecto B ── docs/ + README + SETUP + ADR + ERROR_LOG
Proyecto C ── docs/ + README + SETUP + ADR + ERROR_LOG
```

**Qué incluye la estrategia:**

- **Documentación como código:** Markdown, Git, revisión por [[XX-abreviaciones#PR|PR]] y publicación con Quartz o un generador equivalente.
- **Wiki central:** políticas, procesos, plantillas, glosario y activos reutilizables.
- **Documentación por proyecto:** requisitos, arquitectura, decisiones, pruebas, operación y lecciones.
- **Captura de conocimiento tácito:** [[XX-abreviaciones#ADR|ADR]], post-mortems, revisiones de código y sesiones breves de transferencia.
- **Búsqueda y recuperación:** índice, etiquetas, identificadores y buscador del sitio.

## 2. Objetivo

Resolver cuatro necesidades concretas:

1. Evitar que cada proyecto investigue de nuevo problemas ya resueltos.
2. Conservar las decisiones y sus motivos, no solo el resultado.
3. Reducir el tiempo de incorporación de un integrante nuevo.
4. Mantener un estándar común para varios proyectos sin perder la autonomía de cada equipo.

## 3. Información a gestionar

| Nivel              | Contenido                                                                                                                 | Ejemplo                                                                                                      |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------ | :----------------------------------------------------------------------------------------------------------- |
| **Organizacional** | Políticas, estándares, procesos, plantillas, glosario, componentes reutilizables y activos de [[XX-abreviaciones#IA\|IA]] | Guía de estilo, plantilla de ADR, checklist de PR                                                            |
| **Proyecto**       | Requisitos, alcance, arquitectura, decisiones, pruebas, operación, riesgos y estado                                       | [[03-especificacion-de-requisitos\|ERS]] de BioSignal, diagrama [[XX-abreviaciones#C4\|C4]], plan de pruebas |
| **Operación**      | Runbooks, incidencias, errores conocidos, backups y monitoreo                                                             | Procedimiento de restore, error [[XX-abreviaciones#JWT\|JWT]]                                                |
| **Aprendizaje**    | Lecciones aprendidas, post-mortems y recomendaciones                                                                      | Qué falló en una migración y cómo evitarlo                                                                   |

**Regla de clasificación:** si sirve para más de un proyecto, va a la wiki central; si es específico, va al repositorio del proyecto. Si es reusable, se enlaza desde la wiki.

## 4. Herramientas y métodos

| Necesidad                   | Herramienta / método                                                             |
| :-------------------------- | :------------------------------------------------------------------------------- |
| Redacción y versionado      | Markdown + Git/GitHub                                                            |
| Publicación y búsqueda      | Quartz (u otro generador estático) con índice y etiquetas                        |
| Gestión de tareas y cambios | GitHub Issues/Projects; [[XX-abreviaciones#RFC\|RFC]] para cambios de línea base |
| Decisiones                  | ADR con contexto, decisión, alternativas y consecuencias                         |
| Errores recurrentes         | Registro `ERROR_LOG` con síntoma, causa, solución y prevención                   |
| Lecciones                   | Post-mortem sin culpables y registro de lecciones por hito                       |
| Conocimiento tácito         | Pair programming, revisión de PR y transferencias breves                         |
| Activos de IA               | Prompts y agentes versionados, con dueño y ámbito de uso                         |

**Docs-as-Code:** toda documentación técnica vive en el repositorio del proyecto, en Markdown. Una historia o PR no se considera terminada si el cambio de código no actualiza la documentación correspondiente. Las [[XX-abreviaciones#API|APIs]] se documentan con OpenAPI/Swagger generado desde el código.

**Apoyo de IA:** un asistente puede indexar la wiki y responder preguntas, pero **no es la estrategia**: es una interfaz de consulta sobre la misma base de conocimiento. Sus respuestas deben citar el documento fuente y respetar los permisos del usuario.

## 5. Organización y catalogación

### 5.1. Estructura de la wiki central

```text
knowledge-base/
├── 00-gobierno/          (dueños, ciclo de revisión, índices)
├── 01-estandares/        (estilo, arquitectura, seguridad)
├── 02-procesos/          (SCM, cambios, calidad, adquisiciones)
├── 03-reutilizables/     (componentes, scripts, plantillas de código)
├── 04-plantillas/        (ADR, RFC, post-mortem, README, SETUP)
├── 05-seguridad/         (secretos, accesos, privacidad)
├── 06-onboarding/        (guía de ingreso, glosario, FAQ)
└── 07-activos-ia/        (prompts, agentes, skills)
```

### 5.2. Estructura de cada proyecto

```text
proyecto/
├── README.md             (qué es y cómo se usa)
├── SETUP.md              (entorno local en pocos pasos)
├── AGENTS.md             (contexto para asistentes de IA)
└── docs/
    ├── 00-indice.md
    ├── 01-requisitos/
    ├── 02-arquitectura/
    │   ├── c4/
    │   ├── base-de-datos/
    │   └── adr/
    ├── 03-despliegue/
    ├── 04-calidad/
    └── 05-operacion/
        ├── runbooks/
        ├── incidencias/
        └── lecciones.md
```

En BioSignal, la documentación de gestión se publica desde `content/` con Quartz; el código y su documentación técnica van en los repositorios `biosignal-backend` y `biosignal-frontend`.

### 5.3. Identificadores

| Tipo              | Formato         | Ejemplo      |
| :---------------- | :-------------- | :----------- |
| Documento de wiki | `KB-<área>-<n>` | `KB-SEC-03`  |
| Decisión          | `ADR-<n>`       | `ADR-001`    |
| Error             | `ERR-<n>`       | `ERR-042`    |
| Lección           | `LESSON-<n>`    | `LESSON-007` |
| Runbook           | `RUN-<n>`       | `RUN-002`    |
| Plantilla         | `TPL-<n>`       | `TPL-ADR`    |

Cada documento incluye título, dueño, versión, fecha, estado y etiquetas. Los enlaces entre documentos usan el identificador, no solo el título, para evitar duplicados y referencias ambiguas.

## 6. Acceso y consulta

| Nivel            | Quién accede                                       | Contenido                                                       |
| :--------------- | :------------------------------------------------- | :-------------------------------------------------------------- |
| **Público**      | Cualquier persona                                  | Documentación publicada del producto y material de difusión     |
| **Interno**      | Toda la organización                               | Estándares, plantillas, glosario y guías generales              |
| **Confidencial** | Equipo del proyecto                                | Código, arquitectura interna, pruebas y credenciales de staging |
| **Restringido**  | [[XX-abreviaciones#PM\|PM]], seguridad y dirección | Contratos, claves de producción, datos personales y auditorías  |

**Cómo se encuentra la información:**

1. Buscar por identificador (`ADR-001`, `ERR-042`) o por etiqueta (`#seguridad`, `#postgresql`).
2. Usar el índice del proyecto y el índice central de la wiki.
3. Consultar el glosario si el término es nuevo.
4. Si no se encuentra, registrar la pregunta en el FAQ o abrir un issue de documentación.

**Regla de privacidad:** no se almacenan datos personales reales ni credenciales en la wiki. Los [[XX-abreviaciones#EDF|EDF]] de ejemplo son sintéticos o anonimizados.

## 7. Responsables

| Rol                                       | Quién                                                                            | Responsabilidad                                                                   |
| :---------------------------------------- | :------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------- |
| **Dueño del conocimiento organizacional** | [[XX-abreviaciones#PMO\|PMO]] / [[XX-abreviaciones#APM\|APM]] de la organización | Mantener la wiki central, el glosario, las plantillas y el índice.                |
| **Dueño del conocimiento del proyecto**   | APM del proyecto (en BioSignal, Ignacio Ávila)                                   | Mantener el índice, la estructura y la vigencia de la documentación del proyecto. |
| **Autores**                               | Cada integrante                                                                  | Documentar lo que produce y actualizar el documento afectado en el mismo PR.      |
| **Revisores**                             | PM, líder técnico o Process Owner                                                | Verificar claridad, vigencia y trazabilidad antes de publicar.                    |
| **[[XX-abreviaciones#QA\|QA]]**           | QA del proyecto                                                                  | Verificar que la documentación forme parte de la Definition of Done.              |
| **Sponsor / dirección**                   | [[XX-abreviaciones#UNViMe\|UNViMe]] en BioSignal                                 | Acceder a los documentos de gobierno y aprobar los que correspondan.              |

## 8. Actualización

| Momento                     | Qué se actualiza                                                                          |
| :-------------------------- | :---------------------------------------------------------------------------------------- |
| **Inicio de un proyecto**   | Se copia la plantilla, se crea `README`, `SETUP`, `AGENTS.md` y el índice.                |
| **Cada PR**                 | Documento afectado, API, decisión o runbook; se verifica en la revisión.                  |
| **Cada decisión relevante** | ADR con contexto, alternativas, decisión y consecuencias.                                 |
| **Cada incidente**          | Entrada en `ERROR_LOG` y, si es grave, post-mortem.                                       |
| **Cada hito**               | Lecciones aprendidas y actualización del índice.                                          |
| **Cierre del proyecto**     | Se archiva la documentación, se extraen activos reutilizables y se enlazan desde la wiki. |
| **Revisión mensual**        | Enlaces rotos, documentos obsoletos y contenidos sin dueño.                               |

**Versionado:** `v0.x` para borrador, `v1.0` para aprobado y `v1.x` para correcciones menores. La versión vigente es la publicada; las anteriores se conservan en Git para auditoría.

## 9. Ejemplo concreto de aplicación

**Situación:** un integrante del equipo de BioSignal necesita entender por qué el backend usa FastAPI y cómo resolver un error de token JWT.

1. Busca en el índice del proyecto y encuentra `ADR-001` (“FastAPI como framework backend”).
2. Lee el contexto, las alternativas evaluadas y la decisión; no necesita preguntar al autor.
3. Busca `ERR-042` en el registro de errores y encuentra el síntoma, la causa y la solución.
4. Si el error no está registrado, abre una entrada nueva con el formato establecido y la enlaza desde el runbook correspondiente.
5. El APM revisa la entrada en la reunión semanal y la marca como vigente.

**Situación multi-proyecto:** un equipo que inicia un proyecto nuevo necesita autenticación. En la wiki central encuentra `KB-SEC-03` con el componente reutilizable, la plantilla de ADR y las lecciones de BioSignal. Reutiliza el diseño, adapta lo necesario y devuelve a la wiki las mejoras. No empieza desde cero.

## 10. Beneficios y dificultades

**Beneficios esperados:**

- Menos tiempo buscando información y menos interrupciones al equipo.
- Incorporación más rápida de nuevos integrantes.
- Decisiones trazables y reutilización entre proyectos.
- Menos dependencia de una sola persona.
- Base común para auditorías y para la mejora continua.

**Dificultades posibles:**

- Documentación desactualizada o duplicada.
- Falta de disciplina para actualizar en el mismo PR.
- Exceso de documentación para tareas simples.
- Fragmentación entre wiki, repositorios y chats.
- Permisos mal configurados o exposición de información sensible.

**Mitigaciones:**

- Dueño claro por documento y revisión mensual.
- Documentación como parte de la Definition of Done.
- Plantillas breves y una taxonomía simple.
- Enlaces y buscador en lugar de copiar contenido.
- Clasificación por sensibilidad y revisión de accesos.

## 11. Indicadores de la estrategia

| Indicador                                      | Meta                             |
| :--------------------------------------------- | :------------------------------- |
| PR con documentación actualizada               | ≥ 90 %                           |
| Documentos con dueño y versión vigente         | 100 %                            |
| Enlaces rotos detectados en revisión mensual   | 0                                |
| Tiempo de incorporación de un integrante nuevo | ≤ 1 día para levantar el entorno |
| Activos reutilizados por otros proyectos       | ≥ 1 por proyecto y por fase      |

## 12. Implementación en varios proyectos

| Fase                   | Acción                                                                    | Evidencia                                             |
| :--------------------- | :------------------------------------------------------------------------ | :---------------------------------------------------- |
| **Preparación**        | Crear la wiki central, el glosario y las plantillas.                      | Repositorio `knowledge-base` con índice y plantillas. |
| **Inicio de proyecto** | Copiar la plantilla y completar `README`, `SETUP`, `AGENTS.md` y `docs/`. | Repositorio del proyecto inicializado.                |
| **Ejecución**          | Actualizar documentos en cada PR, registrar ADR y errores.                | PR con cambios en `.md` y `ERROR_LOG`.                |
| **Cierre de fase**     | Revisar lecciones, enlaces y documentos obsoletos.                        | Informe de revisión y lecciones aprendidas.           |
| **Cierre de proyecto** | Archivar, extraer activos reutilizables y actualizar la wiki.             | Proyecto archivado y activos enlazados.               |

La estrategia es acumulativa: cada proyecto deja a la organización un estándar, una plantilla o una lección reutilizable. La wiki central no reemplaza la documentación de cada proyecto; la conecta y evita que el conocimiento quede aislado.

## 13. Registro de Cambios

| Versión | Fecha      | Cambio                                                                                                                                                                                                                                                  | Responsable | Estado    |
| :------ | :--------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---------- | :-------- |
| v1.0    | —          | Versión inicial: estrategia de gestión del conocimiento y estructura de la wiki                                                                                                                                                                         | PM          | Histórico |
| v2.0    | 09/11/2026 | Reescritura con la estrategia **wiki organizacional + Docs-as-Code**: niveles de información, herramientas, catalogación, identificadores, accesos, actualización, indicadores y aplicación multi-proyecto. Tramitado como **RFC-011** en el Change Log | APM + PM    | Aprobado  |
