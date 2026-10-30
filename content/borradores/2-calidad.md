# Métricas de Calidad — Proyecto BioSignal

| Campo          | Valor                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------- |
| Documento      | MQ-BIOSIG-02 (anexo del Plan de Gestión de la Calidad)                                         |
| Versión        | v0.1 (borrador)                                                                                |
| Base normativa | ISO/IEC 25010 (producto), ISO/IEC 12207 nivel 1 (proceso), ISO 9001/90003 (sistema de calidad) |

## 1. Cómo leer este documento

Cada métrica tiene: **ID**, qué se mide, **fórmula**, **umbral Pasa / No Pasa**, **herramienta**, **cuándo** y **quién**. Un entregable se considera técnicamente exitoso cuando **todas** sus métricas obligatorias están en "Pasa". Las métricas provienen de los RNF y criterios de aceptación aprobados; no se introducen umbrales nuevos salvo los marcados con (*) , que son propuestos por el equipo de calidad.

Convención de verificación: [P] Prueba · [D] Demostración · [I] Inspección · [A] Análisis.

## 2. Métricas de producto (ISO/IEC 25010)

### 2.1 Adecuación funcional (Functional Suitability)

| ID       | Subcaracterística      | Métrica                                    | Fórmula                                           | Umbral                                                     | Herramienta                                 | Req.         |
| -------- | ---------------------- | ------------------------------------------ | ------------------------------------------------- | ---------------------------------------------------------- | ------------------------------------------- | ------------ |
| MP-FS-01 | Completitud funcional  | % de RF implementados y verificados        | RF con prueba aprobada / 14 RF × 100              | 100 %                                                      | Matriz de trazabilidad + reporte de pruebas | RF-01…RF-14  |
| MP-FS-02 | Corrección funcional   | Casos de prueba de aceptación aprobados    | Casos OK / casos ejecutados × 100                 | 100 % de los críticos; ≥ 95 % del total (*)                | Playwright / UAT                            | Criterios §4 |
| MP-FS-03 | Pertinencia funcional  | Aceptación EDF válidos y rechazo de no-EDF | Aciertos / casos del conjunto de validación × 100 | 100 % (conjunto con EDF válidos, EDF+ y archivos espurios) | pytest                                      | RF-04        |
| MP-FS-04 | Corrección de cabecera | Cabeceras corruptas detectadas             | Detectadas / inyectadas × 100                     | 100 %                                                      | pytest con fuzzing de cabecera              | RF-05        |

### 2.2 Eficiencia de desempeño (Performance Efficiency)

| ID       | Subcaracterística       | Métrica                                     | Fórmula                                             | Umbral                                      | Herramienta                              | Req.                |
| -------- | ----------------------- | ------------------------------------------- | --------------------------------------------------- | ------------------------------------------- | ---------------------------------------- | ------------------- |
| MP-PE-01 | Comportamiento temporal | Tiempo al primer segmento interactivo (LCP) | Mediana y p95 de LCP en 10 Mbps                     | **≤ 2,5 s** (p75 según CWV)                 | Lighthouse / Web Vitals                  | RNF-02              |
| MP-PE-02 | Comportamiento temporal | Fluidez de renderizado                      | FPS medio y p5 durante paneo/zoom continuo (≥ 60 s) | **≥ 30 FPS** sostenidos                     | Chrome DevTools Performance              | RNF-03              |
| MP-PE-03 | Comportamiento temporal | Tiempo de ingesta                           | Tiempo(validación + sanitización + persistencia)    | **≤ 30 s** para EDF < 50 MB                 | Benchmark en servidor (n ≥ 10)           | RNF-04              |
| MP-PE-04 | Capacidad               | Usuarios concurrentes                       | Usuarios virtuales simultáneos sin 5xx              | **100** con 0 errores 5xx                   | k6 / JMeter                              | RNF-01              |
| MP-PE-05 | Comportamiento temporal | Latencia bajo carga                         | Latencia media de API en la prueba de 100 usuarios  | < 3 s media (traza RNF-01); p95 ≤ 5 s (*)   | k6                                       | RNF-01              |
| MP-PE-06 | Utilización de recursos | Uso de CPU/memoria en servidor bajo carga   | % pico durante la prueba                            | CPU < 80 %, RAM < 80 % (*)                  | Monitoreo (Prometheus/Grafana o similar) | RNF-01              |
| MP-PE-07 | Utilización de recursos | Memoria del navegador con 32 canales        | MB de heap tras 5 min de uso                        | Sin crecimiento sostenido (sin fuga) (*)    | DevTools Memory                          | RNF-08              |
| MP-PE-08 | Comportamiento temporal | Latencia consulta a BD                      | Tiempo de consulta de catálogo                      | < 50 ms conexión BD; consultas < 500 ms (*) | EXPLAIN ANALYZE / pgbench                | Pkg 1.2.1 / 1.3.3.1 |

### 2.3 Compatibilidad (Compatibility)

| ID       | Subcaracterística              | Métrica                            | Fórmula                                                                                                               | Umbral | Herramienta              | Req.   |
| -------- | ------------------------------ | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ------ | ------------------------ | ------ |
| MP-CO-01 | Coexistencia/Interoperabilidad | % de matriz cross-browser superada | Casos OK / casos totales × 100 (Chromium: Chrome, Edge; Gecko: Firefox; WebKit: Safari; 2 últimas versiones estables) | 100 %  | Playwright + Safari real | RNF-07 |
| MP-CO-02 | Interoperabilidad              | Validez del EDF exportado          | EDF exportados legibles por librerías estándar / total exportados                                                     | 100 %  | MNE-Python / pyedflib    | RF-14  |

### 2.4 Usabilidad (Usability)

| ID       | Subcaracterística        | Métrica                                             | Fórmula                                               | Umbral                                      | Herramienta                    | Req.         |
| -------- | ------------------------ | --------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------- | ------------------------------ | ------------ |
| MP-US-01 | Capacidad de aprendizaje | Time-on-Task: buscar, abrir y configurar una señal  | Tiempo medio con ≥ 5 estudiantes sin formación previa | **< 5 min** (media); todos < 8 min (*)      | Prueba de usuario cronometrada | RNF-09       |
| MP-US-02 | Tasa de éxito de tarea   | % de participantes que completan la tarea sin ayuda | Completan / participantes × 100                       | ≥ 90 % (*)                                  | Prueba de usuario              | RNF-09       |
| MP-US-03 | Accesibilidad            | Contraste de trazado/etiquetas                      | Ratio de contraste                                    | ≥ 4,5:1 texto; ≥ 3:1 gráficos (WCAG 2.1 AA) | Lighthouse / axe               | UI/UX        |
| MP-US-04 | Adaptabilidad de UI      | Despliegue por dispositivo                          | Canales visibles: ≥ 1024 px hasta 32; < 768 px 1–2    | Cumple                                      | [D] Demostración responsive    | RNF-08       |
| MP-US-05 | Satisfacción             | Cuestionario SUS                                    | Puntaje SUS                                           | ≥ 68 (*)                                    | Cuestionario post-UAT          | RI-03, RI-04 |

### 2.5 Fiabilidad (Reliability)

| ID       | Subcaracterística   | Métrica                                                | Fórmula                                                         | Umbral                                                        | Herramienta                         | Req.         |
| -------- | ------------------- | ------------------------------------------------------ | --------------------------------------------------------------- | ------------------------------------------------------------- | ----------------------------------- | ------------ |
| MP-RE-01 | Madurez             | Tasa de errores críticos en prueba de estrés           | Peticiones con error crítico (5xx/timeout) / total × 100        | **< 1 %** global; **0 %** de 5xx en la prueba de 100 usuarios | k6                                  | RNF-01       |
| MP-RE-02 | Disponibilidad      | Disponibilidad inicial en producción                   | Tiempo operativo / tiempo total (ventana de observación)        | ≥ 99,9 %                                                      | Uptime monitor (p. ej. Uptime Kuma) | Pkg 1.5      |
| MP-RE-03 | Tolerancia a fallos | Integridad ante fallo de ingesta                       | Registros inconsistentes metadatos↔binario tras fallo inyectado | 0 (transacción atómica con rollback)                          | pytest de integración               | Pkg 1.3.2.1  |
| MP-RE-04 | Recuperabilidad     | Restauración desde backup                              | Restauración exitosa y tiempo                                   | Éxito 100 %; RTO ≤ 4 h (*)                                    | Prueba de restauración en staging   | Pkg 1.2.1    |
| MP-RE-05 | Madurez             | Densidad de defectos                                   | Defectos confirmados / KLOC (o por módulo)                      | Tendencia decreciente; 0 críticos al cierre                   | Gestor de tareas                    | OC-02        |
| MP-RE-06 | Madurez             | Defectos críticos/bloqueantes abiertos al cierre de QA | Conteo                                                          | **0**                                                         | Reporte QA                          | Criterios §4 |

### 2.6 Seguridad (Security)

| ID       | Subcaracterística                | Métrica                                           | Fórmula                                                                                   | Umbral                                | Herramienta                            | Req.          |
| -------- | -------------------------------- | ------------------------------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------- | -------------------------------------- | ------------- |
| MP-SE-01 | Confidencialidad                 | PII residual en EDF persistidos                   | Archivos con PII en campos paciente/registro / total × 100                                | **0 %** sobre el 100 % de archivos    | Script de auditoría binaria            | RF-06, RNF-05 |
| MP-SE-02 | Confidencialidad                 | PII en anotaciones EDF+ y metadatos de archivo    | Hallazgos en canal de anotaciones, nombre de archivo, logs                                | 0                                     | Script de auditoría + revisión de logs | RF-06         |
| MP-SE-03 | Confidencialidad                 | Cifrado en tránsito                               | Protocolo y calificación                                                                  | **TLS 1.3** exclusivo; calificación A | testssl.sh / SSL Labs                  | RNF-06        |
| MP-SE-04 | Autenticidad/Control de acceso   | Vulnerabilidades OWASP Top 10 (críticas/altas)    | Hallazgos abiertos                                                                        | **0**                                 | OWASP ZAP + revisión manual            | OC-02         |
| MP-SE-05 | Confidencialidad                 | Vulnerabilidades en dependencias (críticas/altas) | Hallazgos abiertos                                                                        | **0**                                 | pip-audit, npm audit                   | Pkg 1.3       |
| MP-SE-06 | Control de acceso                | Pruebas de elevación de privilegios               | Intentos no autorizados bloqueados / intentos                                             | 100 % con HTTP 403                    | pytest / ZAP                           | RF-01         |
| MP-SE-07 | Responsabilidad (Accountability) | Eventos auditables registrados                    | Eventos críticos (alta, edición, baja, descarga, login) con registro / eventos ejecutados | 100 %                                 | Inspección de logs                     | RF-08         |
| MP-SE-08 | Autenticidad                     | Expiración de sesión Admin                        | Sesiones invalidadas a los 30 min de inactividad                                          | 100 % (tolerancia ± 5 s)              | pytest / E2E                           | RF-02         |
| MP-SE-09 | Integridad                       | Fuerza bruta                                      | Bloqueo tras intentos fallidos                                                            | Bloqueo efectivo al 5.º intento       | E2E                                    | Pkg 1.3.1.1   |
| MP-SE-10 | Integridad                       | Secretos hardcodeados                             | Hallazgos en repositorio                                                                  | 0                                     | gitleaks / trufflehog                  | SCM §3.3      |
| MP-SE-11 | No repudio / Integridad          | Integridad de señal tras edición de metadatos     | Hash del binario antes = después                                                          | 100 %                                 | Test de hash                           | Pkg 1.3.2.2   |

### 2.7 Mantenibilidad (Maintainability)

| ID       | Subcaracterística   | Métrica                              | Fórmula                                           | Umbral                              | Herramienta                 | Req.      |
| -------- | ------------------- | ------------------------------------ | ------------------------------------------------- | ----------------------------------- | --------------------------- | --------- |
| MP-MA-01 | Capacidad de prueba | Cobertura de pruebas unitarias       | % de líneas (y ramas) cubiertas en lógica crítica | **> 80 %** (*ramas ≥ 70 %)          | pytest-cov / Jest-coverage  | Pkg 1.4.1 |
| MP-MA-02 | Capacidad de prueba | Pruebas unitarias exitosas           | Pasan / ejecutadas                                | 100 % (0 fallas)                    | CI                          | Pkg 1.4.1 |
| MP-MA-03 | Analizabilidad      | Cumplimiento de estándares de código | Errores de linter abiertos                        | 0 errores; advertencias tendencia ↓ | ruff, ESLint, mypy, tsc     | CI        |
| MP-MA-04 | Modularidad         | Complejidad ciclomática              | Máx. por función                                  | ≤ 10 (excepciones justificadas) (*) | radon / ESLint complexity   | CI        |
| MP-MA-05 | Modificabilidad     | Duplicación de código                | % duplicado                                       | ≤ 5 % (*)                           | jscpd / SonarQube Community | CI        |
| MP-MA-06 | Reusabilidad        | Migraciones con par up/down          | Migraciones con rollback probado / total          | 100 %                               | Revisión + CI               | SCM §4.3  |

### 2.8 Portabilidad (Portability)

| ID       | Subcaracterística | Métrica                                  | Fórmula                                                    | Umbral                  | Herramienta            | Req.      |
| -------- | ----------------- | ---------------------------------------- | ---------------------------------------------------------- | ----------------------- | ---------------------- | --------- |
| MP-PO-01 | Instalabilidad    | Despliegue reproducible con contenedores | Despliegue desde cero con un comando documentado en README | Éxito en entorno limpio | Docker Compose / CI    | Pkg 1.2.2 |
| MP-PO-02 | Adaptabilidad     | Funcionamiento en múltiples dispositivos | Ver MP-US-04 y MP-CO-01                                    | Cumple                  | Playwright (emulación) | RNF-08    |

## 3. Métricas de proceso (ISO 9001 / ISO 12207 nivel 1)

| ID     | Proceso                    | Métrica                                               | Fórmula                                                         | Umbral                           | Fuente                     |
| ------ | -------------------------- | ----------------------------------------------------- | --------------------------------------------------------------- | -------------------------------- | -------------------------- |
| MPR-01 | Control de versiones       | PR con revisión de tercero                            | PR aprobadas por revisor ≠ autor / PR totales                   | 100 %                            | GitHub                     |
| MPR-02 | Control de versiones       | Commits directos a `main`/`develop`                   | Conteo                                                          | 0                                | GitHub (ramas protegidas)  |
| MPR-03 | Gestión de cambios         | Cambios con RFC en Change Log                         | Cambios registrados / cambios aplicados a líneas base           | 100 %                            | Change Log                 |
| MPR-04 | Integración continua       | Builds de `develop` en verde                          | Builds OK / builds totales                                      | ≥ 90 % (*)                       | CI                         |
| MPR-05 | Verificación               | Eficacia de remoción de defectos (DRE)                | Defectos hallados antes de producción / (antes + después) × 100 | ≥ 95 % (*)                       | Gestor de tareas           |
| MPR-06 | Verificación               | Defectos escapados a UAT/producción                   | Conteo y severidad                                              | 0 críticos                       | Reporte QA                 |
| MPR-07 | Verificación               | Reapertura de defectos                                | Reabiertos / cerrados × 100                                     | ≤ 10 % (*)                       | Gestor de tareas           |
| MPR-08 | Gestión de proyecto        | Desempeño de cronograma y costo                       | SPI = EV/PV; CPI = EV/AC                                        | SPI ≥ 0,9 y CPI ≥ 0,9 (*)        | Reportes de avance (1.1.4) |
| MPR-09 | Documentación              | Documentos con revisión por pares antes de aprobación | Revisados / aprobados                                           | 100 %                            | Actas de revisión          |
| MPR-10 | Requisitos                 | Cobertura de trazabilidad                             | RF/RNF con traza a EDT y prueba / total                         | 100 %                            | Matriz de trazabilidad     |
| MPR-11 | Auditoría de configuración | Desvíos hallados por hito                             | Conteo                                                          | 0 sin justificar                 | Informe IC-01              |
| MPR-12 | Infraestructura            | Ambientes listos (dev/staging/prod)                   | Ambientes operativos / planificados                             | 100 % antes del inicio de Fase 3 | Pkg 1.2.1 / 1.2.2          |

## 4. Métricas del servicio (ISO/IEC 20000, para el pase a producción)

| ID    | Práctica                      | Métrica                                                                                   | Umbral                   |
| ----- | ----------------------------- | ----------------------------------------------------------------------------------------- | ------------------------ |
| MS-01 | Gestión de incidencias        | Canal documentado de reporte de fallas disponible                                         | Sí (existe y verificado) |
| MS-02 | Gestión de disponibilidad     | Monitoreo de uptime activo con alertas                                                    | Sí; objetivo 99,9 %      |
| MS-03 | Gestión de cambios y releases | Cambios en backend/infraestructura documentados y probados en staging antes de producción | 100 %                    |
| MS-04 | Continuidad / respaldo        | Backup automático programado y restauración probada                                       | Sí                       |
| MS-05 | Gestión de la configuración   | Versión desplegada = versión aprobada en Change Log                                       | 100 %                    |

## 5. Trazabilidad RNF → Métrica

| RNF                        | Métrica(s)                             |
| -------------------------- | -------------------------------------- |
| RNF-01 Concurrencia        | MP-PE-04, MP-PE-05, MP-PE-06, MP-RE-01 |
| RNF-02 Tiempo de respuesta | MP-PE-01                               |
| RNF-03 Fluidez             | MP-PE-02                               |
| RNF-04 Ingesta             | MP-PE-03                               |
| RNF-05 Privacidad          | MP-SE-01, MP-SE-02, MP-SE-11           |
| RNF-06 TLS 1.3             | MP-SE-03                               |
| RNF-07 Navegadores         | MP-CO-01                               |
| RNF-08 Adaptabilidad       | MP-US-04, MP-PE-07                     |
| RNF-09 Usabilidad          | MP-US-01, MP-US-02, MP-US-05           |

## 6. Plan de recolección

| Frecuencia       | Métricas                                                     | Responsable           | Destino                        |
| ---------------- | ------------------------------------------------------------ | --------------------- | ------------------------------ |
| Cada commit / PR | MP-MA-01…06, MP-SE-05, MP-SE-10, MPR-01, MPR-02, MPR-04      | CI (Chiecher)         | Log de CI                      |
| Semanal          | Defectos (MP-RE-05/06, MPR-05/07), avance                    | QA + APM              | Reunión semanal de QA          |
| Por hito         | MPR-03, MPR-08…12; auditoría de configuración                | APM + QA              | Informe IC-01                  |
| Fase 4–5         | MP-PE-01…08, MP-CO-01, MP-US-01…05, MP-SE-01…04, MP-SE-06…09 | QA, Frontend, Backend | Informes IC-02, IC-03          |
| Fase 5–6         | MP-PE-04, MP-RE-01…04, MP-SE-03, MS-01…05                    | QA + DevOps           | Reporte Consolidado QA (EJ-04) |

## 7. Observación de consistencia

Algunos paquetes de trabajo del EDT mencionaban valores distintos a los del Enunciado de Alcance y los RNF aprobados (60 FPS, archivos de 500 MB en 20 s, exportación a CSV/JSON/MATLAB). Este documento **adopta los valores de los RNF y del Enunciado de Alcance** (30 FPS, <50 MB en 30 s, solo EDF/EDF+).

> **Actualización 29/10/2026 (RFC-005):** el EDT y su Diccionario fueron corregidos para eliminar las contradicciones (60 FPS → ≥ 30 FPS; 500 MB/20 s → < 50 MB/≤ 30 s; export CSV/JSON/MATLAB → solo EDF/EDF+; eliminados calibradores, roles extra y registro/recuperación de credenciales). **La observación queda cerrada.**
