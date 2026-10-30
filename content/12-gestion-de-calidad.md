---
project: BioSignal
version: 1
title: 12. Gestión de Calidad
aliases:
  - Gestión de Calidad
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-10-29
---

# Gestión de la calidad — BioSignal

**Alcance:** proyecto (procesos y entregables de gestión), producto (plataforma EP-01 a EP-06) y servicio (puesta en servicio y transferencia a la UNViMe).

## 1. Enfoque y marco normativo

| Norma                            | Rol en BioSignal                                                   | Dónde se aplica                                   |
| -------------------------------- | ------------------------------------------------------------------ | ------------------------------------------------- |
| **ISO 9001 / ISO 90003**         | Sistema de gestión de la calidad y su interpretación para software | Política, procesos, auditorías, mejora (sección 2)       |
| **ISO/IEC/IEEE 12207 (nivel 1)** | Procesos del ciclo de vida y madurez del proceso                   | Entornos, SCM, CI/CD, verificación (sección 2)           |
| **ISO/IEC 25010**                | Modelo de calidad del producto                                     | Características y métricas del software (sección 3)      |
| **ISO/IEC 20000**                | Gestión del servicio                                               | Puesta en servicio y transferencia operativa (sección 4) |
| **ISO/IEC/IEEE 29148**           | Calidad de requisitos                                              | ERS y revisión documental (sección 2.7)                  |
| **EDF / EDF+**                   | Formato de entrada/salida de señales                               | RF-04 a RF-06, RF-14                              |
| **Ley 25.326**                   | Protección de datos personales                                     | RF-06, RNF-05, RP-03                              |
| **OWASP Top 10 / ASVS**          | Verificación de seguridad web                                      | Pruebas de seguridad                              |
| **WCAG 2.1 AA**                  | Accesibilidad                                                      | RNF-12, interfaz y gráficos                       |
| **Core Web Vitals**              | Referencia de experiencia web                                      | RNF-02 (TTIS como métrica principal)              |

| Dimensión | Norma principal          | Pregunta que responde                                   | Sección |
| --------- | ------------------------ | ------------------------------------------------------- | ------- |
| Proyecto  | ISO 9001 / 90003 / 12207 | ¿El proceso es repetible, trazable y auditable?         | 2       |
| Producto  | ISO/IEC 25010            | ¿El software cumple los atributos de calidad acordados? | 3       |
| Servicio  | ISO/IEC 20000            | ¿Puede operarse, monitorearse y transferirse?           | 4       |

## 2. Calidad del proyecto (ISO 9001 / 90003 / 12207)

### 2.1 Política de calidad

El equipo de BioSignal se compromete a entregar a la UNViMe una plataforma **segura, confiable, rápida y verificable**, que proteja de forma irreversible la privacidad de los pacientes (Ley 25.326), cumpla los criterios de aceptación antes del **15/02/2027** y sea construida con procesos repetibles, trazables y auditables.

### 2.2 Objetivos medibles

| ID    | Objetivo                      | Meta                                                                        | Origen                     |
| ----- | ----------------------------- | --------------------------------------------------------------------------- | -------------------------- |
| OC-01 | Privacidad                    | 0 % de datos identificatorios residuales en el 100 % de los EDF persistidos | RF-06, RNF-05              |
| OC-02 | Defectos críticos/bloqueantes | 0 abiertos al cierre de la fase de QA                                       | Criterios de aceptación del alcance |
| OC-03 | Desempeño del visualizador    | TTIS ≤ 2,5 s (≥ 10 Mbps) y ≥ 30 FPS                                         | RNF-02, RNF-03             |
| OC-04 | Concurrencia                  | 100 usuarios simultáneos sin errores 5xx                                    | RNF-01                     |
| OC-05 | Ingesta                       | ≤ 30 s para EDF < 50 MB                                                     | RNF-04                     |
| OC-06 | Seguridad en tránsito         | TLS 1.3 y calificación A (SSL Labs / testssl)                               | RNF-06                     |
| OC-07 | Mantenibilidad                | Cobertura > 80 % en lógica crítica; 0 fallas                                | RNF-14                     |
| OC-08 | Compatibilidad                | 100 % de la matriz cross-browser                                            | RNF-07                     |
| OC-09 | Usabilidad                    | Tarea "buscar–abrir–configurar" < 5 min                                     | RNF-09                     |
| OC-10 | Cumplimiento de proceso       | 100 % de PR con revisión cruzada y 100 % de cambios en el Change Log        | Plan SCM                   |

### 2.3 Procesos del SGC (adaptación de ISO 90003)

| Cláusula             | Cómo se aplica en BioSignal                                                                    | Evidencia                                        | Brecha / acción                                                         |
| -------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------- |
| **4. Contexto**      | Interesados, marco legal (Ley 25.326), infraestructura UNViMe y riesgos externos identificados | Acta, registro de interesados, matriz de riesgos | Sin brecha crítica                                                      |
| **5. Liderazgo**     | El PM y los líderes técnicos asumen la calidad; QA tiene autoridad de veto técnico             | Este plan, RACI, actas                           | Formalizar la política de seguridad y codificación en una guía única    |
| **6. Planificación** | Enfoque basado en riesgos: deuda técnica, seguridad, integración, plazos y rotación            | Matriz de riesgos, RQ-01 a RQ-07                 | Mantener revisión de riesgos por hito                                   |
| **7. Soporte**       | Entornos dev/staging/prod, CI/CD, repositorios, competencias y documentación controlada        | Plan SCM, matriz de competencias, CI             | Sin manuales de usuario (excluido del alcance)                          |
| **8. Operación**     | ERS, diseño, desarrollo, control de releases y salidas no conformes                            | ERS, EDT, Change Log, sección 3.5                       | Documentar el diseño de arquitectura y el flujo de salidas no conformes |
| **9. Evaluación**    | Pruebas, revisión de código, métricas, UAT y auditorías internas                               | Informes IC-01 a IC-07                           | Incorporar encuesta de satisfacción (SUS) y auditoría interna por hito  |
| **10. Mejora**       | No conformidades, causa raíz y actualización del plan                                          | Registro IC-06, lecciones aprendidas             | Aprobar el plan de mejora continua de la sección 6                                |

### 2.4 Roles y responsabilidades

| Rol                              | Integrante                         | Responsabilidad de calidad                                                             |
| -------------------------------- | ---------------------------------- | -------------------------------------------------------------------------------------- |
| Director del Proyecto / CCB      | Mateo T. Astudillo                 | Aprueba el plan, las líneas base, los cambios y la liberación a producción             |
| Asistente del PM / Process Owner | Ignacio N. Ávila Gelbes            | Mantiene el plan, el registro de calidad y el Change Log; coordina auditorías          |
| Líder de Código y QA             | Germán E. Herrera                  | Plan de pruebas, revisión de PR, aprobación de entregables y Reporte Consolidado de QA |
| Líder de Infraestructura y BD    | Eber B. Chiecher                   | Migraciones up/down, backups, TLS, CI/CD y monitoreo                                   |
| Líder Frontend y UI/UX           | Rocío Pereyra / Martín D. Mosainer | Visualizador, usabilidad, accesibilidad, rendimiento en cliente                        |
| Revisor Legal / Normativo        | Equipo PM / Asesoría UNViMe        | Dictamen de cumplimiento de la Ley 25.326                                              |
| Patrocinador / UNViMe            | Alejandro Rosas / Dirección TIC    | Aceptación formal y provisión de infraestructura (RP-01)                               |

### 2.5 Aseguramiento de la calidad (preventivo)

| Actividad                                            | Frecuencia       | Responsable        | Evidencia               |
| ---------------------------------------------------- | ---------------- | ------------------ | ----------------------- |
| Revisión cruzada de PR                               | Cada PR          | Herrera / Mosainer | Aprobación en GitHub    |
| Pipeline CI (lint, build, tests, SAST, dependencias) | Cada push/PR     | Chiecher           | Log de CI               |
| Revisión por pares de documentos                     | Por documento    | Process Owner      | Acta de revisión        |
| Auditoría de configuración                           | Fin de cada hito | APM + QA           | Informe IC-01           |
| Auditoría de proceso                                 | Hitos 3, 5 y 6   | PM + QA            | Informe IC-01           |
| Revisión de migraciones DDL                          | Cada migración   | Chiecher           | Script up/down aprobado |
| Retrospectiva y lecciones aprendidas                 | Fin de fase      | PM                 | Registro de lecciones   |

### 2.6 Métricas del proceso (ISO 9001 / 12207)

| ID     | Proceso                    | Métrica                                         | Umbral                |
| ------ | -------------------------- | ----------------------------------------------- | --------------------- |
| MPR-01 | Control de versiones       | PR aprobadas por revisor distinto del autor     | 100 %                 |
| MPR-02 | Control de versiones       | Commits directos a `main`/`develop`             | 0                     |
| MPR-03 | Gestión de cambios         | Cambios con RFC en el Change Log                | 100 %                 |
| MPR-04 | Integración continua       | Builds de `develop` en verde                    | ≥ 90 %                |
| MPR-05 | Verificación               | Eficacia de remoción de defectos (DRE)          | ≥ 95 %                |
| MPR-06 | Verificación               | Defectos escapados a UAT/producción             | 0 críticos            |
| MPR-07 | Verificación               | Reapertura de defectos                          | ≤ 10 %                |
| MPR-08 | Gestión del proyecto       | SPI = EV/PV; CPI = EV/AC                        | ≥ 0,9                 |
| MPR-09 | Documentación              | Documentos revisados por pares antes de aprobar | 100 %                 |
| MPR-10 | Requisitos                 | Cobertura de trazabilidad RF/RNF → EDT → prueba | 100 %                 |
| MPR-11 | Auditoría de configuración | Desvíos sin justificar por hito                 | 0                     |
| MPR-12 | Infraestructura            | Ambientes operativos / planificados             | 100 % antes de Fase 3 |

### 2.7 Calidad de requisitos y documentos (ISO/IEC/IEEE 29148)

Todo requisito debe ser **único, atómico, no ambiguo, verificable y con criterio Pasa/No Pasa**. La revisión documental verifica además:

- Encabezado con versión, fecha, autor, aprobador e historial de cambios.
- Versionado correcto (`v0.x` en revisión, `v1.0` aprobado, `v1.x` corrección menor).
- Trazabilidad completa: necesidad → requisito → EDT → prueba.
- Coherencia entre umbrales, fechas, alcance y exclusiones de todos los documentos.
- Revisión legal cuando se tratan datos personales y firma del Director del Proyecto.
- Publicación en el repositorio central como única versión vigente.

### 2.8 Costo de la calidad

| Categoría     | Ejemplos en BioSignal                                                                  |
| ------------- | -------------------------------------------------------------------------------------- |
| Prevención    | Formatos y guías estandarizadas, revisión por pares, CI/CD, definición de métricas     |
| Evaluación    | Pruebas, auditorías, UAT, perfilado de rendimiento                                     |
| Falla interna | Retrabajo por bugs hallados en QA, re-sanitización de archivos                         |
| Falla externa | Defecto en producción durante la Expo Carreras o el inicio del ciclo 2027, fuga de PII |

Se prioriza la inversión en **prevención y evaluación del flujo de ingesta/anonimización** (impacto legal y reputacional) y del **visualizador** (impacto en la adopción curricular).

## 3. Calidad del producto (ISO/IEC 25010)

### 3.1 Modelo y prioridad

Niveles objetivo acordados (ALTA / MEDIA / BAJA). Las características marcadas como **candidatas a certificación** son las que sostienen la propuesta de valor.

| Característica (ISO 25010) | Nivel objetivo                                 | Foco en BioSignal                                      |
| -------------------------- | ---------------------------------------------- | ------------------------------------------------------ |
| Adecuación funcional       | ALTA                                           | Cobertura de RF-01 a RF-14, validación EDF             |
| Eficiencia de desempeño    | MEDIA/ALTA                                     | TTIS, FPS, concurrencia, ingesta                       |
| Compatibilidad             | ALTA (coexistencia) / BAJA (interoperabilidad) | Cross-browser; interoperabilidad acotada a EDF/EDF+    |
| Capacidad de interacción   | **Candidata a certificación**                  | Aprendizaje, operabilidad, accesibilidad               |
| Fiabilidad                 | MEDIA/ALTA                                     | Disponibilidad, tolerancia a fallos, recuperación      |
| Seguridad                  | ALTA                                           | Confidencialidad, integridad, auditoría, autenticidad  |
| Mantenibilidad             | ALTA                                           | Cobertura, modularidad, análisis estático              |
| Flexibilidad               | BAJA                                           | Infraestructura fija; adaptabilidad móvil acotada      |
| Protección (safety)        | MEDIA/BAJA                                     | Uso académico, no diagnóstico; advertencias de alcance |

### 3.2 Métricas clave y umbrales

| ID       | Característica / métrica                        | Umbral                                       | Verificación                     | Req.          |
| -------- | ----------------------------------------------- | -------------------------------------------- | -------------------------------- | ------------- |
| MP-FS-01 | RF implementados y verificados                  | 100 %                                        | Trazabilidad + pruebas           | RF-01…RF-14   |
| MP-FS-02 | Casos de aceptación aprobados                   | 100 % críticos; ≥ 95 % total                 | Playwright / UAT                 | Criterios de aceptación del alcance |
| MP-FS-03 | Aceptación de EDF válidos y rechazo de espurios | 100 %                                        | pytest                           | RF-04         |
| MP-FS-04 | Detección de cabeceras corruptas                | 100 %                                        | pytest con fuzzing               | RF-05         |
| MP-PE-01 | TTIS del primer segmento interactivo            | ≤ 2,5 s (p75)                                | PerformanceObserver / Lighthouse | RNF-02        |
| MP-PE-02 | FPS en paneo/zoom con 32 canales                | ≥ 30 FPS sostenidos                          | DevTools Performance             | RNF-03        |
| MP-PE-03 | Tiempo de ingesta                               | ≤ 30 s para EDF < 50 MB                      | Benchmark (n ≥ 10)               | RNF-04        |
| MP-PE-04 | Usuarios concurrentes                           | 100 sin errores 5xx                          | k6 / JMeter                      | RNF-01        |
| MP-PE-05 | Latencia de API bajo carga                      | media < 3 s; p95 ≤ 5 s                       | k6                               | RNF-01        |
| MP-PE-06 | CPU / RAM del servidor                          | < 80 %                                       | Monitoreo                        | RNF-01        |
| MP-PE-07 | Memoria del navegador (32 canales)              | Sin fuga tras 5 min                          | DevTools Memory                  | RNF-08        |
| MP-CO-01 | Matriz cross-browser                            | 100 %                                        | Playwright + Safari real         | RNF-07        |
| MP-CO-02 | EDF exportado legible por librerías estándar    | 100 %                                        | MNE-Python / pyedflib            | RF-14         |
| MP-US-01 | Time-on-Task "buscar–abrir–configurar"          | < 5 min (media)                              | Prueba con ≥ 5 estudiantes       | RNF-09        |
| MP-US-02 | Tasa de éxito de tarea                          | ≥ 90 %                                       | Prueba de usuario                | RNF-09        |
| MP-US-03 | Contraste y accesibilidad                       | ≥ 4,5:1 texto; ≥ 3:1 gráficos; teclado       | Lighthouse / axe                 | RNF-12        |
| MP-US-04 | Canales por dispositivo                         | ≥ 1024 px: 32; < 768 px: 1–2                 | Demostración responsive          | RNF-08        |
| MP-US-05 | Satisfacción (SUS)                              | ≥ 68                                         | Cuestionario post-UAT            | RI-03, RI-04  |
| MP-RE-01 | Errores críticos bajo estrés                    | < 1 %; 0 % de 5xx con 100 usuarios           | k6                               | RNF-01        |
| MP-RE-02 | Disponibilidad en producción                    | ≥ 99,9 % mensual                             | Uptime monitor                   | RNF-10        |
| MP-RE-03 | Integridad ante fallo de ingesta                | 0 registros inconsistentes                   | pytest de integración            | Pkg 1.3.2.1   |
| MP-RE-04 | Restauración desde backup                       | Éxito 100 %; RTO ≤ 4 h; RPO ≤ 24 h           | Prueba de restore                | RNF-11        |
| MP-RE-05 | Densidad de defectos                            | Tendencia decreciente; 0 críticos al cierre  | Gestor de tareas                 | OC-02         |
| MP-SE-01 | PII residual en EDF persistidos                 | 0 % sobre el 100 % de archivos               | Auditoría binaria                | RF-06, RNF-05 |
| MP-SE-02 | PII en anotaciones EDF+, nombres y logs         | 0 hallazgos                                  | Auditoría + revisión de logs     | RF-06         |
| MP-SE-03 | Cifrado en tránsito                             | TLS 1.3; calificación A                      | testssl.sh / SSL Labs            | RNF-06        |
| MP-SE-04 | Vulnerabilidades OWASP críticas/altas           | 0 abiertas                                   | ZAP + revisión manual            | OC-02         |
| MP-SE-05 | Vulnerabilidades en dependencias                | 0 críticas/altas                             | pip-audit / npm audit            | Pkg 1.3       |
| MP-SE-06 | Elevación de privilegios                        | 100 % bloqueada con HTTP 403                 | pytest / ZAP                     | RF-01         |
| MP-SE-07 | Eventos auditables registrados                  | 100 % (alta, edición, baja, descarga, login) | Inspección de logs               | RNF-13        |
| MP-SE-08 | Expiración de sesión Admin                      | 30 min (± 5 s)                               | pytest / E2E                     | RF-02         |
| MP-SE-09 | Fuerza bruta                                    | Bloqueo al 5.º intento                       | E2E                              | RNF-15        |
| MP-SE-10 | Secretos hardcodeados                           | 0                                            | gitleaks / trufflehog            | Plan SCM, sección 3.3      |
| MP-SE-11 | Integridad de la señal tras editar metadatos    | Hash antes = después                         | Test de hash                     | Pkg 1.3.2.2   |
| MP-MA-01 | Cobertura de pruebas unitarias                  | > 80 % líneas; ≥ 70 % ramas                  | pytest-cov / Jest                | RNF-14        |
| MP-MA-02 | Pruebas unitarias exitosas                      | 100 % (0 fallas)                             | CI                               | RNF-14        |
| MP-MA-03 | Linter y tipado                                 | 0 errores                                    | ruff, ESLint, mypy, tsc          | RNF-14        |
| MP-MA-04 | Complejidad ciclomática                         | ≤ 10 por función                             | radon / ESLint                   | RNF-14        |
| MP-MA-05 | Duplicación de código                           | ≤ 5 %                                        | jscpd                            | —             |
| MP-MA-06 | Migraciones con up/down probado                 | 100 %                                        | Revisión + CI                    | Plan SCM, sección 4.3      |
| MP-PO-01 | Despliegue reproducible                         | Éxito desde cero con un comando              | Docker Compose / CI              | Pkg 1.2.2     |

### 3.3 Verificación por entregable

| Entregable                 | Criterio de calidad                                                          | Método                                            | Responsable    |
| -------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------- | -------------- |
| EP-01 Autenticación/RBAC   | 403 ante acción no permitida; sesión Admin de 30 min; bloqueo al 5.º intento | Unitarias, integración y elevación de privilegios | QA             |
| EP-02 Ingesta/Sanitización | Cabecera válida; 0 PII; ≤ 30 s (< 50 MB); baja lógica auditada               | Benchmark + auditoría binaria al 100 %            | QA + Backend   |
| EP-03 Visualizador         | TTIS ≤ 2,5 s; ≥ 30 FPS; 32 canales / 1–2 en móvil                            | Lighthouse, PerformanceObserver, DevTools         | QA + Frontend  |
| EP-04 Acceso público       | Señal demo y enlace a admisiones sin credenciales                            | Demostración                                      | PM + QA        |
| EP-05 Exportación          | EDF íntegro y anonimizado, sin pérdida de muestras                           | Hash/valores + MNE-Python                         | QA             |
| EP-06 Dataset semilla      | ≥ 30 EDF (≥ 15 ECG, ≥ 15 EEG) catalogados                                    | Inventario en BD de producción                    | DBA / Chiecher |
| EJ-02 ERS + matriz         | Sin ambigüedades; trazabilidad 100 %                                         | Revisión por pares                                | Process Owner  |
| EJ-03 Código               | Convenciones, sin secretos, CI verde                                         | Linter, SAST, revisión de PR                      | Herrera        |
| EJ-04 Reporte QA           | Cero críticos/bloqueantes abiertos                                           | Informe final de QA                               | QA             |
| EJ-05/EJ-06 Actas          | Firmadas ≤ 15/02/2027                                                        | Acta firmada                                      | PM             |

### 3.4 Estrategia de pruebas

| Nivel / tipo             | Alcance                                             | Herramientas (open source)                          |
| ------------------------ | --------------------------------------------------- | --------------------------------------------------- |
| Unitarias                | Parser EDF, cabecera, sanitización, RBAC, sesión    | pytest + pytest-cov; Jest/Vitest                    |
| Integración              | API ↔ BD ↔ almacenamiento; migraciones              | pytest + Testcontainers / Docker Compose            |
| E2E / funcionales        | Login, carga, búsqueda, visualización, descarga     | Playwright                                          |
| Carga y rendimiento      | 100 usuarios; latencia; ingesta                     | k6 o Apache JMeter                                  |
| Rendimiento en cliente   | TTIS, FPS, memoria                                  | Lighthouse, PerformanceObserver, DevTools           |
| Seguridad                | OWASP Top 10, dependencias, TLS                     | OWASP ZAP, pip-audit, npm audit, Bandit, testssl.sh |
| Privacidad / forense EDF | Cabeceras, anotaciones y metadatos                  | Script propio + MNE-Python / pyedflib               |
| Compatibilidad           | Chrome, Edge, Firefox, Safari (2 últimas versiones) | Playwright + Safari real                            |
| Usabilidad               | Time-on-Task < 5 min                                | Prueba con estudiantes                              |
| Aceptación (UAT)         | Validación por docentes y GAB                       | Sesiones con acta                                   |
| Humo                     | Producción tras despliegue                          | Script automatizado + LV-10                         |
| Calidad estática         | Estilo y complejidad                                | ruff/flake8, mypy, ESLint, Prettier                 |

**Datos de prueba:** señales sintéticas y anonimizadas de PhysioNet/PhysioBank, más un EDF "sentinela" con PII sintética en todos los campos para validar la sanitización.

### 3.5 Gestión de defectos

| Severidad                | Definición                                                            | Ejemplo                                 | SLA                        |
| ------------------------ | --------------------------------------------------------------------- | --------------------------------------- | -------------------------- |
| **Crítica / Bloqueante** | Caída, fuga de PII, corrupción de datos, falla general de renderizado | EDF persistido con nombre de paciente   | Inmediata; bloquea el hito |
| **Mayor**                | Funcionalidad principal degradada sin alternativa                     | Paneo por debajo de 30 FPS              | ≤ 3 días hábiles           |
| **Menor**                | Falla con alternativa razonable                                       | Reordenar canales falla en un navegador | Antes del cierre de fase   |
| **Cosmético**            | Sin impacto funcional                                                 | Alineación de un botón                  | Backlog                    |

Ciclo de vida: `Nuevo → Triage (QA) → Asignado → En corrección (bugfix/*) → PR + revisión → En verificación → Cerrado / Reabierto`. Todo defecto registra ID, severidad, versión, pasos de reproducción, evidencia y requisito afectado. Si altera una línea base, se tramita por RFC (Plan SCM).

**Go / No-Go de la fase de QA:** 0 críticos/bloqueantes abiertos; 100 % de unitarias en verde; cobertura > 80 % en lógica crítica; RNF-01 a RNF-15 en umbral; auditoría binaria 100 % limpia; UAT aprobado; recomendación escrita de QA al PM.

## 4. Calidad del servicio (ISO/IEC 20000)

### 4.1 Prácticas y estado

| Práctica                        | Situación actual                                                           | Decisión / acción                                                                                                 |
| ------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Relaciones y acuerdos (SLA)** | Se definen entregables y criterios de aceptación, pero no un SLA formal    | Fijar objetivos operativos (disponibilidad 99,9 %, RTO ≤ 4 h, RPO ≤ 24 h) en el Acta de Despliegue                |
| **Incidencias y problemas**     | No hay proceso formalizado                                                 | Documentar canal de reporte, categorías, prioridades y responsable de recepción antes de la transferencia (LV-11) |
| **Cambios y releases**          | Cubierto por el Plan SCM para software propio; no hay software de terceros | Mantener RFC, staging y rollback; registrar la versión desplegada                                                 |
| **Capacidad y disponibilidad**  | No garantizadas por el equipo; dependen de RP-01                           | Monitoreo de uptime y recursos, alertas y escalamiento al patrocinador                                            |
| **Continuidad y respaldo**      | Backup diario y restore definidos en RNF-11                                | Entregar política de respaldo y procedimiento de restauración probado                                             |
| **Gestión de la configuración** | Versión desplegada = versión aprobada en Change Log                        | Verificación en cada release (MS-05)                                                                              |

### 4.2 Métricas del servicio

| ID    | Práctica           | Métrica                                    | Umbral              |
| ----- | ------------------ | ------------------------------------------ | ------------------- |
| MS-01 | Incidencias        | Canal documentado de reporte disponible    | Sí, verificado      |
| MS-02 | Disponibilidad     | Monitoreo de uptime con alertas            | Sí; objetivo 99,9 % |
| MS-03 | Cambios y releases | Cambios documentados y probados en staging | 100 %               |
| MS-04 | Continuidad        | Backup automático y restauración probada   | Sí                  |
| MS-05 | Configuración      | Versión desplegada = versión aprobada      | 100 %               |

### 4.3 Criterios de puesta en servicio y transferencia

Antes de declarar el servicio operativo se verifica:

- Release candidate etiquetado (SemVer) y aprobado en el Change Log.
- Cero defectos críticos/bloqueantes y recomendación escrita de QA.
- Plan de rollback documentado y probado.
- Credenciales, subdominio `*.unvime.edu.ar` y ≥ 100 GB de almacenamiento verificados (RP-01).
- TLS válido, backups programados y secretos fuera del código.
- Prueba de humo completa: login, carga, búsqueda, visualización y descarga.
- Dataset semilla ≥ 30 EDF catalogados y auditoría binaria con 0 PII.
- Canal de incidencias, monitoreo y procedimiento de cambio entregados a la Dirección TIC.

## 5. Verificación: listas de verificación e informes

### 5.1 Listas de verificación

Cada lista se completa por el responsable indicado y se adjunta al Informe de Calidad del hito. Un ítem **crítico (★)** en "no cumple" bloquea la aprobación.

| ID    | Lista                                         | Responsable              | Se usa en              |
| ----- | --------------------------------------------- | ------------------------ | ---------------------- |
| LV-01 | Definition of Done de código (PR a `develop`) | Autor + revisor          | Cada PR                |
| LV-02 | Ingesta, validación y anonimización EDF/EDF+  | Backend + QA             | Hito 4                 |
| LV-03 | Metadatos, baja lógica y exportación          | Backend + QA             | Hito 4                 |
| LV-04 | Autenticación, sesiones y RBAC                | Backend + QA             | Hitos 3 y 6            |
| LV-05 | Visualizador interactivo                      | Frontend + QA            | Hito 5                 |
| LV-06 | Compatibilidad cross-browser                  | QA                       | Hito 5                 |
| LV-07 | Base de datos y migraciones                   | Chiecher + Herrera       | Cada migración         |
| LV-08 | Seguridad web y transporte                    | QA + DevOps              | Hitos 3 y 6            |
| LV-09 | Revisión de calidad de documentos             | Process Owner + autor    | Cada documento         |
| LV-10 | Pre-despliegue y puesta en servicio           | DevOps + QA + PM         | Hito 6                 |
| LV-11 | Calidad del servicio para operar              | DevOps + PM              | Cierre / transferencia |
| LV-12 | Compuerta Go / No-Go de QA                    | QA recomienda; PM decide | Fin de Fase 5          |
| LV-13 | Cierre del proyecto                           | PM + APM                 | Hito 7                 |

### 5.2 Informes de calidad

| ID    | Informe                                             | Momento            | Autor        |
| ----- | --------------------------------------------------- | ------------------ | ------------ |
| IC-01 | Auditoría de proceso y configuración                | Fin de cada hito   | APM + QA     |
| IC-02 | Rendimiento, carga y compatibilidad                 | Fases 4–5          | QA           |
| IC-03 | Auditoría forense de cabeceras EDF                  | Hitos 4 y 6        | QA + Backend |
| IC-04 | Defectos y análisis de tendencia                    | Semanal / por hito | QA           |
| IC-05 | **Reporte Consolidado de QA (EJ-04)**               | Cierre de Fase 5   | Herrera (QA) |
| IC-06 | Registro de no conformidades y acciones correctivas | Continuo           | QA + APM     |
| IC-07 | Pruebas de aceptación (UAT)                         | Semanas 21–23      | QA           |

**Ciclo de aprobación:** elaboración (autor) → revisión (Process Owner o líder técnico) → aprobación (PM) → publicación en el repositorio central → comunicación en la reunión semanal de QA o en el Informe de Hito. Solo la versión publicada es vigente.

### 5.3 Calendario de calidad por hito

| Hito                    | Actividad principal                                  | Evidencia           |
| ----------------------- | ---------------------------------------------------- | ------------------- |
| H1 Acta de Constitución | Revisión del acta y aprobación del plan              | Acta de revisión    |
| H2 Requisitos aprobados | Revisión de ERS (29148) y línea base de métricas     | IC-01 (documental)  |
| H3 Autenticación        | RBAC, expiración, fuerza bruta, OWASP                | Reporte de pruebas  |
| H4 Gestión de señales   | Auditoría binaria, benchmark de ingesta, baja lógica | IC-03               |
| H5 Visualizador         | FPS/TTIS, cross-browser, usabilidad                  | IC-02               |
| H6 Despliegue           | Carga de 100 usuarios, TLS, humo, LV-10 y LV-11      | IC-05 / EJ-04       |
| H7 Cierre               | Auditoría final, lecciones aprendidas                | IC-01 final + actas |

### 5.4 Recolección de métricas

| Frecuencia       | Métricas                                      | Responsable           | Destino         |
| ---------------- | --------------------------------------------- | --------------------- | --------------- |
| Cada commit / PR | MP-MA, MP-SE-05/10, MPR-01/02/04              | CI (Chiecher)         | Log de CI       |
| Semanal          | Defectos (MP-RE-05, MPR-05/07) y avance       | QA + APM              | Reunión semanal |
| Por hito         | MPR-03, MPR-08…12; auditoría de configuración | APM + QA              | IC-01           |
| Fases 4–5        | MP-PE, MP-CO, MP-US, MP-SE-01…04/06…09        | QA, Frontend, Backend | IC-02, IC-03    |
| Fases 5–6        | MP-PE-04, MP-RE-01…04, MP-SE-03, MS-01…05     | QA + DevOps           | IC-05 (EJ-04)   |

## 6. Mejora continua

Se adopta un ciclo **PDCA** con revisión al cierre de cada hito:

1. **Planificar:** objetivos, métricas y acciones preventivas (secciones 2.2 y 3.2).
2. **Hacer:** ejecución del plan, PR, CI y pruebas.
3. **Verificar:** informes IC, auditorías, UAT y tablero de calidad.
4. **Actuar:** no conformidades (IC-06), análisis de causa raíz (5 Porqués / Ishikawa) y actualización del plan.

**Plan de mejora inicial:**

| Brecha                                               | Acción                                                                      | Responsable        | Verificación                 |
| ---------------------------------------------------- | --------------------------------------------------------------------------- | ------------------ | ---------------------------- |
| Cultura de calidad delegada solo a QA                | Incluir la calidad como criterio en la revisión de desempeño y en cada hito | PM                 | Acta de retrospectiva        |
| Falta de política de seguridad y codificación        | Publicar guía única de estilo y seguridad                                   | Herrera + Chiecher | Revisión en LV-01            |
| Diseño y arquitectura poco documentados              | Documento de arquitectura base                                              | Chiecher           | Revisión por pares           |
| Salidas no conformes sin procedimiento               | Formalizar el flujo de defectos de la sección 3.5                                     | QA                 | IC-06                        |
| Sin encuestas de satisfacción ni auditorías internas | Aplicar SUS en UAT y auditoría de proceso por hito                          | QA + APM           | IC-05 / IC-01                |
| Sin plan de mejora continua                          | Este apartado y revisión por hito                                           | PM                 | Versión actualizada del plan |
| Proceso de incidencias del servicio no formalizado   | Canal, categorías y prioridades antes de la transferencia                   | PM + DevOps        | LV-11                        |

Las mejoras aprobadas se incorporan como nueva versión de este plan (v1.1, v2.0) mediante el Change Log del Plan SCM.

## 7. Riesgos de calidad

| ID    | Riesgo                                                         | P   | I   | Mitigación                                                            | Alerta                                |
| ----- | -------------------------------------------------------------- | --- | --- | --------------------------------------------------------------------- | ------------------------------------- |
| RQ-01 | PII residual en cabecera, anotaciones EDF+ o nombre de archivo | 2   | 5   | Lista blanca de campos, auditoría binaria al 100 %, archivo sentinela | Cualquier hallazgo > 0                |
| RQ-02 | Visualizador < 30 FPS con 32 canales                           | 3   | 4   | Submuestreo LTTB, WebGL/Canvas, chunking, perfilado temprano          | FPS medio < 35 en pruebas intermedias |
| RQ-03 | Degradación con 100 usuarios concurrentes                      | 3   | 4   | Caché, paginado por fragmentos, carga progresiva (25/50/100)          | p95 > 3 s                             |
| RQ-04 | Safari/WebKit incompatible                                     | 3   | 3   | Playwright WebKit en CI y prueba manual en Safari                     | Falla en la matriz                    |
| RQ-05 | Infraestructura UNViMe tardía (RP-01)                          | 3   | 5   | Staging propio equivalente y escalamiento al patrocinador             | Sin credenciales al inicio de Fase 5  |
| RQ-06 | Cambios no controlados que rompen la línea base                | 2   | 4   | Ramas protegidas, RFC y auditoría por hito                            | Commit directo en `main`/`develop`    |
| RQ-07 | Falta de EDF válidos con aval ético (RP-03)                    | 3   | 4   | Dataset público de respaldo y convenios tempranos                     | < 30 registros al inicio de Fase 5    |

## 8. Integración con otros planes

- **Plan SCM:** ramas protegidas, PR con revisión cruzada, migraciones up/down, Change Log y auditoría de configuración.
- **Plan de Comunicaciones:** resultados de pruebas en la reunión semanal de QA y en el Informe de Hito.
- **Plan de Riesgos y Adquisiciones:** presupuesto de licencias $0; solo herramientas open source.
- **Gestión del Conocimiento:** lecciones aprendidas y Error Logs del proyecto.
- **Matriz de Competencias:** formación y evaluación de las habilidades requeridas por cada rol.
