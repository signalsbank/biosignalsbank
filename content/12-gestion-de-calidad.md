---
project: BioSignal
version: 2.0
title: 12. Gestión de Calidad
aliases:
  - "Gestión de Calidad"
  - "Calidad"
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-11-10
---

# Gestión de la calidad — BioSignal

Este documento evalúa la calidad de BioSignal en cuatro dimensiones: **producto** (ISO/IEC 25010), **servicio** (ISO/IEC 20000-1), **procesos del ciclo de vida** (ISO/IEC/IEEE 12207) y **madurez del proceso** (ISO/IEC 33000). El alcance comprende los entregables de software [[04-enunciado-del-alance-del-proyecto#3.1. Entregables del Producto (Software)|EP-01 a EP-06]] y la puesta en servicio en la UNViMe.

| Dimensión     | Norma              | Pregunta que responde                                                   | Sección |
| :------------ | :----------------- | :---------------------------------------------------------------------- | :-----: |
| Producto      | ISO/IEC 25010:2023 | ¿El software cumple los atributos de calidad acordados?                 |    1    |
| Servicio      | ISO/IEC 20000-1    | ¿Puede operarse, monitorearse y transferirse?                           |    2    |
| Ciclo de vida | ISO/IEC/IEEE 12207 | ¿Están definidos los procesos de transición, operación y mantenimiento? |    3    |
| Proceso       | ISO/IEC 33000      | ¿Qué nivel de madurez tiene el proceso clave?                           |    4    |

## 1. Calidad del producto (ISO/IEC 25010)

Se adoptan los niveles **ALTA / MEDIA / BAJA**. **ALTA** exige verificar todas las subcaracterísticas aplicables; **MEDIA**, las críticas para el alcance; **BAJA**, solo el comportamiento básico. **Capacidad de interacción** y **seguridad** son prioritarias por su impacto en la adopción y en la protección de datos personales.

| Característica (ISO/IEC 25010) | Subcaracterísticas aplicables                                                                      |       Nivel        | Evidencia / criterio de aceptación                                                                                                                                                                                                                                                                            |
| :----------------------------- | :------------------------------------------------------------------------------------------------- | :----------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Adecuación funcional**       | Completitud, corrección y pertinencia funcional                                                    |        ALTA        | [[03-especificacion-de-requisitos#3. Requisitos Funcionales\|RF-01 a RF-14]] implementados y trazados; 100 % de casos de aceptación críticos aprobados.                                                                                                                                                       |
| **Eficiencia de desempeño**    | Comportamiento temporal, utilización de recursos y capacidad                                       |     MEDIA/ALTA     | TTIS ≤ 2,5 s ([[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-02]]); ≥ 30 FPS (RNF-03); ingesta ≤ 30 s para EDF < 50 MB (RNF-04); 100 usuarios concurrentes (RNF-01).                                                                                                                     |
| **Compatibilidad**             | Coexistencia e interoperabilidad                                                                   |    ALTA / BAJA     | 100 % de la matriz cross-browser ([[03-especificacion-de-requisitos#4.3. Compatibilidad y Portabilidad\|RNF-07]]); importación y exportación EDF/EDF+.                                                                                                                                                        |
| **Capacidad de interacción**   | Reconocibilidad, aprendibilidad, operabilidad, protección contra errores, estética y accesibilidad | ALTA (prioritaria) | Tarea “buscar–abrir–configurar” < 5 min ([[03-especificacion-de-requisitos#4.4. Usabilidad\|RNF-09]]); WCAG 2.1 AA ([[03-especificacion-de-requisitos#4.5. Disponibilidad, Respaldo, Accesibilidad, Auditoría, Mantenibilidad y Seguridad (RNF adicionales)\|RNF-12]]); ≥ 90 % de éxito en prueba de usuario. |
| **Fiabilidad**                 | Ausencia de defectos, disponibilidad, tolerancia a fallos y recuperabilidad                        |     MEDIA/ALTA     | Uptime ≥ 99,9 % ([[03-especificacion-de-requisitos#4.5. Disponibilidad, Respaldo, Accesibilidad, Auditoría, Mantenibilidad y Seguridad (RNF adicionales)\|RNF-10]]); backup diario, RTO ≤ 4 h y RPO ≤ 24 h (RNF-11).                                                                                          |
| **Seguridad**                  | Confidencialidad, integridad, no repudio, responsabilidad y autenticidad                           | ALTA (prioritaria) | Anonimización irreversible y 0 PII ([[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros\|RF-06]], [[03-especificacion-de-requisitos#4.2. Seguridad y Privacidad\|RNF-05]]); TLS 1.3 (RNF-06); RBAC, auditoría (RNF-13) y sesión de 30 min (RNF-15).                          |
| **Mantenibilidad**             | Modularidad, reutilizabilidad, analizabilidad, modificabilidad y testabilidad                      |        ALTA        | Cobertura > 80 % de líneas y ≥ 70 % de ramas; lint/tipado limpio; complejidad ciclomática ≤ 10 ([[03-especificacion-de-requisitos#4.5. Disponibilidad, Respaldo, Accesibilidad, Auditoría, Mantenibilidad y Seguridad (RNF adicionales)\|RNF-14]]).                                                           |
| **Flexibilidad**               | Adaptabilidad, escalabilidad, instalabilidad y reemplazabilidad                                    |        BAJA        | Docker Compose; despliegue reproducible; responsive con 32 canales en escritorio y 1–2 en móvil ([[03-especificacion-de-requisitos#4.3. Compatibilidad y Portabilidad\|RNF-08]]).                                                                                                                             |
| **Protección (safety)**        | Restricción operacional, identificación de riesgos, falla segura y advertencia de peligro          |     MEDIA/BAJA     | Uso académico, no diagnóstico; advertencias de alcance y validación de cabeceras EDF.                                                                                                                                                                                                                         |

**Verificación:** pruebas unitarias y de integración (pytest, Jest), E2E (Playwright), carga (k6), seguridad (OWASP ZAP, pip-audit, testssl.sh), accesibilidad (Lighthouse/axe) y auditoría binaria de archivos EDF.

## 2. Calidad del servicio (ISO/IEC 20000-1)

Se evalúa la operación y gobernanza del servicio que se transferirá a la Dirección TIC de la UNViMe. Escala: **C** = cumple, **P** = parcial, **NC** = no cumple.

| Práctica                        | Estado | Evidencia / situación actual                                                                                                                                                                                          | Acción requerida                                                                |
| :------------------------------ | :----: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------ |
| **Gobierno del servicio**       |   P    | Roles de PM, RDS y Dirección TIC definidos; falta formalizar el dueño del servicio transferido.                                                                                                                       | Designar responsable del servicio en el Acta de Despliegue.                     |
| **Relaciones y acuerdos (SLA)** |   P    | SLA definido en el [[08-gestion-de-adquisiciones\|documento 08]] (disponibilidad 99,9 %, RTO ≤ 4 h, RPO ≤ 24 h); pendiente de firma.                                                                                  | Formalizarlo en el Acta de Despliegue.                                          |
| **Incidencias y problemas**     |   NC   | No hay proceso formalizado.                                                                                                                                                                                           | Definir canal, categorías, prioridades y responsable antes de la transferencia. |
| **Cambios y releases**          |   C    | Plan SCM para software propio: RFC, staging, rollback y registro de la versión desplegada; no hay software de terceros.                                                                                               | Mantener el registro por release.                                               |
| **Capacidad y disponibilidad**  |   P    | Dependen de [[03-especificacion-de-requisitos#6. Requisitos y Restricciones del Proyecto\|RP-01]] y del monitoreo de uptime.                                                                                          | Monitorear recursos, alertas y escalamiento al patrocinador.                    |
| **Continuidad y respaldo**      |   P    | Backup diario y restore definidos en [[03-especificacion-de-requisitos#4.5. Disponibilidad, Respaldo, Accesibilidad, Auditoría, Mantenibilidad y Seguridad (RNF adicionales)\|RNF-11]]; falta probar la restauración. | Entregar política de respaldo y evidencia de restore probado.                   |
| **Gestión de la configuración** |   C    | Versión desplegada = versión aprobada en el Change Log.                                                                                                                                                               | Verificar en cada release.                                                      |
| **Mejora continua**             |   P    | Ciclo PDCA definido; sin serie histórica de métricas.                                                                                                                                                                 | Revisar indicadores al cierre de cada hito y registrar acciones.                |

**Resultado:** 2 prácticas cumplen, 5 son parciales y 1 no cumple. La brecha crítica es el proceso de incidencias, que debe formalizarse antes de la transferencia. Indicadores de servicio: disponibilidad ≥ 99,9 %, RTO ≤ 4 h, RPO ≤ 24 h y 100 % de cambios documentados.

**Criterios de puesta en servicio:**

- Release candidate etiquetado (SemVer) y aprobado en el Change Log, sin defectos críticos/bloqueantes y con recomendación escrita de QA.
- Rollback documentado y probado; TLS válido; backups programados; secretos fuera del código.
- Infraestructura UNViMe verificada: credenciales, subdominio `*.unvime.edu.ar` y ≥ 100 GB de almacenamiento ([[03-especificacion-de-requisitos#6. Requisitos y Restricciones del Proyecto|RP-01]]).
- Dataset semilla ≥ 30 EDF catalogados y auditoría binaria con 0 PII.
- Prueba de humo completa: login, carga, búsqueda, visualización y descarga.
- Canal de incidencias, monitoreo y procedimiento de cambio entregados a la Dirección TIC.

## 3. Procesos de transición, operación y mantenimiento (ISO/IEC/IEEE 12207)

| Grupo             | Proceso               | Cómo se aplica en BioSignal                                                         | Evidencia                                          |
| :---------------- | :-------------------- | :---------------------------------------------------------------------------------- | :------------------------------------------------- |
| **Transición**    | Instalación           | Despliegue del release candidate en el servidor UNViMe con Docker Compose.          | Acta de despliegue y checklist de pre-despliegue.  |
| **Transición**    | Apoyo a la aceptación | UAT con docentes y GAB; aceptación formal del patrocinador.                         | Informe de UAT y acta de aceptación.               |
| **Transición**    | Transición            | Transferencia de credenciales, monitoreo y canal de incidencias a la Dirección TIC. | Acta de transferencia y checklist de entrega.      |
| **Operación**     | Operación             | Servicio en producción con monitoreo de uptime, recursos y backups.                 | Panel de monitoreo e indicadores de servicio.      |
| **Operación**     | Soporte operativo     | Atención de incidencias y consultas del servicio transferido.                       | Canal de incidencias y registro de tickets.        |
| **Operación**     | Servicio al usuario   | Comunicación de disponibilidad, alcance y limitaciones a los usuarios.              | Avisos institucionales y documentación publicada.  |
| **Mantenimiento** | Mantenimiento         | Correcciones, parches de seguridad y mejoras posteriores al cierre.                 | RFC, ramas `bugfix/*` y releases SemVer.           |
| **Mantenimiento** | Logística             | Gestión de dependencias, backups y renovación de servicios.                         | Inventario de dependencias y política de respaldo. |

## 4. Evaluación del proceso (ISO/IEC 33000)

Se selecciona el proceso de **Verificación y QA** porque concentra la evidencia de calidad del proyecto: plan de pruebas, revisión de PR, CI, auditorías y reportes de calidad.

| Nivel | Descripción                                                   |    Estado     | Evidencia / justificación                                                        |
| :---: | :------------------------------------------------------------ | :-----------: | :------------------------------------------------------------------------------- |
| **0** | Incompleto: no se ejecuta o no logra sus salidas              |      No       | El proceso existe y produce resultados.                                          |
| **1** | Ejecutado: resultados reactivos/artesanales                   |   Superado    | Hay pruebas unitarias, integración, E2E y revisión de PR.                        |
| **2** | Gestionado: se planifica, monitorea y ajusta                  | **Alcanzado** | Plan de pruebas, CI, umbrales, reporte consolidado de QA y registro de defectos. |
| **3** | Establecido: proceso estándar definido a nivel organizacional |    Parcial    | La guía es del proyecto; aún no está institucionalizada para otros proyectos.    |
| **4** | Predecible: límites de control cuantitativos y estadísticos   |      No       | No hay series históricas ni control estadístico del proceso.                     |
| **5** | En optimización: mejora continua basada en causas comunes     |      No       | Se aplica PDCA, pero sin análisis cuantitativo de variación.                     |

**Resultado: Nivel 2 (Gestionado).** El proceso se planifica, monitorea y ajusta, pero falta convertirlo en estándar organizacional y medirlo con series históricas. **Acción:** documentar el proceso de verificación como plantilla reutilizable, definir una línea base de defectos y revisar los indicadores al cierre de cada hito. **Meta:** Nivel 3 al cierre del proyecto.

## 5. Síntesis

| Dimensión | Resultado                                                                                                   |
| :-------- | :---------------------------------------------------------------------------------------------------------- |
| Producto  | 9 características evaluadas; capacidad de interacción y seguridad son prioritarias.                         |
| Servicio  | 2 prácticas conformes, 5 parciales y 1 no conforme; formalizar incidencias y SLA antes de la transferencia. |
| Procesos  | Transición, operación y mantenimiento definidos con evidencia por hito.                                     |
| Madurez   | Nivel 2 (Gestionado) en Verificación y QA; meta Nivel 3 al cierre.                                          |
