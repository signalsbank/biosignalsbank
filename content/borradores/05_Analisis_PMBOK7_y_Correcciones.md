---
project: BioSignal
version: 0.1
title: 5. Análisis de Alineación con PMBOK 7 y Plan de Correcciones
aliases:
  - Análisis PMBOK 7
  - Plan de Correcciones PMBOK 7
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-10-20
status: borrador
---

# Análisis de alineación con PMBOK 7 y plan de correcciones

> **Documento de trabajo.** Este análisis no modifica los artefactos publicados. Cada corrección debe aprobarse mediante el flujo del Plan de Gestión de la Configuración y Control de Cambios y registrarse como RFC. Se propone publicar la versión corregida como `v1.0` una vez aprobada por el PM y el patrocinador. El documento permanece en `borradores/` y no se agrega al índice hasta su aprobación.

| Campo | Valor |
| :--- | :--- |
| Proyecto | **BioSignal** — Banco de Señales Biomédicas (UNViMe) |
| Documento | APC-BIOSIG-05 |
| Versión | v0.1 (borrador para revisión) |
| Fecha | 20/10/2026 |
| Marco de referencia | **PMBOK 7.ª edición (PMI, 2021)**: 12 principios, 8 dominios de desempeño, tailoring y modelos/métodos/artefactos (MMAs) |
| Alcance revisado | `content/`: 11 artefactos publicados + `index.md`, y los borradores de calidad, adquisiciones, competencias y control de código |
| Elaborado por | Equipo PM/QA |
| Aprobación pendiente | Mateo T. Astudillo (Director del Proyecto) y Alejandro Rosas (Patrocinador EICA) |
| Resultado | **42 hallazgos**: 14 críticos, 24 altos y 4 medios |

---

## 1. Resumen ejecutivo

Los documentos de BioSignal tienen un **nivel técnico alto**: el alcance está bien delimitado, los requisitos no funcionales son medibles, la matriz de trazabilidad existe, el diccionario del EDT incorpora riesgos y costos, y el control de cambios tiene un diseño razonable. También hay borradores de calidad y de adquisiciones con bastante detalle.

Sin embargo, el conjunto **todavía no está alineado con PMBOK 7**. La documentación está construida con una lógica cercana a PMBOK 6 (procesos, áreas de conocimiento, planes separados) y presenta **tres problemas sistémicos**:

1. **No existe una línea base única.** El nombre del proyecto, las fechas, los objetivos, las métricas, el presupuesto y los entregables cambian según el documento. Esto impide medir el desempeño y tomar decisiones confiables.
2. **El alcance está contaminado por funciones no aprobadas.** El EDT incluye registro de usuarios, recuperación de credenciales, cuatro roles, exportación a CSV/JSON/MATLAB, diagnóstico CIE-10/SNOMED, calibradores y archivos de 500 MB, mientras que el alcance y los requisitos excluyen varias de esas funciones.
3. **Los dominios de PMBOK 7 no están demostrados.** No hay caso de negocio, plan de beneficios, plan integrado, registro de riesgos, RACI, team charter, plan de medición, evaluación de complejidad ni registro de tailoring. La calidad existe en borradores, pero no está integrada al conjunto.

**Recomendación:** no aprobar el Acta ni la Especificación de Requisitos en su versión actual. Aplicar primero las correcciones **P0** (Sección 9), publicar una línea base `v1.0` y recién después iniciar la ejecución formal. Las correcciones P1 y P2 pueden ejecutarse en las dos semanas siguientes.

### 1.1. Semáforo general

| Dimensión                         |   Estado    | Motivo principal                                                                                                     |
| :-------------------------------- | :---------: | :------------------------------------------------------------------------------------------------------------------- |
| Gobernanza, valor y planificación |   🔴 Rojo   | Sin plan integrado, caso de negocio ni plan de beneficios; fechas y objetivos contradictorios                        |
| Alcance, requisitos y EDT         |   🔴 Rojo   | Funciones fuera de alcance en el EDT; paquete 1.2.3 vacío; métricas incompatibles                                    |
| Tiempo, costo y recursos          |   🔴 Rojo   | 24 semanas de EDT frente a una ventana real de 15; esfuerzo ya superior al límite antes de estimar módulos faltantes |
| Interesados y comunicaciones      | 🟡 Amarillo | Hay plan, pero los niveles están mal clasificados y faltan registros y canales                                       |
| Equipo y roles                    |   🔴 Rojo   | La “matriz” es un catálogo de competencias, no un RACI; 8 roles para 6 personas                                      |
| Riesgos e incertidumbre           |   🔴 Rojo   | Solo matriz 5×5 y 3 riesgos del Acta; sin registro, dueños, disparadores ni oportunidades                            |
| Calidad                           | 🟡 Amarillo | Buenos borradores, pero no integrados, indexados ni alineados a PMBOK 7                                              |
| Cambios y configuración           | 🟡 Amarillo | Diseño sólido, pero contradictorio con el borrador de cambios de código y con el Change Log                          |
| Medición y beneficios             |   🔴 Rojo   | Sin línea base, KPI, dashboard ni medición de beneficios post-cierre                                                 |
| Documentación y forma             | 🟡 Amarillo | Índice incompleto, nombres inconsistentes y errores de tipeo                                                         |

---

## 2. Alcance, fuentes y método

### 2.1. Documentos revisados

**Documentos publicados en `content/`:**

| Documento | Líneas | Uso en el análisis |
| :--- | ---: | :--- |
| `project-charter.md` | 183 | Propósito, objetivos, hitos, presupuesto, interesados |
| `requirements-documentation.md` | 111 | Requisitos de negocio, interesados, RF, RNF, transición y restricciones |
| `project-scope-statement.md` | 158 | Alcance del producto y del proyecto, entregables, aceptación, exclusiones |
| `work-breakdown-structure.md` | 86 | EDT y diagrama Mermaid |
| `wbs-dictionary.md` | 395 | Diccionario del EDT, estimaciones, riesgos y costos |
| `communications-management-plan.md` | 29 | Comunicaciones internas y externas |
| `stakeholder-engagement-plan.md` | 16 | Interesados y nivel de involucramiento |
| `requirements-traceability-matrix.md` | 65 | Trazabilidad RF/RNF/RT/RP |
| `probability-and-impact-matrix.md` | 80 | Matriz 5×5 y niveles de riesgo |
| `responsibility-assignment-matrix.md` | 155 | Perfiles, funciones y competencias |
| `change-control-plan.md` | 214 | SCM, cambios documentales, código, datos y UI |
| `index.md` | 24 | Índice de publicación |

**Borradores revisados:**

- `01_Plan_de_Gestion_de_la_Calidad.md`
- `02_Metricas_de_Calidad.md`
- `03_Listas_de_Verificacion_de_Calidad.md`
- `04_Informes_de_Calidad.md`
- `Gestión de adquisiciones.md`
- `Matriz de competencias.md`
- `Control de cambios de procesos del código.md`
- Notas de `Calidad del proyecto.md`, `Calidad del producto.md`, `Calidad del servicio.md` y `Calidad de procesos.md`

### 2.2. Método

1. **Lectura completa** de los artefactos y extracción de afirmaciones verificables (fechas, métricas, IDs, roles, entregables).
2. **Contraste cruzado** entre documentos: Acta ↔ Alcance ↔ Requisitos ↔ EDT ↔ Diccionario ↔ Trazabilidad ↔ Calidad ↔ Cambios.
3. **Mapeo a PMBOK 7**: 12 principios, 8 dominios de desempeño, tailoring y artefactos.
4. **Clasificación de severidad**:
   - **Crítico (C):** bloquea la aprobación de una línea base o genera riesgo legal, de alcance o de credibilidad.
   - **Alto (A):** produce retrabajo, ambigüedad o pérdida de trazabilidad.
   - **Medio (M):** afecta calidad documental, mantenibilidad o comunicación.
5. **Propuesta de corrección** con ubicación, acción, responsable y evidencia de verificación.

### 2.3. Límites del análisis

- No se tuvo acceso a decisiones del patrocinador, al código real, a los datos de prueba ni a las herramientas de gestión.
- Las fechas y horas se analizan como están escritas; cuando el documento no declara moneda o unidad, se indica la ambigüedad.
- Este documento **no reemplaza** la aprobación del patrocinador ni la revisión legal.

---

## 3. Lo que ya está bien

| Fortaleza | Evidencia | Valor para PMBOK 7 |
| :--- | :--- | :--- |
| Propósito claro y pertinente | Acta §5 y §7; Alcance §1 | Principio de **valor** y **stewardship** |
| Compromiso explícito con privacidad y ética | Ley 25.326, anonimización, RP-03 | **Stewardship** y **calidad** |
| Requisitos no funcionales medibles | RNF-01 a RNF-09; LCP ≤ 2,5 s; ≥ 30 FPS; ≤ 30 s de ingesta | **Calidad** y **medición** |
| Trazabilidad requisito → EDT | Matriz de trazabilidad completa para RF, RT, RNF y RP | **Sistemas** y **entrega** |
| Diccionario del EDT con riesgos y costos | Paquetes 1.1.x, 1.3.2.x | **Planificación** e **incertidumbre** |
| Control de cambios con CI, roles, flujo y Change Log | Plan SCM §1–§6 | **Cambio** y **gobernanza** |
| Borradores de calidad con métricas ISO/IEC 25010 | Documentos 01–04 | **Calidad** |
| Matriz de competencias y plan de mejora | Borrador “Matriz de competencias” | **Equipo** |
| Análisis de hacer o comprar | Borrador “Gestión de adquisiciones” | **Trabajo del proyecto** |

> **Conclusión:** no se parte de cero. Se trata de **consolidar, alinear y eliminar contradicciones**, no de reescribir todo.

---

## 4. Hallazgos consolidados

**Leyenda de severidad:** C = Crítico · A = Alto · M = Medio.

### 4.1. Gobernanza, valor y planificación

| ID       | Sev. | Ubicación                                                                         | Hallazgo                                                                                                                                                                                                               | Corrección propuesta                                                                                                              | PMBOK 7                     |
| :------- | :--: | :-------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------- | :-------------------------- |
| **H-01** |  C   | `project-charter.md:12`; frontmatter; borradores                                  | El nombre cambia entre “BioSignalsBank”, “BioSignal” y “BioSignals”.                                                                                                                                                   | Fijar **BioSignal** como nombre canónico y “Banco de Señales Biomédicas” como descriptor; reemplazar variantes y registrar alias. | Stewardship / Sistemas      |
| **H-02** |  C   | `project-charter.md:74-76`                                                        | Objetivos SMART contradictorios: “100 muestras” vs. 100 usuarios; latencia < 10 s vs. 2,5 s; fechas anteriores a la aprobación del Acta; 50 archivos vs. 30 del dataset; 5 cátedras vs. 2 programas; 10 min vs. 5 min. | Reescribir como **objetivos de salida** con métrica, fecha y verificación; mover adopción a **beneficios**.                       | Valor / Medición            |
| **H-03** |  C   | `project-charter.md:57,132,144-150,178`; `project-scope-statement.md:69,155`; EDT | Fechas incompatibles: fin 15/02/2027 vs. 27/11/2026; período 01/08–27/11/2026; EDT de 24 semanas; Acta aprobada 02/11/2026.                                                                                            | Aprobar **una sola línea base** (Sección 11.2) y recalcular EDT, hitos y capacidad.                                               | Planificación               |
| **H-04** |  C   | EDT 1.1.3; `index.md`                                                             | Se referencia un “Plan para la dirección del proyecto” que no existe en `content/`. Los planes subsidiarios están dispersos.                                                                                           | Crear `project-management-plan.md` como documento integrador con líneas base, tailoring y enlaces.                                | Planificación / Sistemas    |
| **H-05** |  C   | `borradores/01:24,82`; `change-control-plan.md`; `borradores/04:7`                | El enfoque declarado es PMBOK 6 (procesos 8.1, 8.2, 8.3) y no hay registro de tailoring.                                                                                                                               | Añadir **registro de tailoring** y explicar qué se adapta de PMBOK 7; usar PMBOK 6 solo como fuente de técnicas.                  | Tailoring                   |
| **H-06** |  C   | Acta (fases); `change-control-plan.md:191`                                        | No se define el enfoque de desarrollo: el EDT es predictivo, pero se mencionan “Sprints” sin cadencia, incrementos ni Definition of Done.                                                                              | Definir enfoque **híbrido**: compuertas por hito + iteraciones de 2 semanas, backlog, revisión y retrospectiva.                   | Desarrollo y ciclo de vida  |
| **H-07** |  C   | Acta §6–§7; Alcance §4                                                            | No hay un caso de negocio formal (solo la justificación del Acta §7) ni un plan de beneficios; la adopción académica se trata como criterio de aceptación, aunque ocurre después del cierre.                           | Crear **caso de negocio** (1 página) y **registro de beneficios** con dueño, métrica, línea base y ventana de medición.           | Valor                       |
| **H-33** |  A   | `project-charter.md`                                                              | Faltan presupuesto/fuente de fondos, gobernanza, firmas, criterios de éxito de producto vs. proyecto, ciclo de vida y registro de supuestos.                                                                           | Completar el Acta con las secciones mínimas de PMBOK 7 (Sección 11.2).                                                            | Planificación / Stewardship |
| **H-37** |  A   | EDT 1.1.4; documentos                                                             | Se mencionan SPI/CPI, pero no hay línea base, fórmula, fuente de datos, dashboard ni frecuencia de medición.                                                                                                           | Crear **plan de medición** con KPI, fórmula, meta, fuente, frecuencia y responsable.                                              | Medición                    |
| **H-40** |  A   | Todos                                                                             | No hay evaluación de complejidad ni estrategias de adaptabilidad/resiliencia (buffers, MVP, planes de respaldo).                                                                                                       | Agregar **evaluación de complejidad** y plan de resiliencia (Sección 11.9).                                                       | Complejidad / Adaptabilidad |
| **H-42** |  M   | Frontmatter de todos                                                              | No hay dueño, estado, fecha de aprobación, historial de cambios, clasificación ni “reemplaza a”.                                                                                                                       | Estandarizar metadatos y agregar historial de cambios a cada documento.                                                           | Stewardship / Cambio        |

### 4.2. Alcance, requisitos y EDT

| ID | Sev. | Ubicación | Hallazgo | Corrección propuesta | PMBOK 7 |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **H-08** | A | `project-charter.md:82-85`; `requirements-documentation.md:84` | Criterios de éxito inconsistentes: 50 usuarios/10 min vs. RNF-09 < 5 min; 5 cátedras vs. 2 programas; 50 archivos vs. 30 del dataset. | Unificar en un **scorecard** único (Sección 11.2) y eliminar duplicados. | Medición |
| **H-09** | A | `project-charter.md:84`; `project-scope-statement.md:142` | El Acta promete “realizar anotaciones”, pero el Alcance excluye el módulo de anotaciones y los requisitos no lo incluyen. | **Recomendado:** eliminar “anotaciones” del Acta y mantenerlo fuera de alcance. Si se quiere incluir, crear RF-15, paquete EDT y RFC. | Alcance / Entrega |
| **H-10** | A | `project-charter.md:120-124,170`; `project-scope-statement.md:99-115` | El Acta lista 3 entregables y luego exige “4 entregables”; el Alcance define 6 de producto (EP-01…EP-06) y 6 de proyecto (EJ-01…EJ-06). | Usar los IDs **EP/EJ**, definir 6 + 6 y actualizar criterios de aceptación y cierre. | Entrega |
| **H-11** | C | `wbs-dictionary.md:217,236,255,311,320,328` | El EDT incluye funciones fuera de alcance: registro y recuperación de credenciales, 4 roles, CSV/PhysioNet/MATLAB, CIE-10/SNOMED, calibradores, 50.000 registros, 500 MB/20 s y 60 FPS. | Aplicar la tabla de corrección de la Sección 11.4: eliminar o aprobar por RFC; alinear cada paquete a RF/RNF. | Entrega / Alcance |
| **H-12** | C | `wbs-dictionary.md:144-155`; paquetes 1.2.1, 1.2.2, 1.3.1.x, 1.3.3.x, 1.4.x, 1.5; `work-breakdown-structure.md:63` | El paquete **1.2.3 está vacío**; varios paquetes no tienen costos/riesgos; 1.3.2.1 y 1.3.2.2 no tienen fechas; el diagrama Mermaid omite 1.2.3. | Completar todos los paquetes con los 8 campos mínimos; agregar 1.2.3 al diagrama; unificar nombres. | Planificación |
| **H-23** | A | `wbs-dictionary.md:247,320,328` vs. `requirements-documentation.md:65-68` | Métricas del EDT incompatibles con los RNF: 60 FPS vs. 30 FPS; 500 MB/20 s vs. 50 MB/30 s; CSV/JSON/MAT vs. solo EDF/EDF+. | Adoptar los valores de los RNF y del Alcance; corregir el EDT vía RFC; agregar verificación de consistencia. | Calidad / Medición |
| **H-30** | A | `requirements-documentation.md:34-99` | Faltan prioridad, fuente, dueño, método de verificación y supuestos por requisito; faltan RNF de disponibilidad, backup/RTO/RPO, accesibilidad, auditabilidad, mantenibilidad y seguridad de autenticación. | Completar la ERS con campos y RNF-10 a RNF-14 (Sección 11.3). | Planificación / Entrega |
| **H-31** | A | `requirements-traceability-matrix.md` | La matriz no incluye casos de prueba, evidencia, estado, trazabilidad inversa ni beneficios; algunos anclajes pueden quedar huérfanos. | Extender la RTM con esas columnas y ejecutar una verificación de huérfanos. | Medición / Entrega |
| **H-32** | A | `project-scope-statement.md:117-129` | Los criterios de aceptación mezclan entregables con beneficios (“Adopción Académica”) y no definen autoridad ni acta de aceptación. | Separar **aceptación del proyecto** de **beneficios**; agregar línea base de alcance y firma. | Entrega / Valor |

### 4.3. Tiempo, costo y recursos

| ID | Sev. | Ubicación | Hallazgo | Corrección propuesta | PMBOK 7 |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **H-13** | C | `project-charter.md:156-158`; `wbs-dictionary.md:21` | El Acta declara costo directo **$0 USD**, pero el EDT estima **$10.000/h** y un total de **$4.100.000** en los paquetes estimados; además hay insumos pagos en adquisiciones. No se declara moneda. | Separar **desembolso de caja** ($0) de **costo interno de esfuerzo** (ARS, no erogable); declarar moneda, fuente y tratamiento de insumos en especie. | Planificación / Medición |
| **H-14** | C | `wbs-dictionary.md:21-101,240-281` | Los paquetes estimados suman **280 h** (346 h si se cuenta el reporte quincenal) antes de estimar 1.2.x, 1.3.1.x, 1.3.3.x, 1.4.x y 1.5; el límite declarado es 260–360 h. | Reestimar de abajo hacia arriba, calcular capacidad real y reducir alcance a un **MVP** o ampliar plazo. | Planificación / Equipo |
| **H-15** | A | `wbs-dictionary.md:21` | La estimación de tres valores usa **(TO + TM + TP) / 3**; la fórmula PERT correcta es **(TO + 4·TM + TP) / 6**. | Recalcular con PERT beta, desvío estándar y nivel de confianza; documentar el método. | Planificación |
| **H-16** | C | `wbs-dictionary.md` (fechas) vs. Acta (hitos) | El EDT asigna semanas 1–24, pero el Acta fija hitos que no coinciden: 1.1.1 semanas 1–2 vs. Acta 02/11; 1.1.2 semanas 2–4 vs. 09/11; 1.3.1.1 semanas 8–9 vs. 07/12; 1.3.2.1 y 1.3.2.2 sin fechas vs. Hito 4 del 01/02. | Crear un **Gantt único** con dependencias, ruta crítica, buffers y hitos de aceptación; re-mapear el EDT a la línea base aprobada. | Planificación / Medición |
| **H-17** | A | EDT; Acta | Si el proyecto inicia el 02/11/2026, la ventana hasta el 15/02/2027 es de **15 semanas**, no 24; no hay calendario de recursos ni nivelación. | Aprobar la **Opción A** (15 semanas, MVP) o la **Opción B** (24 semanas, inicio en agosto); nivelar recursos. | Equipo / Planificación |
| **H-18** | M | `project-charter.md:144-150` | Los “hitos” son entregables (“Módulo listo”, “Documento aprobado”), no eventos de aceptación. | Definir hitos como **decisión/aceptación** con criterio de salida y autoridad. | Planificación |
| **H-27** | C | `responsibility-assignment-matrix.md` | El documento es un catálogo de competencias, no una matriz RACI; hay 8 roles para 6 personas; UX/UI, DBA y DevOps no están asignados; QA es el mismo desarrollador backend. | Crear **RACI por paquete/entregable**, mapear 8 roles a 6 personas y separar la revisión de QA del autor. | Equipo / Planificación |
| **H-28** | A | `responsibility-assignment-matrix.md`; no hay team charter | No hay team charter, reglas de convivencia, gestión de conflictos, reconocimiento, plan de desarrollo, calendario de recursos ni sucesión. | Crear **team charter** y plan de recursos; reutilizar la matriz de competencias como anexo. | Equipo |

### 4.4. Interesados y comunicaciones

| ID | Sev. | Ubicación | Hallazgo | Corrección propuesta | PMBOK 7 |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **H-19** | A | `stakeholder-engagement-plan.md:12-16` | “Alta/Media/Baja” no está definido; estudiantes y docentes figuran como “Baja” aunque son críticos para la adopción; GAB figura “Media” aunque provee los datos. | Reemplazar por **registro de interesados + matriz de evaluación de involucramiento** (actual vs. deseado). | Interesados |
| **H-20** | A | `communications-management-plan.md:13,27` | “Por hito (5 instancias)” vs. 7 hitos; faltan filas de sponsor, TIC, legal/ética, GAB y usuarios; no hay escalamiento, feedback, confidencialidad, idioma ni retención. | Actualizar el plan con emisor, receptor, formato, canal, frecuencia, dueño, feedback y escalamiento (Sección 11.8). | Interesados / Comunicaciones |
| **H-29** | A | `stakeholder-engagement-plan.md:10-16` | La tabla no es un registro: no tiene ID, influencia, interés, actitud, contacto, expectativas ni estrategia. | Crear **registro de interesados** con IDs SI-01… y vincularlo a los RI de la ERS. | Interesados |

### 4.5. Riesgos, calidad y cambios

| ID | Sev. | Ubicación | Hallazgo | Corrección propuesta | PMBOK 7 |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **H-21** | C | `probability-and-impact-matrix.md`; `project-charter.md:135-138` | Solo hay matriz 5×5 y 3 riesgos en el Acta; no hay registro con dueño, causa, evento, efecto, disparador, respuesta, riesgo residual, reservas ni oportunidades. | Crear **registro de riesgos** e **informe de riesgos**; definir apetito, umbrales y revisión quincenal (Sección 11.6). | Incertidumbre |
| **H-22** | A | `borradores/01:24`; `index.md` | El plan de calidad está en borradores, no está indexado y se declara PMBOK 6; no hay costo de calidad ni integración con el resto. | Integrarlo como **plan subsidiario**, traducirlo a lenguaje PMBOK 7 e indexarlo cuando se apruebe. | Calidad |
| **H-24** | A | `change-control-plan.md:86,103,107-122,128,191`; `borradores/Control de cambios de procesos del código.md:14-23` | Contradicciones: ramas `main/develop` vs. `main/test/dev`; revisores distintos; “(alguna herramienta)”; ruta `/workspace/knowledge/`; CI-DOC incluye manuales fuera de alcance; Figma no es entregable; stack Node/Python/React vs. Next.js/FastAPI. | Consolidar **un solo plan SCM**, elegir un modelo de ramas, fijar herramienta y stack, y alinear el alcance de los CI. | Cambio |
| **H-25** | A | `change-control-plan.md:203-205`; ERS v1 | RFC del 05/10, 12/10 y 18/10 anteriores a la aprobación del Acta (02/11); RFC-001 cambia RNF-02 de 10 s a 2,5 s, pero el Acta sigue con 10 s y la ERS figura v1; RFC-003 aprobado sin actualizar requisitos ni DDL. | Rebaselinar versiones, crear RFC-004, vincular cada RFC a los artefactos afectados y registrar aprobación/fecha. | Cambio / Medición |
| **H-26** | A | `change-control-plan.md:36,43-67` | El CCB es PM + APM; no incluye al patrocinador para cambios de alcance, plazo o costo; no hay quórum, SLA de decisión, cambio de emergencia ni formulario de solicitud. | Definir **gobernanza del CCB**, quórum, plazos, ruta de emergencia y plantilla de RFC. | Cambio / Liderazgo |
| **H-36** | A | Acta, Alcance y EDT | Los supuestos están dispersos; no tienen dueño, fecha de validación, fecha de expiración ni vínculo con riesgos; no hay issue log ni lecciones aprendidas. | Crear **registro de supuestos**, **issue log** y **registro de lecciones aprendidas**. | Incertidumbre / Planificación |
| **H-38** | A | EDT 1.5; Alcance §6 | El despliegue solo contempla “smoke test”; no hay plan de transición, handover, runbook, monitoreo, backup/restore ni aceptación operativa. | Crear **plan de transición** y checklist de pase a operación, aunque el soporte posterior esté fuera de alcance. | Entrega |
| **H-39** | A | `borradores/Gestión de adquisiciones.md`; Acta §11 | Hay insumos pagos (VPS, SaaS, dominio, pentesting, UI/UX, dataset, IA) frente al $0; varios no están en el EDT (1.2.3 vacío); no hay decisión make-or-buy ni tipo de contrato. | Integrar el plan de adquisiciones, conciliar presupuesto, marcar insumos en especie/donados y eliminar lo no necesario. | Trabajo del proyecto |
| **H-41** | A | `requirements-documentation.md:65-84`; `change-control-plan.md:186` | Faltan RNF de disponibilidad, backup/RTO/RPO, accesibilidad, auditabilidad, mantenibilidad y seguridad de autenticación; la sanitización solo cubre la cabecera y no las anotaciones EDF+ ni los metadatos. | Agregar RNF-10 a RNF-14 y ampliar RF-06 a **toda** la información identificatoria (cabecera, TALs y metadatos). | Calidad / Stewardship |

### 4.6. Documentación y forma

| ID | Sev. | Ubicación | Hallazgo | Corrección propuesta | PMBOK 7 |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **H-34** | M | `index.md`; `public/` | El índice omite calidad, adquisiciones, riesgo, change log, team charter y medición; `public/` conserva nombres antiguos en español y puede tener enlaces rotos. | Actualizar el índice después de aprobar; reconstruir Quartz, agregar alias/redirecciones y verificar enlaces. | Sistemas / Stewardship |
| **H-35** | M | Varios | Errores y variantes: “Ingenierica”, “Modulo”, “Gestion”, “simultaneo”, “ejecutas”, “ECS/EMA/EM”, “BioSignal/BioSignalsBank/BioSignals”. | Crear glosario y guía de estilo; ejecutar corrección ortográfica y de acrónimos. | Calidad / Stewardship |

**Total:** 42 hallazgos (14 críticos, 24 altos, 4 medios).

---

## 5. Evaluación de los 12 principios de PMBOK 7

| Principio | Estado | Evidencia actual | Brecha principal | Acción correctiva |
| :--- | :---: | :--- | :--- | :--- |
| **1. Stewardship** (custodia) | 🟡 Parcial | Compromiso con Ley 25.326, ética y datos; PM con autoridad definida. | Cláusula de publicidad a favor del equipo; roles duplicados; datos sin política de retención. | Eliminar o formalizar la cláusula de publicidad; definir retención, clasificación y custodia de datos. |
| **2. Team** (equipo) | 🔴 Brecha | Roles y competencias descritos; matriz de suplencia. | Sin team charter, reglas, capacidad, conflictos, reconocimiento ni plan de desarrollo. | Crear team charter, RACI, calendario de recursos y plan de mejora. |
| **3. Stakeholders** (interesados) | 🔴 Brecha | Plan de interesados y comunicaciones existe. | Niveles mal clasificados; sin registro, actitud, influencia ni estrategia. | Registro + matriz de involucramiento actual/deseado + plan de comunicación. |
| **4. Value** (valor) | 🟡 Parcial | Objetivos estratégicos y de adopción. | Sin caso de negocio, beneficios, dueño ni medición post-cierre. | Caso de negocio y registro de beneficios con métricas y ventana. |
| **5. Systems Thinking** (pensamiento sistémico) | 🔴 Brecha | Documentos individuales bien elaborados. | Contradicciones entre Acta, Alcance, ERS, EDT, Calidad y Cambios. | Plan integrado + verificación cruzada + una sola línea base. |
| **6. Leadership** (liderazgo) | 🟡 Parcial | PM con autoridad y escalamiento al sponsor. | Gobernanza esporádica; sponsor solo en hitos; decisiones de alcance sin comité. | Definir comité directivo, cadencia, derechos de decisión y escalamiento. |
| **7. Tailoring** (adaptación) | 🔴 Brecha | Se usan técnicas de PMBOK 6. | No hay registro de por qué se eligen artefactos, enfoque ni métricas. | Registro de tailoring y justificación fit-for-purpose. |
| **8. Quality** (calidad) | 🟡 Parcial | Plan, métricas, checklists e informes en borradores. | No integrados, no indexados, con métricas contradictorias. | Integrar calidad al plan; alinear métricas; agregar costo de calidad. |
| **9. Complexity** (complejidad) | 🔴 Brecha | Proyecto técnicamente complejo (EDF, WebGL, múltiples escuelas). | No hay evaluación de complejidad ni estrategias. | Registro de complejidad (técnica, organizacional, ambigüedad, volatilidad). |
| **10. Risk** (riesgo) | 🔴 Brecha | Matriz 5×5 y 3 riesgos. | Sin registro, dueños, disparadores, reservas ni oportunidades. | Registro + informe + apetito + revisión quincenal. |
| **11. Adaptability & Resilience** | 🔴 Brecha | Plan secuencial con fecha única. | Sin buffers, MVP, escenarios ni plan de respaldo. | MVP MoSCoW, buffers, fallback de datos/infraestructura y go/no-go. |
| **12. Change** (cambio) | 🟡 Parcial | Plan SCM completo y Change Log. | Inconsistente con el borrador de código; RFC previos al Acta; sin impacto en beneficios. | Un solo SCM, RFC vinculadas, gestión del cambio organizacional y adopción. |

---

## 6. Evaluación de los 8 dominios de desempeño

| Dominio | Estado | Evidencia actual | Brecha | Resultado esperado | Artefactos mínimos |
| :--- | :---: | :--- | :--- | :--- | :--- |
| **Interesados** | 🔴 | Plan de 5 filas; comunicaciones básicas. | Sin registro, influencia, actitud ni estrategia por interesado. | Interesados identificados, priorizados y comprometidos. | Registro, matriz de involucramiento, plan de comunicaciones. |
| **Equipo** | 🔴 | Perfiles y competencias; suplencia. | Sin team charter, RACI, capacidad ni gestión de conflictos. | Equipo con roles claros, carga equilibrada y acuerdos. | Team charter, RACI, calendario, plan de desarrollo. |
| **Enfoque de desarrollo y ciclo de vida** | 🔴 | Fases predictivas y mención a “Sprint”. | Sin enfoque declarado, cadencia, incrementos ni DoD. | Enfoque híbrido coherente con incertidumbre y plazo. | Plan integrado, backlog, calendario de iteraciones, DoD. |
| **Planificación** | 🔴 | Acta, Alcance, ERS, EDT y Diccionario. | Sin plan integrado, líneas base, Gantt, capacidad ni presupuesto coherente. | Línea base aprobada y realista. | PMP, alcance, EDT, cronograma, costo, recursos, calidad, riesgos. |
| **Trabajo del proyecto** | 🟡 | Control de cambios y adquisiciones en borrador. | Adquisiciones no integradas; conocimiento y issues dispersos. | Trabajo ejecutado con control y trazabilidad. | Plan de adquisiciones, change log, issue log, lecciones. |
| **Entrega** | 🟡 | EP/EJ definidos; criterios de aceptación. | Alcance contaminado; aceptación mezclada con beneficios; sin transición. | Entregables aceptados y transición operativa. | Alcance, EDT, diccionario, criterios de aceptación, plan de transición. |
| **Medición** | 🔴 | SPI/CPI mencionados; métricas de calidad en borrador. | Sin línea base, dashboard, KPI ni medición de beneficios. | Desempeño y valor medidos con evidencia. | Plan de medición, dashboard, informes, registro de beneficios. |
| **Incertidumbre** | 🔴 | Matriz 5×5 y 3 riesgos. | Sin registro, dueños, disparadores, oportunidades ni complejidad. | Riesgos y complejidad gestionados. | Registro de riesgos, informe, evaluación de complejidad, reservas. |

---

## 7. Tailoring: qué conservar, qué crear y qué no crear

PMBOK 7 **no exige** producir los 49 procesos de PMBOK 6 ni todos los artefactos. Exige **adaptar** el enfoque al tamaño, complejidad, criticidad, cultura y necesidades del proyecto. Para BioSignal, un proyecto académico de 6 personas y 15–24 semanas, la adaptación razonable es:

### 7.1. Decisiones de tailoring

| Artefacto / práctica | Estado actual | Decisión | Justificación |
| :--- | :--- | :--- | :--- |
| Acta de Constitución | Existe | **Actualizar** | Alinear objetivos, fechas, presupuesto y entregables. |
| Caso de negocio | No existe | **Crear (1 página)** | Justificar valor, beneficios y costo de oportunidad. |
| Plan de beneficios | No existe | **Crear (registro)** | Medir adopción y valor después del cierre. |
| Plan para la dirección del proyecto | No existe | **Crear** | Integrar líneas base y planes subsidiarios. |
| Enunciado del alcance | Existe | **Actualizar** | Separar aceptación de beneficios y agregar línea base. |
| EDT | Existe | **Actualizar** | Re-mapear a la línea base y eliminar funciones fuera de alcance. |
| Diccionario del EDT | Existe | **Actualizar** | Completar 1.2.3 y todos los paquetes; corregir métricas y PERT. |
| Documento de requisitos | Existe | **Actualizar** | Agregar campos, RNF faltantes y sanitización completa. |
| Matriz de trazabilidad | Existe | **Actualizar** | Agregar pruebas, evidencia, estado y trazabilidad inversa. |
| Línea base de alcance | Parcial | **Crear** | Versionar alcance + EDT + diccionario. |
| Línea base de cronograma | No existe | **Crear** | Gantt con dependencias, ruta crítica y buffers. |
| Línea base de costos | No existe | **Crear** | Presupuesto de caja + costo interno + reservas. |
| Registro de interesados | No existe | **Crear** | Base para el plan de involucramiento. |
| Plan de involucramiento | Existe | **Actualizar** | Reemplazar Alta/Media/Baja por niveles PMBOK 7. |
| Plan de comunicaciones | Existe | **Actualizar** | Agregar canales, escalamiento, feedback y confidencialidad. |
| Team charter | No existe | **Crear** | Acuerdos, reglas, disponibilidad y conflictos. |
| Plan de recursos | No existe | **Fusionar** con team charter | Evitar duplicación en un equipo pequeño. |
| RACI | No existe | **Crear** | Asignar responsabilidad por paquete/entregable. |
| Plan de gestión de riesgos | No existe | **Crear (1 página)** | Apetito, umbrales, roles y cadencia. |
| Registro de riesgos | No existe | **Crear** | Dueño, causa, efecto, respuesta, disparador y residual. |
| Informe de riesgos | No existe | **Crear (plantilla)** | Resumen para el sponsor y el equipo. |
| Matriz de probabilidad e impacto | Existe | **Mantener** | Es útil; falta definir escalas y criterios. |
| Plan de calidad | Borrador | **Integrar** | Convertirlo en plan subsidiario y indexarlo. |
| Métricas de calidad | Borrador | **Integrar** | Alinear con RNF y ISO/IEC 25010. |
| Listas de verificación | Borrador | **Integrar** | Usarlas como evidencia de QA. |
| Informes de calidad | Borrador | **Integrar** | Plantillas oficiales; completar con datos reales. |
| Plan SCM / control de cambios | Existe | **Actualizar** | Consolidar con el borrador de código y corregir referencias. |
| Change Log | Parcial | **Crear/estandarizar** | Vincular RFC, versión, estado y artefacto. |
| Plan de adquisiciones | Borrador | **Integrar** | Conciliar $0, insumos en especie y EDT. |
| Make-or-buy | Borrador | **Integrar** | Justificar qué se compra y qué se hace. |
| Registro de supuestos | No existe | **Crear** | Dueño, validación, expiración y vínculo con riesgos. |
| Issue log | No existe | **Usar GitHub Issues** | No crear un documento separado; el equipo ya usa Git. |
| Lecciones aprendidas | No existe | **Crear (retrospectivas)** | Registrar al final de cada iteración/hito. |
| Lista de hitos | Parcial | **Actualizar** | Hitos como aceptación, no entregables. |
| Calendario del proyecto | No existe | **Usar herramienta** | GitHub Projects/Google Calendar; no duplicar. |
| Plan de medición | No existe | **Crear** | KPI, fórmulas, metas, fuentes y frecuencia. |
| Plan de transición | No existe | **Crear** | Handover, runbook, monitoreo, backup/restore y aceptación operativa. |
| Informe final / cierre | Parcial | **Crear (plantilla)** | Cierre formal con lecciones y aceptación. |
| Registro de tailoring | No existe | **Crear** | Justificar decisiones de esta tabla. |
| Estructura de desglose organizacional | No existe | **No aplica** | Equipo pequeño; el RACI cubre la asignación. |
| Estructura de desglose de recursos | No existe | **No aplica** | Se fusiona con team charter y RACI. |
| Estructura de desglose de riesgos | No existe | **Incluir en registro** | Categorías dentro del registro, sin documento aparte. |
| Contratos | No existen | **Crear solo si hay compra paga** | Si todo es en especie o gratuito, no aplica. |

### 7.2. Conjunto mínimo viable de artefactos

Para no burocratizar el proyecto, se propone este **set mínimo** (12 documentos, algunos fusionados):

1. Acta de Constitución actualizada.
2. Caso de negocio + registro de beneficios (puede ser un anexo del Acta).
3. Plan para la dirección del proyecto (integrador).
4. Línea base de alcance: Enunciado + EDT + Diccionario.
5. ERS + Matriz de trazabilidad.
6. Registro de interesados + plan de involucramiento.
7. Plan de comunicaciones.
8. Team charter + RACI.
9. Plan de calidad + métricas + checklists + informes (documentos 01–04).
10. Plan de riesgos + registro + informe.
11. Plan SCM + Change Log.
12. Plan de medición + plan de transición.

> **Criterio de tailoring:** si un artefacto no ayuda a tomar una decisión, entregar valor o cumplir un requisito legal, se fusiona o no se crea. La decisión se registra en el **registro de tailoring**.

---

## 8. Riesgos de no aplicar las correcciones

| Si no se corrige… | Consecuencia probable | Impacto |
| :--- | :--- | :--- |
| Nombre y línea base | Documentos y enlaces inconsistentes; auditoría confusa | Medio |
| Objetivos y fechas | Se planifica sobre una fecha imposible; se pierde credibilidad ante el sponsor | Alto |
| Alcance del EDT | Se desarrollan funciones no aprobadas; retrabajo y desvío de horas | Crítico |
| Esfuerzo y costo | Se excede el límite de 260–360 h o se descubre tarde | Crítico |
| RACI y team charter | Dos personas hacen lo mismo o nadie asume una tarea; conflictos | Alto |
| Riesgos | Un riesgo materializado (datos, infraestructura, rendimiento) detiene el proyecto | Crítico |
| Interesados | GAB no entrega datos; docentes no adoptan; sponsor no aprueba | Alto |
| Sanitización incompleta | Exposición de datos personales en TALs o metadatos; incumplimiento legal | Crítico |
| Change Log | No se puede demostrar qué versión se aprobó y desplegó | Alto |
| Beneficios | Se entrega software, pero no se demuestra adopción ni valor | Medio |

---

## 9. Correcciones priorizadas

### 9.1. P0 — Antes de aprobar el Acta (vence 30/10/2026)

| ID | Acción | Responsable | Evidencia de cierre |
| :--- | :--- | :--- | :--- |
| **P0-01** | Aprobar glosario, nombre canónico y guía de estilo (H-01, H-35). | PM + APM | Glosario v1.0 y `grep` sin variantes. |
| **P0-02** | Reescribir objetivos, éxito, entregables, presupuesto y fechas del Acta (H-02, H-03, H-08, H-10, H-13, H-33). | PM | Acta v1.0 con tablas de la Sección 11.2. |
| **P0-03** | Crear el Plan para la Dirección del Proyecto, el registro de tailoring y el enfoque híbrido (H-04, H-05, H-06). | PM + APM | `project-management-plan.md` v1.0. |
| **P0-04** | Crear caso de negocio y registro de beneficios; mover adopción a beneficios (H-07, H-32). | PM + Sponsor | Anexo de beneficios aprobado. |
| **P0-05** | Alinear ERS, Alcance, EDT y Diccionario; eliminar funciones fuera de alcance y completar 1.2.3 (H-09, H-11, H-12, H-23, H-30). | PM + QA + Backend | EDT v2.0 + diccionario completo. |
| **P0-06** | Reestimar esfuerzo/costo, calcular capacidad y elegir línea base A o B (H-13, H-14, H-15, H-16, H-17, H-18). | PM + equipo | Gantt + presupuesto + análisis de capacidad. |
| **P0-07** | Crear registro e informe de riesgos con dueños, disparadores y reservas (H-21). | PM + QA | Registro R-01…R-12 y acta de revisión. |
| **P0-08** | Crear RACI y team charter; mapear 8 roles a 6 personas y separar QA del autor (H-27, H-28). | PM + APM | RACI v1.0 + team charter firmado. |

### 9.2. P1 — Antes de aprobar Requisitos (02–13/11/2026)

| ID | Acción | Responsable | Evidencia de cierre |
| :--- | :--- | :--- | :--- |
| **P1-01** | Crear registro de interesados y matriz de involucramiento actual/deseado (H-19, H-29). | APM | Registro SI-01…SI-09. |
| **P1-02** | Actualizar comunicaciones con canales, escalamiento, feedback y confidencialidad (H-20). | APM | Plan v2.0. |
| **P1-03** | Integrar el plan de calidad, métricas, checklists e informes; traducir a PMBOK 7 (H-22). | QA | Documentos 01–04 aprobados e indexados. |
| **P1-04** | Extender la RTM con pruebas, evidencia, estado y trazabilidad inversa (H-31). | QA + APM | RTM v2.0 sin huérfanos. |
| **P1-05** | Consolidar el plan SCM con el borrador de código; corregir ramas, ruta, herramienta, CI y stack (H-24, H-25, H-26). | PM + Infra | Plan SCM v2.0 + RFC-004…010. |
| **P1-06** | Crear plan de medición con KPI, fórmulas, fuentes y frecuencia (H-37). | PM + QA | Dashboard y ficha de KPI. |
| **P1-07** | Agregar RNF-10 a RNF-14 y ampliar la sanitización a TALs y metadatos (H-30, H-41). | QA + Backend + Legal | ERS v2.0 + dictamen legal. |
| **P1-08** | Crear registros de supuestos, issues y lecciones aprendidas (H-36). | APM | Logs activos y revisados. |

### 9.3. P2 — Antes del primer hito de ejecución (16–27/11/2026)

| ID | Acción | Responsable | Evidencia de cierre |
| :--- | :--- | :--- | :--- |
| **P2-01** | Actualizar índice, publicación Quartz, alias y enlaces (H-34). | APM | `index.md` v2.0 + build sin enlaces rotos. |
| **P2-02** | Crear plan de transición y checklist de pase a operación (H-38). | PM + Infra | Plan de transición aprobado. |
| **P2-03** | Integrar adquisiciones, conciliar $0 y eliminar insumos no necesarios (H-39). | PM + Sponsor | Plan de adquisiciones v1.0. |
| **P2-04** | Crear evaluación de complejidad y plan de resiliencia/MVP (H-40). | PM + equipo | Matriz de complejidad + plan de buffers. |
| **P2-05** | Estandarizar metadatos y control documental (H-42). | APM | Frontmatter y historial en todos los documentos. |
| **P2-06** | Corrección ortográfica y de acrónimos (H-35). | APM | Checklist de estilo completada. |

---

## 10. Correcciones específicas por documento

| Documento | Líneas / sección | Problema | Corrección concreta |
| :--- | :--- | :--- | :--- |
| `project-charter.md` | 12 | “BioSignal” vs. frontmatter “BioSignalsBank” | Usar “BioSignal” y descriptor “Banco de Señales Biomédicas”. |
| `project-charter.md` | 74-76 | Objetivos contradictorios | Reemplazar por la tabla de la Sección 11.2. |
| `project-charter.md` | 82-85 | Criterios de éxito inconsistentes | Unificar con el scorecard de la Sección 11.2. |
| `project-charter.md` | 120-124 | 3 entregables | Reemplazar por EP-01…EP-06 y EJ-01…EJ-06. |
| `project-charter.md` | 132 | Período 01/08–27/11/2026 | Reemplazar por la línea base aprobada (A o B). |
| `project-charter.md` | 144-150 | Hitos vs. entregables | Renombrar como “hitos de aceptación” y alinear fechas. |
| `project-charter.md` | 156-158 | $0 vs. costo interno y publicidad | Separar caja/esfuerzo; eliminar o formalizar publicidad. |
| `project-charter.md` | 162 | “Ingenierica” | “Ingeniería”. |
| `project-charter.md` | 170 | “4 entregables” | “6 entregables de producto y 6 de proyecto”. |
| `project-charter.md` | 178 | Despliegue antes del 27/11/2026 | Alinear con la fecha de cierre 15/02/2027. |
| `project-scope-statement.md` | 25 | Sección pública y banners | Mantener, pero aclarar que la señal demo es sintética o anonimizada. |
| `project-scope-statement.md` | 32 | Dataset de 30 | Alinear con RT-01 y eliminar “50 archivos” del Acta. |
| `project-scope-statement.md` | 41-45 | Métricas de desempeño | Mantener 100 usuarios, 2,5 s, 30 FPS y 30 s; agregar método de medición. |
| `project-scope-statement.md` | 69 | Hito 7 ≤ 15/02/2027 | Mantener; alinear hitos 1–6. |
| `project-scope-statement.md` | 119-129 | Aceptación mezclada con beneficios | Separar tablas de aceptación y beneficios (Sección 11.3). |
| `project-scope-statement.md` | 133-136 | Supuestos sin dueño | Mover al registro de supuestos con dueño y fecha. |
| `project-scope-statement.md` | 140-151 | Exclusiones | Mantener; agregar “registro/recuperación de credenciales” si se decide excluir. |
| `project-scope-statement.md` | 155-157 | Restricciones | Alinear con la línea base y el presupuesto. |
| `requirements-documentation.md` | 34-39 | RF-01 a RF-03 | Aclarar que solo hay 2 roles (Administrador/Consultor); agregar criterios de sesión. |
| `requirements-documentation.md` | 43-47 | RF-04 a RF-08 | Ampliar RF-06 a TALs y metadatos; aclarar baja lógica/restauración. |
| `requirements-documentation.md` | 51-59 | RF-09 a RF-14 | Agregar métrica de FPS y método; RF-14 debe exigir archivo sanitizado. |
| `requirements-documentation.md` | 65-84 | RNF-01 a RNF-09 | Agregar RNF-10 a RNF-14 (disponibilidad, backup, accesibilidad, auditoría, mantenibilidad). |
| `requirements-documentation.md` | 90-99 | RT/RP | Alinear con EDT y agregar dueño/fecha. |
| `work-breakdown-structure.md` | 9-38 | EDT de 24 semanas | Re-mapear a la línea base aprobada; agregar 1.2.3. |
| `work-breakdown-structure.md` | 37 | 1.5 con tabulación | Corregir indentación a 4 espacios. |
| `work-breakdown-structure.md` | 63 | Mermaid omite 1.2.3 | Agregar nodo y enlace. |
| `wbs-dictionary.md` | 21-23 | Fórmula PERT incorrecta | Cambiar a `(TO + 4·TM + TP) / 6`. |
| `wbs-dictionary.md` | 144-155 | Paquete 1.2.3 vacío | Completar objetivo, descripción, prerrequisitos, actividades, fechas, aceptación y supuestos. |
| `wbs-dictionary.md` | 217 | Roles: Admin, Investigador, Usuario, Auditor | Reducir a Administrador y Consultor, o aprobar nuevos roles por RFC. |
| `wbs-dictionary.md` | 236 | Detecta EDF, CSV, PhysioNet | Dejar solo EDF/EDF+; eliminar otros formatos. |
| `wbs-dictionary.md` | 247 | 500 MB en 20 s | Cambiar a < 50 MB en ≤ 30 s (RNF-04). |
| `wbs-dictionary.md` | 255 | CIE-10/SNOMED, medicamentos | Alinear con RF-07 (tipo, patología, grupo etario, equipamiento, notas) o ampliar RF-07. |
| `wbs-dictionary.md` | 311 | Calibradores/mediciones | Eliminar si las anotaciones están fuera de alcance; si se mantienen, crear RF-15. |
| `wbs-dictionary.md` | 320 | 60 FPS y 1.000.000 muestras | Cambiar a ≥ 30 FPS y definir tamaño máximo (50 MB/32 canales). |
| `wbs-dictionary.md` | 328 | CSV, JSON, MATLAB | Dejar solo EDF/EDF+; si se quiere exportar, crear RFC. |
| `wbs-dictionary.md` | 337 | Validación con MNE/WFDB | Mantener como método de verificación, no como formato de salida. |
| `stakeholder-engagement-plan.md` | 10-16 | Niveles Alta/Media/Baja | Reemplazar por registro + matriz de involucramiento (Sección 11.5). |
| `communications-management-plan.md` | 13 | “Por hito (5 instancias)” | Cambiar a 7 hitos o a la cadencia aprobada. |
| `communications-management-plan.md` | 27 | “Cierre de hito” con `<br>` | Limpiar HTML y definir responsable. |
| `communications-management-plan.md` | 29 | Imágenes embebidas | Mover a anexo o eliminar si no aportan; verificar accesibilidad. |
| `probability-and-impact-matrix.md` | 63-80 | Solo matriz | Agregar referencia al registro de riesgos y definir escalas/criterios. |
| `responsibility-assignment-matrix.md` | 8-155 | Catálogo de competencias | Mantener como anexo; crear RACI (Sección 11.7). |
| `change-control-plan.md` | 86 | Ruta `/workspace/knowledge/` | Cambiar a `content/` y URL del repositorio. |
| `change-control-plan.md` | 103 | Repos backend/frontend y stack | Fijar stack canónico (Next.js/React + FastAPI/Python + PostgreSQL) en un ADR. |
| `change-control-plan.md` | 107-122 | Ramas `main/develop` | Unificar con el borrador de código en un solo modelo. |
| `change-control-plan.md` | 128 | Revisores Herrera/Mosainer | Definir pool de revisores y regla de independencia. |
| `change-control-plan.md` | 149 | “ejecutas” | “ejecutadas”. |
| `change-control-plan.md` | 191 | “(alguna herramienta)” | Reemplazar por GitHub Projects. |
| `change-control-plan.md` | 203-205 | RFC antes del Acta | Rebaselinar fechas y versiones; crear RFC-004…010. |
| `index.md` | 4-24 | Índice incompleto | Agregar calidad, adquisiciones, riesgos, change log, team charter y medición cuando se aprueben. |
| `borradores/01` | 24, 82 | PMBOK 6 | Cambiar a lenguaje PMBOK 7 y agregar referencia al tailoring. |
| `borradores/02` | 154 | Observación de consistencia | Convertir la observación en RFC y corregir el EDT. |
| `borradores/Control de cambios de procesos del código.md` | 14-23 | Ramas `main/test/dev` | Alinear con el plan SCM consolidado. |
| `borradores/Matriz de competencias.md` | 15 | “PMBOK 6/7” y proceso de adquisiciones | Actualizar a PMBOK 7 y separar competencias de RACI. |

---

## 11. Propuestas de texto corregido

### 11.1. Nombre canónico, glosario y guía de estilo

**Texto propuesto para el encabezado de todos los documentos:**

> El nombre canónico del proyecto es **BioSignal**. Su descriptor institucional es **Banco de Señales Biomédicas de la Universidad Nacional de Villa Mercedes (UNViMe)**. En documentos nuevos no se usarán las variantes “BioSignalsBank” ni “BioSignals”. Las variantes históricas se conservan solo como alias de búsqueda.

| Término | Uso canónico | Observación |
| :--- | :--- | :--- |
| Proyecto | **BioSignal** | No “BioSignalsBank” ni “BioSignals”. |
| Producto | **Banco de Señales Biomédicas** | Descriptor, no nombre comercial. |
| Universidad | **UNViMe** | Universidad Nacional de Villa Mercedes. |
| Escuela patrocinadora | **EICA** | Escuela de Ingeniería y Ciencias Ambientales. |
| Escuela usuaria | **ECS** | Escuela de Ciencias de la Salud. |
| Escuela usuaria | **EM** | Escuela de Medicina. No usar “EMA” salvo que se defina. |
| Grupo de datos | **GAB** | Grupo de Bioingeniería / administradores de datos. |
| Formato | **EDF/EDF+** | Incluye ambos; no usar “.edf” para referirse al estándar completo. |
| Requisito de negocio | **RN-xx** | Ej. RN-01. |
| Requisito de interesado | **RI-xx** | Ej. RI-01. |
| Requisito funcional | **RF-xx** | Ej. RF-01. |
| Requisito no funcional | **RNF-xx** | Ej. RNF-01. |
| Requisito de transición | **RT-xx** | Ej. RT-01. |
| Restricción del proyecto | **RP-xx** | Ej. RP-01. |
| Entregable de producto | **EP-xx** | Ej. EP-01. |
| Entregable de proyecto | **EJ-xx** | Ej. EJ-01. |
| Hallazgo de este análisis | **H-xx** | Ej. H-01. |
| Riesgo | **R-xx** | Ej. R-01. |
| Oportunidad | **O-xx** | Ej. O-01. |
| Solicitud de cambio | **RFC-xxx** | Ej. RFC-004. |
| Estructura de desglose | **EDT** | Equivalente a WBS; definir una vez. |
| Matriz de asignación | **RACI** | Responsable, Aprobador, Consultado, Informado. |

**Reglas de estilo:**

1. Español con acentos y signos de apertura; revisar con corrector ortográfico.
2. Fechas en formato `DD/MM/AAAA`; no mezclar con `YYYY-MM-DD` salvo en nombres de archivo.
3. Moneda explícita: `ARS` o `USD`; nunca `$` sin aclaración.
4. Porcentajes con coma decimal: `2,5 %`, `99,9 %`.
5. Un solo término por concepto: “interesado”, no “stakeholder” salvo en paréntesis la primera vez.
6. Los IDs no cambian una vez aprobados; si cambia el alcance, se crea un ID nuevo y se marca el anterior como obsoleto.
7. Todo documento lleva frontmatter con `project`, `version`, `title`, `aliases`, `status`, `owner`, `approved_by`, `date` y `history`.

---

### 11.2. Acta de Constitución: objetivos, línea base y criterios de éxito

#### 11.2.1. Decisión pendiente: línea base A o B

| Opción | Inicio | Fin | Semanas | Supuesto | Viabilidad |
| :--- | :--- | :--- | ---: | :--- | :--- |
| **A (recomendada)** | 02/11/2026 | 15/02/2027 | 15 | Alcance MVP, iteraciones de 2 semanas, trabajo paralelo, 4 h/semana por persona | Alta, si se reduce el alcance |
| **B** | 31/08/2026 | 15/02/2027 | 24 | EDT actual, Acta aprobada en septiembre, equipo trabajando desde agosto | Baja: la documentación se está elaborando en octubre y el Acta se aprobaría en noviembre |
| **C** | 02/11/2026 | 30/04/2027 | 26 | Extender el plazo | No recomendada: incumple el calendario académico |

> **Recomendación:** aprobar la **Opción A** y reducir el alcance a un MVP. La Opción B solo es válida si el sponsor confirma que el proyecto ya estaba en ejecución desde agosto y que la fecha del Acta (02/11/2026) es un error.

#### 11.2.2. Hitos propuestos para la Opción A

| Hito de aceptación | Fecha | Criterio de salida | Autoridad |
| :--- | :--- | :--- | :--- |
| **H1 — Acta aprobada** | 02/11/2026 | Acta firmada, glosario y línea base v1.0 | Sponsor EICA |
| **H2 — Requisitos aprobados** | 13/11/2026 | ERS + RTM + criterios de aceptación firmados | PM + GAB |
| **H3 — Autenticación/RBAC aceptada** | 18/12/2026 | 2 roles, sesión 30 min, 0 hallazgos críticos de elevación de privilegios | QA + PM |
| **H4 — Ingesta y sanitización aceptadas** | 15/01/2027 | 30 EDF cargados, 0 % PII residual, ≤ 30 s por archivo < 50 MB | QA + Legal |
| **H5 — Visualizador y exportación aceptados** | 29/01/2027 | 32 canales, ≥ 30 FPS, LCP ≤ 2,5 s, exportación EDF sanitizada | QA + docentes |
| **H6 — QA/UAT cerrado** | 05/02/2027 | 0 defectos críticos/bloqueantes; UAT aprobada | QA + Sponsor |
| **H7 — Despliegue y cierre** | 12/02/2027 | Producción en `*.unvime.edu.ar`, TLS 1.3, backup/restore probado, acta firmada | TIC + Sponsor |

#### 11.2.3. Objetivos medibles del proyecto (salidas)

| ID | Objetivo | Métrica | Fecha | Verificación |
| :--- | :--- | :--- | :--- | :--- |
| **O-01** | Entregar autenticación y RBAC con dos roles | 2 roles; expiración Admin a los 30 min; 0 hallazgos críticos de elevación de privilegios | 18/12/2026 | Pruebas de seguridad y QA |
| **O-02** | Entregar ingesta, sanitización y baja lógica | 30 EDF (15 ECG + 15 EEG); 0 % PII residual en cabecera, TALs y metadatos; ≤ 30 s por archivo < 50 MB | 15/01/2027 | Auditoría binaria + benchmark |
| **O-03** | Entregar visualizador interactivo | 32 canales; ≥ 30 FPS; LCP ≤ 2,5 s en ≥ 10 Mbps; 100 usuarios concurrentes | 29/01/2027 | Lighthouse, DevTools, k6/JMeter |
| **O-04** | Entregar exportación y acceso público | Descarga EDF anonimizado; señal demo sintética o anonimizada; enlace a admisiones | 29/01/2027 | Prueba funcional + inspección |
| **O-05** | Desplegar en producción | Dominio `*.unvime.edu.ar`; TLS 1.3; backup/restore probado; smoke test 100 % | 12/02/2027 | Acta TIC + QA |
| **O-06** | Cerrar el proyecto | 0 defectos críticos/bloqueantes; acta de cierre firmada; lecciones aprendidas | 15/02/2027 | Sponsor + PM |
| **O-07** | Cumplir la línea base de gestión | Variación de esfuerzo/costo ≤ 10 %; 100 % de cambios registrados | 15/02/2027 | EVM + Change Log |

#### 11.2.4. Criterios de éxito por interesado

| Interesado | Criterio de éxito | Tipo | Evidencia |
| :--- | :--- | :--- | :--- |
| **Sponsor (EICA)** | Sistema en producción, $0 de desembolso directo, acta de aceptación firmada | Proyecto | Acta + facturas/registro de caja |
| **GAB** | 30 EDF catalogados, 0 % PII residual, metadatos completos | Producto | Inventario + auditoría |
| **Estudiantes y docentes (ECS/EM)** | 50 usuarios completan “buscar–abrir–configurar” en < 5 min; 2 cátedras adoptan | Beneficio | UAT + guías de cátedra |
| **Dirección TIC** | Despliegue, monitoreo, backup y restore verificados | Producto | Checklist de transición |
| **Equipo** | ≤ 360 h totales, 0 accidentes de seguridad, aprendizaje documentado | Proyecto | EVM + retrospectivas |

> **Nota:** la adopción en 2 cátedras y los 50 usuarios son **beneficios**, no criterios de aceptación del producto. Se miden después del cierre, con dueño y ventana definidos (Sección 11.9).

#### 11.2.5. Entregables corregidos

| ID | Entregable | Criterio de aceptación | Autoridad |
| :--- | :--- | :--- | :--- |
| **EP-01** | Autenticación y RBAC | 2 roles; sesión 30 min; 0 hallazgos críticos | QA + PM |
| **EP-02** | Ingesta, sanitización y baja lógica | 30 EDF; 0 % PII; ≤ 30 s/< 50 MB; auditoría | QA + Legal |
| **EP-03** | Visualizador interactivo | 32 canales; ≥ 30 FPS; LCP ≤ 2,5 s; 100 usuarios | QA + docentes |
| **EP-04** | Acceso público y enlace institucional | Señal demo; enlace a admisiones; sin credenciales | PM + QA |
| **EP-05** | Exportación EDF | Archivo sanitizado, íntegro y trazable | QA |
| **EP-06** | Dataset semilla | 30 EDF catalogados (15 ECG + 15 EEG) | GAB + QA |
| **EJ-01** | Acta de Constitución | Firmada y versionada | Sponsor |
| **EJ-02** | ERS + RTM | Aprobadas y sin huérfanos | PM + GAB |
| **EJ-03** | Repositorios de código | Versionados, con CI y README | PM + Infra |
| **EJ-04** | Reporte consolidado de QA | Pruebas, evidencias y 0 críticos | QA |
| **EJ-05** | Acta de despliegue | Producción verificada | TIC + PM |
| **EJ-06** | Acta de cierre | Aceptación final y lecciones | Sponsor + PM |

---

### 11.3. Alcance, requisitos y aceptación

#### 11.3.1. Separar aceptación de beneficios

**Criterios de aceptación del proyecto** (se verifican antes del cierre):

| Entregable / área | Criterio medible | Método | Autoridad |
| :--- | :--- | :--- | :--- |
| EP-01 | 2 roles; 403 ante acción no permitida; sesión 30 min | Pruebas de seguridad | QA |
| EP-02 | 0 % PII residual; ≤ 30 s/< 50 MB; baja lógica auditada | Auditoría binaria + benchmark | QA + Legal |
| EP-03 | 32 canales; ≥ 30 FPS; LCP ≤ 2,5 s; 100 usuarios | Lighthouse + DevTools + k6 | QA |
| EP-04 | Señal demo y enlace funcional sin credenciales | Demostración | PM |
| EP-05 | EDF sanitizado, íntegro, con hash verificable | Comparación de hash | QA |
| EP-06 | 30 EDF catalogados (15 ECG + 15 EEG) | Inventario en BD | GAB |
| EJ-01…EJ-06 | Documentos firmados y versionados | Inspección | Sponsor |

**Beneficios esperados** (se miden después del cierre; no bloquean la aceptación):

| ID | Beneficio | Métrica | Línea base | Meta | Dueño | Ventana |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **B-01** | Soberanía de datos | % de datos en infraestructura UNViMe | 0 % | 100 % | Sponsor | Al cierre + 6 meses |
| **B-02** | Adopción curricular | Cátedras que usan BioSignal en TP | 0 | 2 | Sponsor + PM | 1.er semestre 2027 |
| **B-03** | Uso académico | Usuarios que completan una tarea | 0 | 50 | PM | 3 meses post-cierre |
| **B-04** | Usabilidad | Tiempo medio “buscar–abrir–configurar” | Sin dato | < 5 min | QA | UAT |
| **B-05** | Ahorro de licencias | Costo anual de licencias | > 0 | $0 USD | Sponsor | Anual |
| **B-06** | Divulgación institucional | Jornadas con demostración | 0 | 1 | Sponsor | 2027 |

#### 11.3.2. RNF adicionales propuestos

| ID | Requisito | Métrica / criterio | Verificación |
| :--- | :--- | :--- | :--- |
| **RNF-10** | Disponibilidad | ≥ 99,9 % mensual en producción | Monitoreo de uptime |
| **RNF-11** | Respaldo y recuperación | Backup diario; RTO ≤ 4 h; RPO ≤ 24 h; restore probado | Prueba de restore |
| **RNF-12** | Accesibilidad | WCAG 2.1 AA; navegación por teclado; contraste; lector de pantalla | Auditoría + pruebas manuales |
| **RNF-13** | Auditabilidad | 100 % de altas, bajas, ediciones y descargas con usuario, fecha, acción y resultado | Inspección de logs |
| **RNF-14** | Mantenibilidad | Cobertura > 80 % en lógica crítica; complejidad ciclomática ≤ 10; lint/tipado limpio | CI + reporte |
| **RNF-15** | Seguridad de autenticación | Rate limiting; bloqueo tras 5 intentos; política de contraseñas; sesión 30 min | Pruebas de seguridad |

#### 11.3.3. Corrección de RF-06 (sanitización)

**Texto propuesto:**

> **RF-06 (Sanitización y anonimización irreversible):** durante la ingesta, el servidor debe sobrescribir o eliminar de forma definitiva e irreversible los datos de identificación personal en: (a) la cabecera EDF/EDF+, incluidos nombre, documento, identificación local, fecha de nacimiento y cualquier campo que permita identificar al paciente; (b) los canales de anotaciones TAL de EDF+; y (c) los metadatos libres cargados por el administrador. Se conservarán únicamente datos clínicos agregados (por ejemplo, grupo etario) cuando no permitan reidentificación por combinación con patología, institución, equipo o fecha. El proceso debe generar evidencia de auditoría y ser verificado sobre el 100 % de los archivos.

**Motivo:** la redacción actual solo cubre la cabecera y deja fuera las anotaciones EDF+ y los metadatos, que también pueden contener información personal.

#### 11.3.4. Métrica de tiempo de visualización

Se propone definir una métrica propia, **TTIS** (*Time to Interactive Segment*), medida con `PerformanceObserver` y el primer frame interactivo del canvas. LCP se conserva como referencia de experiencia web, pero no reemplaza la medición del primer segmento interactivo de la señal. Criterio: **TTIS ≤ 2,5 s** en red ≥ 10 Mbps.

---

### 11.4. EDT y Diccionario: tabla de corrección

| Paquete | Texto actual | Corrección propuesta | Motivo |
| :--- | :--- | :--- | :--- |
| **1.2.3** | Vacío | Completar: objetivo, descripción, prerrequisitos, actividades, fechas, aceptación y supuestos. Ejemplo: “Cargar y catalogar 30 EDF (15 ECG/15 EEG) con metadatos y evidencia de anonimización, semanas 3–5”. | Es un paquete crítico y hoy no es auditable. |
| **1.3.1.2** | Registro de usuarios con doble opt-in y Captcha | **Eliminar del MVP** o crear RF-15 y justificarlo. Si los usuarios los crea el Administrador, no se necesita registro público. | No está en el Alcance ni en la ERS. |
| **1.3.1.3** | Recuperación de credenciales | **Eliminar del MVP** o crear RF-16. | No está en el Alcance ni en la ERS. |
| **1.3.1.4** | Roles: Administrador, Investigador Clínico, Usuario Estándar y Auditor | Reducir a **Administrador** y **Consultor**; si se necesitan más roles, crear RFC y actualizar RF-01. | Contradice el Alcance y la ERS. |
| **1.3.2.1** | Detecta EDF, CSV, PhysioNet; archivos de 500 MB en 20 s | Solo **EDF/EDF+**; **< 50 MB en ≤ 30 s**; lectura por streaming. | Contradice RF-04 y RNF-04. |
| **1.3.2.2** | CIE-10/SNOMED, medicamentos, eventos | Alinear con **RF-07**: tipo de señal, patología de referencia, grupo etario, equipamiento y notas clínicas. | Evita alcance no aprobado. |
| **1.3.2.3** | Restauración por administradores | Mantener solo si RF-08 se amplía a restauración; si no, baja lógica sin restauración visible. | Consistencia con RF-08. |
| **1.3.3.1** | Catálogo de 50.000 registros | Cambiar a “30 registros semilla + prueba de escalabilidad a 1.000 registros” o justificar 50.000. | El dataset es de 30; 50.000 no tiene fuente. |
| **1.3.3.2** | 60 FPS; 1.000.000 de muestras; calibradores | **≥ 30 FPS**; definir tamaño máximo < 50 MB y 32 canales; **eliminar calibradores** si las anotaciones están fuera de alcance. | Contradice RNF-03 y el Alcance. |
| **1.3.3.3** | Exporta CSV, JSON, EDF y MATLAB `.mat` | Solo **EDF/EDF+**; agregar registro de auditoría de descargas. | Contradice RF-14 y las exclusiones. |
| **1.4.1 / 1.4.2** | Sin fechas ni esfuerzo | Agregar fechas, horas, costo y riesgo; 1.4.2 debe cubrir UAT y pruebas de carga. | Completar la línea base. |
| **1.5** | Sin horas ni costo | Agregar esfuerzo, costo, riesgo y fecha; incluir transición y handover. | Completar la línea base. |
| **Todas las tablas** | PERT `(TO + TM + TP) / 3` | `(TO + 4·TM + TP) / 6`, con desvío estándar y nivel de confianza. | Fórmula PERT correcta. |

**Regla de consistencia:** ningún paquete del EDT puede introducir un requisito, formato, rol, métrica o funcionalidad que no esté en la ERS y en el Alcance. Si se necesita, se crea un RFC y se actualizan ambos documentos antes de estimar.

---

### 11.5. Registro de interesados y matriz de involucramiento

**Niveles de involucramiento (PMBOK 7):**

| Nivel | Definición |
| :--- | :--- |
| **Inconsciente** | No conoce el proyecto ni su impacto. |
| **Reticente** | Conoce el proyecto y se opone o resiste. |
| **Neutral** | Conoce el proyecto, pero no participa activamente. |
| **Partidario** | Apoya el proyecto y colabora. |
| **Líder** | Impulsa el proyecto y moviliza a otros. |

**Registro propuesto:**

| ID | Interesado | Rol | Interés | Influencia | Actitud | Nivel actual | Nivel deseado | Estrategia | Dueño | Frecuencia |
| :--- | :--- | :--- | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :--- |
| **SI-01** | Alejandro Rosas / EICA | Sponsor | Alto | Alta | Partidario | Partidario | Líder | Reporte ejecutivo y decisiones de línea base | PM | Mensual + hito |
| **SI-02** | GAB / administradores de Bioingeniería | Proveedor de datos y usuario | Alto | Alta | Partidario | Partidario | Líder | Reunión quincenal, dataset y validación clínica | PM | Quincenal |
| **SI-03** | Dirección TIC UNViMe | Infraestructura | Alto | Alta | Neutral | Neutral | Partidario | Plan de infraestructura, SLA y pase a producción | Infra | Semanal en infra |
| **SI-04** | Estudiantes ECS/EM | Usuario final | Alto | Baja | Neutral | Neutral | Partidario | Pilotos, UAT y comunicación de beneficios | APM | Por hito |
| **SI-05** | Docentes de cátedra | Usuario y adoptante | Alto | Media | Neutral | Neutral | Partidario | Validación de casos y guías de TP | PM | Quincenal |
| **SI-06** | Equipo de desarrollo | Ejecutor | Alto | Alta | Partidario | Partidario | Líder | Team charter, weekly y retrospectiva | PM | Semanal |
| **SI-07** | Asesoría legal / comité de ética | Control | Medio | Alta | Neutral | Neutral | Partidario | Dictamen de Ley 25.326 y convenios | PM | Por hito |
| **SI-08** | Cátedras evaluadoras | Evaluador académico | Medio | Media | Neutral | Neutral | Partidario | Informes y demostraciones | PM | Por hito |
| **SI-09** | Proveedores / servicios cloud | Proveedor | Bajo | Media | Neutral | Neutral | Partidario | SLA y evaluación ex post | Infra | Según contrato |

> **Corrección clave:** estudiantes, docentes y GAB no pueden figurar como “Baja” o “Media” sin justificación. La clasificación anterior confundía **influencia** con **importancia para el éxito**. El registro separa ambos conceptos.

---

### 11.6. Registro de riesgos, apetito y informe

#### 11.6.1. Declaración de apetito de riesgo

> BioSignal tiene **apetito bajo** frente a riesgos de privacidad, seguridad y cumplimiento legal; **apetito medio** frente a riesgos técnicos y de cronograma; y **apetito alto** frente a oportunidades de innovación académica. Ningún riesgo con nivel **crítico (15–25)** puede quedar residual al cierre. Los riesgos altos (10–14) requieren respuesta activa y seguimiento quincenal.

**Escalas:**

| Probabilidad | Criterio | Impacto | Criterio |
| :---: | :--- | :---: | :--- |
| 1 | Muy improbable (< 10 %) | 1 | Insignificante: sin efecto en alcance, plazo, costo o calidad |
| 2 | Poco probable (10–30 %) | 2 | Menor: ajuste interno menor |
| 3 | Posible (30–50 %) | 3 | Moderado: desvío controlable |
| 4 | Probable (50–70 %) | 4 | Mayor: afecta un hito o requisito crítico |
| 5 | Muy probable (> 70 %) | 5 | Catastrófico: incumplimiento legal, pérdida de datos o cancelación |

#### 11.6.2. Registro de riesgos propuesto

| ID | Riesgo (causa → evento → efecto) | Categoría | P | I | P×I | Dueño | Respuesta | Disparador | Residual |
| :--- | :--- | :--- | :---: | :---: | :---: | :--- | :--- | :--- | :---: |
| **R-01** | GAB no entrega EDF a tiempo → no hay dataset → retraso de ingesta y UAT | Datos | 4 | 4 | 16 | PM | Mitigar: usar PhysioNet/sintéticos desde la semana 1; acordar fecha con GAB | Sin 10 EDF al 15/12/2026 | 8 |
| **R-02** | Señales extensas → el navegador se congela → no se cumple FPS/LCP | Técnico | 3 | 5 | 15 | Frontend + QA | Mitigar: LTTB, chunking, WebGL, perfilado temprano | FPS < 30 en prototipo | 6 |
| **R-03** | Exámenes/ausencias → baja disponibilidad → retraso | Equipo | 4 | 3 | 12 | PM | Mitigar: buffer, cross-training, suplencia | Ausencia > 20 % en una iteración | 6 |
| **R-04** | TIC no entrega servidor/dominio → no hay despliegue | Infraestructura | 3 | 4 | 12 | Infra | Mitigar: fallback Vercel/Render; acuerdo formal | Sin credenciales al 30/11/2026 | 6 |
| **R-05** | Convenio/consentimiento incompleto → no se pueden usar datos | Legal | 2 | 5 | 10 | PM + Legal | Evitar: dictamen antes de la carga; datos sintéticos como respaldo | Sin dictamen al 15/12/2026 | 5 |
| **R-06** | Nuevas funciones sin RFC → scope creep → retrabajo | Alcance | 4 | 4 | 16 | PM + CCB | Mitigar: change control obligatorio; MoSCoW | Solicitud sin RFC | 8 |
| **R-07** | Dependencia de una persona → pérdida de conocimiento | Equipo | 3 | 4 | 12 | PM | Mitigar: matriz de suplencia y documentación | Salida o ausencia prolongada | 6 |
| **R-08** | Incompatibilidad cross-browser → fallas en Safari/Firefox | Técnico | 3 | 3 | 9 | Frontend + QA | Mitigar: pruebas semanales en 4 navegadores | Falla reproducible | 4 |
| **R-09** | Vulnerabilidad o fuga → incidente de seguridad | Seguridad | 2 | 5 | 10 | Backend + Infra | Mitigar: OWASP ASVS, SAST, revisión de dependencias | Hallazgo crítico | 5 |
| **R-10** | Baja adopción docente → no se usa el sistema | Beneficios | 3 | 4 | 12 | Sponsor + PM | Mitigar: pilotos tempranos, guías de TP, campeones | < 50 % de uso en piloto | 6 |
| **R-11** | Compresión del cronograma → se saltan pruebas | Cronograma | 4 | 4 | 16 | PM | Mitigar: MVP, buffers, go/no-go | SPI < 0,9 | 8 |
| **R-12** | Reidentificación por combinación de metadatos | Privacidad | 2 | 5 | 10 | Legal + QA | Mitigar: generalización, k-anonimato, auditoría | Metadata con combinación única | 4 |

**Oportunidades:**

| ID | Oportunidad | Dueño | Respuesta | Beneficio |
| :--- | :--- | :--- | :--- | :--- |
| **O-01** | Reutilizar datasets abiertos (PhysioNet) para pruebas | GAB | Explotar | Acelera la ingesta y reduce dependencia |
| **O-02** | Usar stack open source y capas gratuitas | Infra | Explotar | Mantiene el $0 de caja |
| **O-03** | Publicar el caso como experiencia académica | PM | Mejorar | Visibilidad institucional y aprendizaje |

#### 11.6.3. Informe de riesgos (plantilla)

```
Informe de riesgos — BioSignal
Período: __________    Fecha: __________    Autor: __________
1. Resumen ejecutivo (3 bullets)
2. Riesgos críticos/altos abiertos (ID, nivel, dueño, respuesta, fecha)
3. Riesgos materializados en el período (impacto real)
4. Cambios de nivel (subas/bajas) y causa
5. Reservas de contingencia usadas y saldo
6. Oportunidades en seguimiento
7. Decisiones requeridas al sponsor/CCB
8. Próxima revisión: __________
```

**Cadencia:** revisión semanal en la reunión de equipo; revisión quincenal con el sponsor; revisión obligatoria en cada hito.

---

### 11.7. Equipo, roles y RACI

#### 11.7.1. Mapa de roles a personas

| Rol PMBOK 7 / proyecto | Persona | Suplente | Observación |
| :--- | :--- | :--- | :--- |
| Director del Proyecto (PM) | Mateo Astudillo | Ignacio Ávila | Autoridad de planificación y escalamiento |
| Asistente del PM (APM) | Ignacio Ávila | Mateo Astudillo | Documentación, comunicaciones y seguimiento |
| Backend / QA | Germán Herrera | Martín Mosainer | **Conflicto potencial:** si es autor, no puede aprobar su propio QA |
| Full-stack / Soporte | Martín Mosainer | Germán Herrera | Integración, RBAC, soporte |
| Infraestructura / DBA / DevOps | Eber Chiecher | Martín Mosainer | Servidores, PostgreSQL, CI/CD, TLS |
| Frontend / UX-UI | Rocío Pereyra | Martín Mosainer | Visualizador, accesibilidad, responsive |
| Patrocinador | Alejandro Rosas (EICA) | Dirección TIC | Aprueba líneas base y cierre |
| Legal / ético | Asesoría UNViMe | PM | Dictamen Ley 25.326 y convenios |

> **Decisión:** no se crean tres roles separados (UX/UI, DBA, DevOps) para seis personas. Esas responsabilidades se asignan a Rocío (UX/UI), Eber (DBA/DevOps) y Martín (suplencia). La matriz de competencias se conserva como anexo de capacidades, no como RACI.

#### 11.7.2. RACI por entregable

**R** = Responsable de ejecutar · **A** = Aprueba · **C** = Consultado · **I** = Informado.

| Entregable / actividad | PM | APM | Backend/QA | Full-stack | Infra/DBA/DevOps | Frontend/UX | Sponsor |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Acta de Constitución | R | C | I | I | I | I | **A** |
| ERS + RTM | **A** | R | C | C | C | C | I |
| EDT + Diccionario | **A** | R | C | C | C | C | I |
| Arquitectura y stack | I | I | R | C | **A** | C | I |
| Autenticación / RBAC | I | I | R | **A** | C | C | I |
| Ingesta / sanitización | I | I | **A** | C | R | I | I |
| Visualizador | I | I | C | R | I | **A** | I |
| Exportación EDF | I | I | **A** | R | C | I | I |
| QA y aceptación técnica | **A** | C | R | C | C | C | I |
| Despliegue | C | I | R | I | **A** | I | I |
| Cierre | R | C | C | I | I | I | **A** |
| Adopción académica | R | R | I | I | I | I | **A** |

> **Regla de independencia:** cuando Germán Herrera sea autor de código backend, la revisión de QA la realizará Martín Mosainer o Eber Chiecher, y la aprobación final de QA la firmará el PM. Ninguna persona aprueba su propio trabajo.

#### 11.7.3. Team charter (contenido mínimo)

| Elemento | Acuerdo propuesto |
| :--- | :--- |
| Propósito | Entregar BioSignal en el plazo y con la calidad acordados |
| Valores | Transparencia, respeto, aprendizaje, cuidado de datos |
| Disponibilidad | 4 h/semana por persona en promedio; martes y jueves de 18:00 a 20:00 para sincronización |
| Comunicación | Discord para bloqueos; GitHub Issues para tareas; correo para el sponsor |
| Reuniones | Daily async (chat), weekly (60 min), review/retro biweekly |
| Conflictos | Se resuelven en 48 h; si persisten, escala al PM; luego al sponsor |
| Calidad | Nadie mergea sin revisión; Definition of Done acordada |
| Reconocimiento | Retrospectiva y reconocimiento público en la reunión semanal |
| Cambios | Solo por RFC aprobada por el CCB |

---

### 11.8. Plan de comunicaciones corregido

| Tipo | Información | Emisor | Receptor | Formato | Canal | Frecuencia | Feedback | Dueño |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Externa | Inicio y Acta | PM | Sponsor, EICA, cátedras | Acta + reunión | Correo + presencial/virtual | Una vez | Firma | PM |
| Externa | Estado del proyecto | PM | Sponsor | Informe ejecutivo + reunión | Correo + reunión | Mensual + hito | Minuta y decisiones | PM |
| Externa | Requisitos y alcance | APM | GAB, TIC, docentes | ERS + RTM | Repositorio + reunión | Por hito | Acta de revisión | APM |
| Externa | Infraestructura | Infra | Dirección TIC | Ticket + checklist | Mesa de ayuda + reunión | Semanal en infra | Confirmación | Infra |
| Externa | Legal y ética | PM | Asesoría legal / comité | Dictamen | Correo formal | Requisitos y auditoría | Dictamen firmado | PM |
| Externa | Cierre | PM | Sponsor, cátedras, usuarios | Acta de cierre | Correo + reunión | Una vez | Firma | PM |
| Interna | Coordinación | PM | Equipo | Reunión + minuta | Discord/virtual | Semanal | Acuerdos | PM |
| Interna | Avance de tareas | Cada integrante | PM/APM | Tablero | GitHub Projects | Continuo | Actualización | APM |
| Interna | Bloqueos | Quien detecta | PM | Mensaje | Discord `#impedimentos` | Inmediato | Respuesta < 24 h | PM |
| Interna | Revisión de código | Revisor | Autor | PR | GitHub | Por PR | Aprobación | QA |
| Interna | Riesgos | QA/PM | Equipo/sponsor | Informe de riesgos | Repositorio | Quincenal | Acciones | PM |
| Interna | Cambios | PM | CCB/equipo | RFC | GitHub/Repositorio | Por cambio | Decisión | PM |
| Interna | Retrospectiva | PM | Equipo | Notas | Repositorio | Biweekly | Acciones | APM |

**Escalamiento:**

| Situación | Plazo | Instancia |
| :--- | :--- | :--- |
| Bloqueo técnico | 24 h | PM |
| Bloqueo que afecta un hito | 48 h | Sponsor |
| Cambio de alcance, plazo o costo | 5 días | CCB + Sponsor |
| Incidente de seguridad o privacidad | Inmediato | PM + Legal + TIC |

**Confidencialidad:** no se envían datos de pacientes por chat ni correo; se usan IDs anonimizados. Los documentos se clasifican como `público`, `interno` o `restringido`. Los logs de auditoría se conservan durante el plazo que defina la UNViMe (se recomienda un mínimo de 5 años).

---

### 11.9. Medición, beneficios, complejidad y MVP

#### 11.9.1. Plan de medición (KPI)

| Dimensión | KPI | Fórmula | Meta | Fuente | Frecuencia | Dueño |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Cronograma | SPI | EV / PV | ≥ 0,9 | Gantt + horas | Semanal | PM |
| Cronograma | Hitos a tiempo | Hitos cumplidos / hitos planificados | 100 % | Acta de hito | Por hito | PM |
| Costo | CPI | EV / AC | ≥ 0,9 | Presupuesto + horas | Semanal | PM |
| Costo | Desembolso | Caja real | $0 USD | Registro de caja | Mensual | PM |
| Alcance | Cobertura de requisitos | RF verificados / RF totales | 100 % | RTM | Por hito | QA |
| Calidad | Defectos críticos | Abiertos al cierre | 0 | GitHub Issues | Semanal | QA |
| Calidad | Cobertura | Líneas cubiertas / líneas críticas | > 80 % | CI | Por PR | QA |
| Desempeño | LCP/TTIS | Mediana y p95 | ≤ 2,5 s | Lighthouse/PerformanceObserver | Por release | QA |
| Desempeño | FPS | Frames / segundo | ≥ 30 | DevTools | Por release | Frontend |
| Desempeño | Concurrencia | Usuarios simultáneos | 100 sin 5xx | k6/JMeter | Por release | QA |
| Ingesta | Tiempo de procesamiento | Mediana y p95 | ≤ 30 s/< 50 MB | Benchmark | Por release | Backend |
| Riesgo | Riesgos con dueño | Riesgos con dueño / total | 100 % | Registro | Quincenal | PM |
| Riesgo | Riesgo crítico residual | Nivel 15–25 al cierre | 0 | Registro | Por hito | PM |
| Interesados | Involucramiento | Nivel actual vs. deseado | ≥ 80 % en objetivo | Registro | Por hito | APM |
| Beneficios | Adopción | Cátedras / usuarios | 2 / 50 | Guías + analítica | Post-cierre | Sponsor |

#### 11.9.2. Evaluación de complejidad

| Dimensión | Nivel | Evidencia | Respuesta |
| :--- | :---: | :--- | :--- |
| Técnica | Alta | Parseo binario EDF/EDF+, sanitización, WebGL, 100 usuarios, 32 canales | Spikes, prototipos, pruebas tempranas, revisión de pares |
| Organizacional | Alta | UNViMe, EICA, ECS, EM, GAB, TIC, asesoría legal | Registro de interesados, gobernanza y acuerdos formales |
| Ambigüedad | Media | Requisitos iniciales, disponibilidad de datos, adopción | ERS con criterios medibles, UAT temprana, datos sintéticos |
| Volatilidad | Media/Alta | Calendario académico, exámenes, disponibilidad del equipo | Buffers, MVP, suplencia y revisión semanal |

#### 11.9.3. MVP MoSCoW

| Prioridad | Alcance | Decisión |
| :--- | :--- | :--- |
| **Must** | EP-01 autenticación/RBAC, EP-02 ingesta/sanitización, EP-03 visualizador, EP-05 exportación, EP-06 dataset, despliegue | Entra en la línea base A |
| **Should** | EP-04 acceso público, edición de metadatos, búsqueda/filtros, auditoría | Entra si el cronograma lo permite |
| **Could** | Registro/recuperación de credenciales, anotaciones, CSV/MATLAB, CIE-10 | No entra sin RFC |
| **Won't** | Diagnóstico por IA, captura en tiempo real, apps nativas, manuales/capacitación, soporte post-cierre | Fuera de alcance |

#### 11.9.4. Cálculo del esfuerzo y costo ya estimados

El diccionario solo tiene estimación por actividad en **ocho paquetes** (1.1.1–1.1.5 y 1.3.2.1–1.3.2.3). El resto de los paquetes no permite calcular horas ni costo. Sobre esa base:

| Grupo | Paquetes | Horas base | Costo base (ARS) | Costo total del diccionario (ARS)* |
| :--- | :--- | ---: | ---: | ---: |
| Gestión del proyecto | 1.1.1–1.1.5 | 49 h | 490.000 | 900.000 |
| Gestión de señales | 1.3.2.1–1.3.2.3 | 231 h | 2.310.000 | 3.200.000 |
| **Total conocido** | **8 paquetes** | **280 h** | **2.800.000** | **4.100.000** |

\* Incluye el costo base más la gestión del riesgo y la contingencia declaradas en cada actividad. Se toma $10.000/h y se asume que el símbolo `$` del diccionario corresponde a ARS, porque la moneda no está declarada.

**Escenario con informes recurrentes:** el paquete 1.1.4 cuesta 6 h por informe y declara emisión quincenal entre las semanas 2 y 24 (12 informes). Si se presupuestan los 12 informes en lugar de uno solo:

| Escenario | Horas conocidas | Costo base (ARS) | Costo total (ARS) |
| :--- | ---: | ---: | ---: |
| Un solo informe (como está el diccionario) | 280 h | 2.800.000 | 4.100.000 |
| 12 informes quincenales | 346 h | 3.460.000 | 5.365.000 |

**Interpretación:** el esfuerzo conocido ya consume entre **78 % y 108 %** del límite de 260–360 h; con los informes recurrentes, entre **96 % y 133 %**. Ninguno de los dos escenarios incluye 1.2.1, 1.2.2, 1.2.3, 1.3.1.1–1.3.1.4, 1.3.3.1–1.3.3.3, 1.4.1–1.4.2 ni 1.5. Por lo tanto, el proyecto **no cabe** en el límite declarado sin reducir alcance (MVP), reestimar los paquetes faltantes y ampliar plazo o capacidad. Este cálculo sustenta el hallazgo **H-14**.

---

### 11.10. Registro de tailoring (plantilla)

| Elemento | Decisión | Justificación | Responsable | Fecha | Aprobado por |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Principios PMBOK 7 | Adoptar los 12, con énfasis en valor, stewardship, calidad y riesgo | Proyecto académico con datos sensibles | PM | | Sponsor |
| Dominios | Adoptar los 8; profundizar en interesados, equipo, planificación, medición e incertidumbre | Brechas identificadas | PM | | Sponsor |
| Ciclo de vida | Híbrido: compuertas por hito + iteraciones de 2 semanas | Incertidumbre técnica y plazo fijo | PM | | Sponsor |
| Artefactos | Set mínimo de 12 documentos; fusionar recursos, issues y calendario | Evitar burocracia en equipo pequeño | PM | | Sponsor |
| Calidad | ISO/IEC 25010 + ISO/IEC 12207 + ISO 9001/90003 | Estándares ya usados en borradores | QA | | PM |
| Riesgos | Matriz 5×5 + registro + informe quincenal | Necesidad de decisiones tempranas | PM | | Sponsor |
| Adquisiciones | Make-or-buy; priorizar open source y en especie | Restricción $0 de caja | PM | | Sponsor |
| Reporte | Mensual al sponsor + semanal interno | Equilibrio entre control y carga | PM | | Sponsor |
| Herramientas | GitHub, GitHub Projects, Discord, Obsidian/Quartz | Stack ya disponible | APM | | PM |

---

### 11.11. Plan SCM y control de cambios consolidado

#### 11.11.1. Correcciones al texto actual

| Punto | Texto actual | Corrección |
| :--- | :--- | :--- |
| Ruta documental | `/workspace/knowledge/` | `content/` del repositorio y URL de GitHub Pages/Quartz. |
| Ramas | `main/develop` en el plan; `main/test/dev` en el borrador | Un solo modelo: `main`, `develop`, `feature/*`, `bugfix/*`; `main` y `develop` protegidas. |
| Revisores | “Herrera o Mosainer” | Pool: Germán, Martín, Eber; si el autor es uno de ellos, revisa otro; QA final lo firma el PM. |
| Herramienta | “(alguna herramienta)” | GitHub Projects + issues `BIOSIG-xx`. |
| CI-DOC | Incluye manuales | Los manuales están fuera de alcance; quitar “manuales” o agregarlos al alcance por RFC. |
| CI-UI | Figma | Mantener solo si los prototipos son entregables; si no, es un insumo interno. |
| Stack | Node.js/Python/React | Fijar Next.js/React + FastAPI/Python + PostgreSQL en un ADR. |
| Change Log | RFC previas al Acta | Rebaselinar fechas y versiones; crear RFC-004…010. |

#### 11.11.2. Gobernanza del CCB

| Elemento | Definición |
| :--- | :--- |
| Miembros | PM (preside), APM, QA, Infra, Sponsor (solo para alcance, plazo, costo o beneficios) |
| Quórum | 3 miembros, incluido el PM |
| Decisiones | Aprobado / Rechazado / Aplazado / Aprobado con condiciones |
| Plazo | 48 h hábiles para cambios normales; 24 h para emergencias |
| Emergencia | PM + QA + Infra pueden aprobar; se ratifica en 48 h |
| Impacto | Alcance, cronograma, costo, calidad, riesgo, beneficios, interesados y legal |
| Registro | RFC + Change Log + versión resultante |

#### 11.11.3. Registro de RFC propuesto

| RFC | Cambio | Hallazgos | Artefactos afectados | Dueño | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **RFC-004** | Rebaselinar Acta: nombre, objetivos, fechas, presupuesto, entregables | H-01, H-02, H-03, H-08, H-10, H-13, H-33 | `project-charter.md` | PM | Propuesto |
| **RFC-005** | Alinear Alcance, ERS, EDT y Diccionario; completar 1.2.3; corregir métricas | H-09, H-11, H-12, H-14, H-15, H-16, H-17, H-18, H-23, H-30, H-31, H-32 | Alcance, ERS, EDT, Diccionario, RTM | PM + QA | Propuesto |
| **RFC-006** | Crear PMP, tailoring, caso de negocio, beneficios y medición | H-04, H-05, H-06, H-07, H-37, H-40, H-42 | Nuevos documentos | PM | Propuesto |
| **RFC-007** | Registro de interesados y comunicaciones | H-19, H-20, H-29 | Interesados, comunicaciones | APM | Propuesto |
| **RFC-008** | Integrar calidad, riesgos, supuestos y RNF de privacidad/seguridad | H-21, H-22, H-36, H-41 | Calidad, riesgos, ERS | QA + PM | Propuesto |
| **RFC-009** | RACI, team charter y asignación de roles | H-27, H-28 | Responsabilidades, team charter | PM | Propuesto |
| **RFC-010** | SCM, índice, transición, adquisiciones y control documental | H-24, H-25, H-26, H-34, H-35, H-38, H-39 | SCM, índice, transición, adquisiciones | PM + APM | Propuesto |

#### 11.11.4. Plantilla de Change Log

| ID RFC | Fecha | Solicitante | Elemento de configuración | Descripción | Impacto | Revisor | Dictamen | Versión resultante | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| RFC-004 | | | CI-DOC-01 Acta | | | | | v1.0 | Propuesto |
| RFC-005 | | | CI-DOC-02/03/04/05 | | | | | v2.0 | Propuesto |

#### 11.11.5. Versionado documental

| Tipo de cambio | Versión | Ejemplo |
| :--- | :--- | :--- |
| Borrador | v0.x | v0.1, v0.2 |
| Aprobado inicial | v1.0 | Acta aprobada |
| Cambio menor (forma) | v1.x | Corrección de títulos |
| Cambio mayor (alcance, línea base) | v2.0 | Nuevo alcance aprobado por RFC |

> Cada documento debe incluir un historial con versión, fecha, autor, descripción y aprobador.

---

## 12. Plan de implementación de las correcciones

| Fase | Fechas | Objetivo | Entregables | Responsable |
| :--- | :--- | :--- | :--- | :--- |
| **Fase 0 — Congelamiento** | 20–23/10/2026 | Detener cambios informales y preparar el rebaseline | Glosario, inventario, registro de decisiones | PM + APM |
| **Fase 1 — P0** | 26–30/10/2026 | Corregir lo que bloquea la aprobación del Acta | Acta v1.0, PMP, tailoring, beneficios, EDT alineado, RACI, riesgos | PM + equipo |
| **Fase 2 — P1** | 02–13/11/2026 | Corregir alcance, requisitos, calidad, interesados y SCM | ERS v2.0, RTM v2.0, plan de calidad, comunicaciones, SCM | PM + QA + APM |
| **Fase 3 — P2** | 16–27/11/2026 | Completar transición, adquisiciones, índice y control documental | Plan de transición, adquisiciones, índice v2.0 | PM + APM |
| **Fase 4 — Verificación** | 30/11/2026 | Validar que no queden contradicciones | Checklist de la Sección 13 completo | APM + QA |
| **Fase 5 — Aprobación** | 04/12/2026 | Aprobar la línea base v1.0 | Acta de aprobación y publicación | Sponsor + PM |

> Si se aprueba la Opción A, el Acta se firma el **02/11/2026** y las fases 2–5 se ejecutan en paralelo con el inicio de la ejecución. Las líneas base de alcance y requisitos se congelan el **13/11/2026**.

---

## 13. Criterios de verificación

| # | Criterio | Evidencia | Estado |
| :---: | :--- | :--- | :---: |
| 1 | Nombre canónico “BioSignal” en todos los documentos; sin variantes | `grep -R -e "BioSignalsBank" -e "BioSignals"` sin resultados en docs nuevos | ☐ |
| 2 | Una sola línea base de fechas; hitos alineados con EDT | Gantt y Acta v1.0 | ☐ |
| 3 | Objetivos con métrica, fecha y verificación | Tabla O-01…O-07 | ☐ |
| 4 | Aceptación del proyecto separada de beneficios | Alcance §4 + registro de beneficios | ☐ |
| 5 | Todo RF/RNF/RT/RP trazado a EDT, prueba y aceptación | RTM v2.0 sin huérfanos | ☐ |
| 6 | Todo paquete del EDT con los 8 campos mínimos; 1.2.3 completo | Diccionario v2.0 | ☐ |
| 7 | Métricas del EDT iguales a ERS/Alcance (30 FPS, 50 MB/30 s, solo EDF) | Revisión cruzada | ☐ |
| 8 | Esfuerzo, costo y capacidad conciliados; PERT correcto | Presupuesto + Gantt + hoja de cálculo | ☐ |
| 9 | RACI con un solo “A” por fila; QA independiente | RACI v1.0 | ☐ |
| 10 | Registro de interesados con nivel actual y deseado | Registro SI-01…SI-09 | ☐ |
| 11 | Comunicaciones con escalamiento, feedback y confidencialidad | Plan v2.0 | ☐ |
| 12 | Registro de riesgos con dueño, disparador, respuesta y residual | Registro R-01…R-12 | ☐ |
| 13 | Calidad integrada, indexada y alineada a PMBOK 7 | Documentos 01–04 + plan | ☐ |
| 14 | Change Log y RFC vinculados; versiones coherentes | Change Log + RFC-004…010 | ☐ |
| 15 | Plan de medición, KPI y beneficios con dueño | Plan de medición + B-01…B-06 | ☐ |
| 16 | Plan de transición y handover | Checklist de operación | ☐ |
| 17 | Registro de tailoring aprobado | Sección 11.10 | ☐ |
| 18 | Índice y publicación sin enlaces rotos | `index.md` v2.0 + build Quartz | ☐ |
| 19 | Glosario y corrección ortográfica | Checklist de estilo | ☐ |
| 20 | Firma del sponsor y del PM | Acta de aprobación | ☐ |

---

## Anexo A. Trazabilidad de correcciones → RFC

| RFC | Hallazgos | Documentos | Responsable | Estado |
| :--- | :--- | :--- | :--- | :--- |
| RFC-004 | H-01, H-02, H-03, H-08, H-10, H-13, H-33 | Acta | PM | Propuesto |
| RFC-005 | H-09, H-11, H-12, H-14, H-15, H-16, H-17, H-18, H-23, H-30, H-31, H-32 | Alcance, ERS, EDT, Diccionario, RTM | PM + QA | Propuesto |
| RFC-006 | H-04, H-05, H-06, H-07, H-37, H-40, H-42 | PMP, tailoring, beneficios, medición | PM | Propuesto |
| RFC-007 | H-19, H-20, H-29 | Interesados, comunicaciones | APM | Propuesto |
| RFC-008 | H-21, H-22, H-36, H-41 | Calidad, riesgos, ERS | QA + PM | Propuesto |
| RFC-009 | H-27, H-28 | RACI, team charter | PM | Propuesto |
| RFC-010 | H-24, H-25, H-26, H-34, H-35, H-38, H-39 | SCM, índice, transición, adquisiciones | PM + APM | Propuesto |

---

## Anexo B. Plantillas mínimas

### B.1. Plantilla de RFC

```
RFC-XXX
Proyecto: BioSignal
Solicitante:
Fecha:
Elemento de configuración afectado: CI-DOC / CI-CODE / CI-DATA / CI-UI / CI-QUALITY / CI-RISK / CI-BENEFITS
Versión actual:
Descripción del cambio:
Justificación (problema/oportunidad):
Impacto:
  - Alcance:
  - Cronograma:
  - Costo:
  - Calidad:
  - Riesgo:
  - Beneficios:
  - Interesados:
  - Legal/privacidad:
Alternativas evaluadas:
Recomendación:
Dictamen CCB: Aprobado / Rechazado / Aplazado / Aprobado con condiciones
Condiciones:
Versión resultante:
Aprobado por:
Fecha de implementación:
Evidencia de verificación:
```

### B.2. Plantilla de lecciones aprendidas

```
Lección aprendida — BioSignal
Fecha:
Hito/iteración:
Situación:
¿Qué funcionó?
¿Qué no funcionó?
Causa raíz:
Acción de mejora:
Responsable:
Fecha de implementación:
¿Se verificó la eficacia? (Sí/No) — Evidencia:
```

### B.3. Plantilla de aceptación de entregable

```
Acta de aceptación — <EP/EJ>
Proyecto: BioSignal
Entregable:
Versión:
Criterios de aceptación:
Resultado de verificación (Pasa/No pasa):
Evidencia:
Observaciones:
Aceptado por:
  - QA:
  - PM:
  - Sponsor:
Fecha:
```

---

## Anexo C. Referencias

- PMI. *A Guide to the Project Management Body of Knowledge (PMBOK Guide)*, 7.ª edición, 2021.
- PMI. *The Standard for Project Management*, 2021.
- ISO/IEC 25010. *Sistemas y software — Modelos de calidad del producto*.
- ISO/IEC/IEEE 29148. *Ingeniería de sistemas y software — Procesos del ciclo de vida — Ingeniería de requisitos*.
- ISO/IEC 12207. *Procesos del ciclo de vida del software*.
- ISO 9001 / ISO/IEC 90003. *Gestión de la calidad — Aplicación a software*.
- Ley Nacional N.º 25.326 de Protección de los Datos Personales (Argentina).
- Especificación EDF/EDF+ (Kemp et al.).
- W3C. *Web Content Accessibility Guidelines (WCAG) 2.1*.
- OWASP. *Application Security Verification Standard (ASVS)*.
- Google. *Core Web Vitals*.

---

## Anexo D. Decisiones que requieren al sponsor

| # | Decisión | Opciones | Impacto | Responsable |
| :---: | :--- | :--- | :--- | :--- |
| 1 | Nombre canónico | BioSignal / BioSignalsBank | Imagen y trazabilidad | Sponsor |
| 2 | Línea base | Opción A (15 semanas, MVP) / Opción B (24 semanas) | Alcance, plazo, esfuerzo | Sponsor + PM |
| 3 | Alcance del MVP | Must/Should/Could/Won't | Entregables y fecha | Sponsor + PM |
| 4 | Presupuesto | $0 de caja / insumos en especie / compra paga | Adquisiciones y legal | Sponsor |
| 5 | Cláusula de publicidad | Eliminar / formalizar por convenio | Ética y propiedad intelectual | Sponsor + Legal |
| 6 | Dueño de beneficios | Sponsor / PM / GAB | Medición post-cierre | Sponsor |
| 7 | Autoridad de aceptación | Sponsor / EICA / TIC | Cierre formal | Sponsor |
| 8 | Soporte post-cierre | Fuera de alcance / convenio de mantenimiento | Operación | Sponsor |

---

> **Fin del documento.** Las correcciones propuestas se consideran completas cuando el checklist de la Sección 13 está al 100 % y la línea base `v1.0` está firmada por el PM y el patrocinador.



