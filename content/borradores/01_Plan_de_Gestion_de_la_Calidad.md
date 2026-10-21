# Plan de Gestión de la Calidad — Proyecto BioSignal

| Campo | Valor |
|---|---|
| Proyecto | BioSignal – Plataforma web de repositorio y visualización de bioseñales (EDF/EDF+) |
| Organización / Patrocinador | Universidad Nacional de Villa Mercedes (UNViMe) |
| Documento | PGC-BIOSIG-01 |
| Versión | v0.1 (borrador) — pasa a v1.0 al ser aprobado por el PM |
| Elaborado por | Equipo PM / QA |
| Aprobado por | Mateo T. Astudillo (Director del Proyecto) |
| Fecha límite del proyecto | 15/02/2027 (inamovible, RP-02) |
| Ítem de configuración | CI-DOC (ver Plan SCM) |

## Historial de cambios

| Versión | Fecha | Autor | Descripción |
|---|---|---|---|
| v0.1 | 20/10/2026 | Equipo PM/QA | Versión inicial del plan |

---

## 1. Propósito y alcance

Este plan define **cómo** el equipo planifica, asegura y controla la calidad de BioSignal: política, objetivos, normas, roles, actividades, herramientas y criterios de aceptación. Se estructura según los tres procesos del PMBOK 6 (Gestión de la Calidad del Proyecto, procesos 8.1, 8.2 y 8.3).

Alcance:

- **Calidad del producto:** módulos EP-01 a EP-06 (autenticación/RBAC, ingesta y sanitización EDF, visualizador, acceso público, exportación, dataset semilla).
- **Calidad del proyecto/proceso:** entregables EJ-01 a EJ-06 (actas, ERS, código, reporte QA, actas de despliegue y cierre).
- **Fuera de alcance** (según Enunciado de Alcance): certificación ANMAT, manuales de usuario, capacitación, soporte posterior al cierre.

## 2. Política de calidad

> El equipo de BioSignal se compromete a entregar a la UNViMe una plataforma **segura, confiable, rápida y verificable**, que proteja de forma irreversible la privacidad de los pacientes (Ley 25.326), cumpla los criterios de aceptación acordados antes del 15/02/2027 y sea construida con procesos repetibles, trazables y auditables.

## 3. Objetivos de calidad (medibles)

| ID | Objetivo | Meta | Origen |
|---|---|---|---|
| OC-01 | Privacidad de datos | 0 % de datos identificatorios residuales en el 100 % de los EDF persistidos | RF-06, RNF-05 |
| OC-02 | Defectos críticos/bloqueantes | 0 abiertos al cierre de la fase de QA | Criterios de aceptación §4 |
| OC-03 | Desempeño de visualización | Primer segmento ≤ 2,5 s (≥ 10 Mbps) y ≥ 30 FPS | RNF-02, RNF-03 |
| OC-04 | Concurrencia | 100 usuarios simultáneos sin errores 5xx | RNF-01 |
| OC-05 | Ingesta | ≤ 30 s para EDF < 50 MB | RNF-04 |
| OC-06 | Seguridad en tránsito | TLS 1.3, calificación A en SSL Labs / testssl | RNF-06 |
| OC-07 | Mantenibilidad | Cobertura de pruebas unitarias > 80 % en lógica crítica; 0 fallas | Plan de trabajo 1.4.1 |
| OC-08 | Compatibilidad | 100 % de la matriz cross-browser superada | RNF-07 |
| OC-09 | Usabilidad | Tarea “buscar–abrir–configurar señal” < 5 min | RNF-09 |
| OC-10 | Cumplimiento de proceso | 100 % de PR con revisión cruzada; 100 % de cambios en Change Log | Plan SCM |

## 4. Normas y estándares aplicables

| Norma | Rol en el proyecto | Dónde se aplica |
|---|---|---|
| **ISO/IEC 90003 / ISO 9001** | Marco del sistema de gestión de calidad: política, procedimientos de control, mejora continua | Este plan; auditorías de proceso por hito |
| **ISO/IEC 12207 (Nivel 1 de madurez)** | Procesos del ciclo de vida: infraestructura, entorno de desarrollo, control de versiones, arquitectura base (proceso ejecutado con ambiente listo) | Paquetes 1.2.1, 1.2.2; Plan SCM; CI/CD |
| **ISO/IEC 25010** | Modelo de calidad del producto (8 características) | Documento de Métricas de Calidad (02) |
| **ISO/IEC 20000** | Gestión de servicios: incidencias, disponibilidad, cambios, release | Checklists de despliegue y puesta en servicio (03) |
| **ISO/IEC/IEEE 29148 / IEEE 830** | Calidad de los requisitos (ERS) | Paquete 1.1.2 |
| **EDF / EDF+ (Kemp et al.)** | Formato de entrada/salida de señales | RF-04, RF-05, RF-06 |
| **Ley 25.326 (Argentina)** | Protección de datos personales | RF-06, RNF-05, RP-03 |
| **OWASP Top 10 / ASVS** | Verificación de seguridad web | Pruebas de seguridad |
| **WCAG 2.1 (AA)** | Accesibilidad / contraste en gráficos fisiológicos | UI/UX |
| **Core Web Vitals (LCP)** | Medición del tiempo de primer segmento | RNF-02 |

> Nota sobre ISO 20000: el soporte posterior al Acta de Cierre está **fuera de alcance**. Los checklists de ISO 20000 se usan para dejar el servicio **listo para operar** y entregar a la Dirección TIC las prácticas recomendadas (incidencias, disponibilidad, cambios) en el momento de la transferencia.

## 5. Roles y responsabilidades de calidad

| Rol | Integrante | Responsabilidad de calidad |
|---|---|---|
| Director del Proyecto / CCB | Mateo T. Astudillo | Aprueba el plan, las líneas base de calidad, los cambios y la liberación a producción (recomendada por QA) |
| Asistente del PM / Process Owner | Ignacio N. Ávila Gelbes | Mantiene este plan, el registro de calidad, el Change Log; coordina auditorías de configuración y de proceso |
| Líder de Código y QA | Germán E. Herrera | Diseña/ejecuta plan de pruebas, aprueba o rechaza entregables, emite el Reporte Consolidado de QA, revisa PRs |
| Líder de Infraestructura y BD | Eber B. Chiecher | Calidad de infraestructura, migraciones (up/down), backups, TLS, CI/CD, monitoreo |
| Líder Frontend y UI/UX | Rocío Pereyra / Martín D. Mosainer | Calidad del visualizador, usabilidad, accesibilidad, rendimiento en cliente, revisión de PRs full-stack |
| Revisor Legal/Normativo | Equipo PM / Asesoría UNViMe | Dictamen de cumplimiento de Ley 25.326 y convenios (RP-03) |
| Patrocinador / UNViMe | Alejandro Rosas / Dirección TIC | Aceptación formal de entregables; provisión de infraestructura (RP-01) |

*(Ajustar la asignación nominal a la matriz RACI definitiva del Plan de Recursos.)*

## 6. Enfoque de gestión de la calidad (PMBOK 6)

### 6.1 Planificar la Gestión de la Calidad (8.1)

- Identificar requisitos y estándares de calidad desde la ERS y la matriz de trazabilidad (RNF-01 a RNF-09, RP-01 a RP-03).
- Definir métricas (documento 02) y checklists (documento 03).
- Análisis costo-beneficio de calidad (ver §10) y diseño de pruebas (§8).
- Resultado: este plan, métricas, checklists y plan de mejora de procesos.

### 6.2 Gestionar la Calidad — Aseguramiento (8.2)

Actividades **preventivas** orientadas al proceso:

| Actividad | Frecuencia | Responsable | Evidencia |
|---|---|---|---|
| Revisión cruzada de PR (code review) | Cada PR | Herrera / Mosainer | Aprobación en GitHub |
| Pipeline CI (lint, build, tests, SAST, auditoría de dependencias) | Cada push/PR | DevOps (Chiecher) | Log de CI |
| Revisión por pares de documentos (ERS, planes) | Por documento | Process Owner | Acta de revisión |
| Auditoría de configuración | Fin de cada hito (7) | APM + QA | Informe IC-01 |
| Auditoría de proceso de calidad | Hitos 3, 5 y 6 | PM + QA | Informe IC-01 |
| Retrospectiva y lecciones aprendidas | Fin de fase | PM | Registro de lecciones |
| Diagramas de causa-efecto / análisis de Pareto de defectos | Ante tendencia adversa | QA | Informe IC-04 |
| Revisión del modelo de datos y migraciones | Cada migración DDL | Chiecher | Script up/down aprobado |

### 6.3 Controlar la Calidad (8.3)

Actividades **detectivas** orientadas al producto: ejecución de pruebas, inspecciones, mediciones y verificación de entregables (ver §8). Resultado: mediciones de control, entregables verificados, solicitudes de cambio por defectos y Reportes de Calidad.

## 7. Entregables y criterios de calidad

| Entregable | Criterio de calidad | Método de verificación | Responsable |
|---|---|---|---|
| EP-01 Autenticación/RBAC | 403 ante acción no permitida; expiración Admin a 30 min; bloqueo tras 5 intentos | [P] Pruebas unitarias/integración; pruebas de elevación de privilegios | QA |
| EP-02 Ingesta/Sanitización | Cabecera validada; 0 PII residual; ≤ 30 s (<50 MB); baja lógica con auditoría | [P] Benchmark; auditoría binaria automatizada al 100 % | QA + Backend |
| EP-03 Visualizador | LCP ≤ 2,5 s; ≥ 30 FPS; 32 canales (desktop) / 1–2 (móvil) | [P] Lighthouse/CWV; DevTools Performance | QA + Frontend |
| EP-04 Acceso público | Señal demo + enlace admisiones funcional sin credenciales | [D] Demostración | PM + QA |
| EP-05 Exportación | EDF íntegro y anonimizado, sin pérdida de muestras | [P] Comparación de hash/valores; validación con MNE-Python | QA |
| EP-06 Dataset semilla | ≥ 30 EDF (≥ 15 ECG, ≥ 15 EEG) catalogados | [I] Inventario en BD de producción | DBA/Chiecher |
| EJ-02 ERS + matriz | Sin ambigüedades; cobertura de trazabilidad 100 % | [I] Revisión por pares | Process Owner |
| EJ-03 Código | Convenciones, sin secretos, CI verde | [I] Linter, SAST, revisión PR | Herrera |
| EJ-04 Reporte QA | Cero críticos/bloqueantes abiertos | [A] Informe final de QA | QA |
| EJ-05/06 Actas | Firmadas ≤ 15/02/2027 | [I] Acta firmada | PM |

## 8. Estrategia de pruebas y herramientas

| Nivel / tipo | Alcance | Herramientas sugeridas (open source, costo $0) |
|---|---|---|
| Unitarias | Parser EDF, validador de cabecera, sanitización, RBAC, expiración de sesión | pytest + pytest-cov (FastAPI); Jest/Vitest (Next.js) |
| Integración | API ↔ BD ↔ almacenamiento; migraciones | pytest + Testcontainers/Docker Compose |
| E2E / funcionales | Flujos login, carga, búsqueda, visualización, descarga | Playwright |
| Rendimiento y carga | 100 usuarios concurrentes; latencia; ingesta | k6 o Apache JMeter |
| Rendimiento en cliente | LCP, FPS | Lighthouse, Chrome DevTools Performance |
| Seguridad | OWASP Top 10, dependencias, TLS | OWASP ZAP, pip-audit, npm audit, Bandit, testssl.sh / SSL Labs |
| Privacidad / forense EDF | Inspección binaria de cabeceras y anotaciones EDF+ | Script propio (Python) + MNE-Python/pyedflib como validador cruzado |
| Compatibilidad | Chrome, Edge, Firefox, Safari (2 últimas versiones estables) | Playwright (Chromium/Firefox/WebKit) + prueba manual en Safari real |
| Usabilidad | Time-on-Task < 5 min | Prueba con usuarios representativos (estudiantes) |
| Aceptación (UAT) | Validación por docentes/GAB | Sesiones UAT con acta |
| Humo (smoke) | Producción tras despliegue | Script automatizado + checklist CL-06 |
| Calidad estática | Estilo y complejidad | ruff/flake8, mypy, ESLint, Prettier |

**Datos de prueba:** señales sintéticas y anonimizadas (PhysioNet/PhysioBank, p. ej. archivos EDF públicos de EEG y ECG), más un EDF “sentinela” con PII sintética en todos los campos para validar la sanitización.

## 9. Gestión de defectos

### 9.1 Clasificación de severidad

| Severidad | Definición | Ejemplo | SLA de corrección |
|---|---|---|---|
| **Crítica / Bloqueante** | Caída del servidor, fuga de PII, corrupción de datos, falla de renderizado general | EDF persistido con nombre del paciente | Inmediata; bloquea el hito |
| **Mayor** | Funcionalidad principal degradada, sin alternativa | Paneo cae a < 30 FPS | ≤ 3 días hábiles |
| **Menor** | Falla con alternativa razonable | Reordenar canales falla en un navegador | Antes del cierre de fase |
| **Cosmético** | Sin impacto funcional | Alineación de un botón | Backlog |

### 9.2 Ciclo de vida

`Nuevo → Triage (QA) → Asignado → En corrección (bugfix/*) → PR + revisión → En verificación → Cerrado / Reabierto`

Todo defecto se registra en el gestor de tareas con ID, severidad, versión, pasos de reproducción, evidencia y vínculo al requisito afectado. Las correcciones que alteren una línea base siguen el flujo del **Plan SCM** (RFC en el Change Log).

### 9.3 Criterios de entrada y salida de la fase de QA

- **Entrada:** módulos 1.3 implementados, CI verde, despliegue en staging con datos anonimizados.
- **Salida (Go / No-Go):** 0 críticos/bloqueantes abiertos; 100 % de pruebas unitarias en verde; cobertura > 80 % en lógica crítica; métricas RNF-01 a RNF-09 en umbral; auditoría binaria 100 % limpia; recomendación escrita de QA al PM.

## 10. Costo de la calidad (estimación cualitativa)

| Categoría | Ejemplos en BioSignal |
|---|---|
| Prevención | Plantillas, peer review, CI/CD, guías de estilo, definición de métricas |
| Evaluación | Pruebas, auditorías, UAT, perfilado de rendimiento |
| Falla interna | Retrabajo por bugs hallados en QA, re-sanitización de archivos |
| Falla externa | Defecto en producción durante la Expo Carreras / inicio de ciclo 2027, fuga de PII |

Criterio de inversión: se prioriza **prevención y evaluación en el flujo de ingesta/anonimización** (impacto máximo: legal y reputacional) y en el **visualizador** (impacto máximo: adopción curricular).

## 11. Riesgos de calidad

| ID | Riesgo | P | I | Mitigación | Métrica de alerta |
|---|---|---|---|---|---|
| RQ-01 | PII residual en cabecera, anotaciones EDF+ o nombre de archivo | 2 | 5 | Sanitización por lista blanca de campos, auditoría binaria al 100 %, archivo sentinela | Cualquier hallazgo > 0 |
| RQ-02 | Visualizador < 30 FPS con 32 canales | 3 | 4 | Submuestreo LTTB, WebGL/Canvas, chunking, perfilado temprano (Sprint de Hito 5) | FPS medio < 35 en pruebas intermedias |
| RQ-03 | Degradación con 100 usuarios concurrentes | 3 | 4 | Caché, paginado por fragmentos, prueba de carga progresiva (25/50/100) | p95 > 3 s |
| RQ-04 | Safari/WebKit incompatible (WebGL, Canvas) | 3 | 3 | Playwright WebKit en CI; prueba manual en Safari real | Falla en matriz |
| RQ-05 | Infraestructura UNViMe tardía (RP-01) | 3 | 5 | Staging propio equivalente en Docker; escalar al patrocinador | Sin credenciales al inicio de Fase 5 |
| RQ-06 | Cambios no controlados que rompen línea base | 2 | 4 | Plan SCM, ramas protegidas, auditoría por hito | Commit directo en main/develop |
| RQ-07 | Falta de datos EDF válidos y con aval ético (RP-03) | 3 | 4 | Dataset público (PhysioNet) como respaldo; gestionar convenios temprano | < 30 registros al inicio de Fase 5 |

## 12. Cronograma de actividades de calidad

| Hito | Actividad de calidad principal | Entregable de calidad |
|---|---|---|
| H1 Acta de Constitución | Revisión del acta; aprobación de este plan (borrador) | Acta de revisión |
| H2 Requisitos aprobados | Revisión de calidad de ERS (29148); línea base de métricas | Informe de Calidad IC-01 (v. documental) |
| H3 Autenticación | Pruebas RBAC, expiración 30 min, fuerza bruta, escaneo OWASP | Reporte unitarias/integración parcial |
| H4 Gestión de señales | Auditoría binaria EDF, benchmark de ingesta, pruebas de baja lógica | Informe IC-03 (auditoría EDF) |
| H5 Visualizador | Perfilado FPS/LCP, cross-browser, usabilidad | Informe IC-02 (rendimiento) |
| H6 Despliegue | Carga 100 usuarios, TLS, humo, checklists ISO 20000 | Reporte Consolidado QA (EJ-04) |
| H7 Cierre | Auditoría final de configuración y calidad, lecciones aprendidas | Informe IC-05 + actas |

## 13. Mejora continua

- Retrospectiva al final de cada hito con acciones registradas (ciclo PDCA).
- Análisis de causa raíz (5 Porqués / Ishikawa) de todo defecto Mayor o Crítico.
- Las mejoras de proceso aprobadas se reflejan como nueva versión de este plan (v1.1, v2.0) vía Change Log.

## 14. Integración con otros planes

- **Plan SCM:** ramas protegidas, PR con revisión cruzada, migraciones up/down, Change Log y auditoría de configuración.
- **Plan de Comunicaciones:** los resultados de pruebas se comunican en la reunión semanal de QA y por Informe de Hito.
- **Plan de Riesgos / Adquisiciones:** presupuesto de licencias $0 → solo herramientas open source.

## 15. Aprobaciones

| Rol | Nombre | Firma | Fecha |
|---|---|---|---|
| Director del Proyecto | Mateo T. Astudillo | | |
| Líder de QA | Germán E. Herrera | | |
| Patrocinador | Alejandro Rosas | | |
