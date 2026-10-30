# Informes de Calidad — Proyecto BioSignal

| Campo     | Valor                                                                                                                         |
| --------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Documento | IC-BIOSIG-04                                                                                                                  |
| Versión   | v0.1 (borrador)                                                                                                               |
| Propósito | Estructura estándar y plantillas de los registros que se generan en _Gestionar la Calidad_ y _Controlar la Calidad_ (PMBOK 6) |

> **Aviso:** el proyecto todavía no ejecutó las pruebas. Este documento entrega las **plantillas oficiales** (con los umbrales ya cargados desde las Métricas) y un registro vivo para completar. No contiene resultados inventados: las columnas "Resultado" y "Estado" se completan con la medición real.

## 1. Catálogo de informes

| ID    | Informe                                                    | Proceso PMBOK | Momento                  | Autor        | Destinatario         | Evidencia                                   |
| ----- | ---------------------------------------------------------- | ------------- | ------------------------ | ------------ | -------------------- | ------------------------------------------- |
| IC-01 | Informe de auditoría de proceso y configuración            | 8.2 Gestionar | Fin de cada hito (H1–H7) | APM + QA     | PM / CCB             | Checklists LV-01, LV-09, LV-12; Change Log  |
| IC-02 | Informe de pruebas de rendimiento, carga y compatibilidad  | 8.3 Controlar | Fases 4–5                | QA           | PM, Líderes técnicos | k6/JMeter, Lighthouse, DevTools, Playwright |
| IC-03 | Informe de auditoría forense de cabeceras EDF (privacidad) | 8.3 Controlar | Hito 4 y Hito 6          | QA + Backend | PM, Revisor legal    | Script de auditoría binaria                 |
| IC-04 | Informe de defectos y análisis de tendencia                | 8.3 Controlar | Semanal / por hito       | QA           | Equipo completo      | Gestor de tareas                            |
| IC-05 | **Reporte Consolidado de QA (EJ-04)**                      | 8.3 Controlar | Cierre de Fase 5         | Herrera (QA) | Patrocinador, PM     | Todos los anteriores                        |
| IC-06 | Registro de no conformidades y acciones correctivas        | 8.2 / 8.3     | Continuo                 | QA + APM     | PM                   | Registro NC                                 |
| IC-07 | Informe de pruebas de aceptación (UAT)                     | 8.3 Controlar | Semanas 21–23            | QA           | Patrocinador         | Acta UAT firmada                            |

## 2. Encabezado común de todo informe

```
Proyecto:            BioSignal (UNViMe)
Informe:             IC-0X — <nombre>
Versión / Fecha:     vX.Y / DD-MM-AAAA
Hito / Fase:         <H# / Fase #>
Versión del sistema: <SemVer, commit/tag> — Entorno: <dev | staging | producción>
Autor:               <nombre y rol>
Revisado por:        <nombre y rol>
Distribución:        <grupo receptor según Plan de Comunicaciones>
```

---

## 3. IC-01 — Informe de auditoría de proceso y configuración

**3.1 Alcance auditado:** ☐ Documentación (CI-DOC) ☐ Código (CI-CODE) ☐ Base de datos (CI-DATA) ☐ UI/UX (CI-UI)

**3.2 Verificaciones**

| #   | Verificación                                             | Criterio           | Resultado | Evidencia | Estado |
| --- | -------------------------------------------------------- | ------------------ | --------- | --------- | ------ |
| 1   | Entregables desplegados = versión aprobada en Change Log | 100 % coincidencia |           |           |        |
| 2   | Cambios fuera del proceso formal                         | 0                  |           |           |        |
| 3   | PR con revisión de tercero                               | 100 % (MPR-01)     |           |           |        |
| 4   | Commits directos a `main`/`develop`                      | 0 (MPR-02)         |           |           |        |
| 5   | Migraciones con par up/down                              | 100 % (MP-MA-06)   |           |           |        |
| 6   | Documentos con versión y firma vigentes                  | 100 % (MPR-09)     |           |           |        |
| 7   | Cobertura de trazabilidad                                | 100 % (MPR-10)     |           |           |        |
| 8   | SPI / CPI                                                | ≥ 0,9 (MPR-08)     |           |           |        |

**3.3 No conformidades detectadas:** ver registro IC-06.  
**3.4 Conclusión:** ☐ Conforme ☐ Conforme con observaciones ☐ No conforme  
**3.5 Acciones y responsables:** ______________________

---

## 4. IC-02 — Informe de pruebas de rendimiento, carga y compatibilidad

**4.1 Condiciones de prueba**

| Ítem                  | Valor                                         |
| --------------------- | --------------------------------------------- |
| Entorno / hardware    |                                               |
| Red simulada          | 10 Mbps (RNF-02)                              |
| Archivo(s) de prueba  | tamaño, nº de canales, frecuencia de muestreo |
| Herramienta y versión |                                               |
| Navegador y versión   |                                               |

**4.2 Resultados**

| ID Métrica | Prueba                            | Umbral        | Medición (media / p95) | Resultado        | Evidencia |
| ---------- | --------------------------------- | ------------- | ---------------------- | ---------------- | --------- |
| MP-PE-01   | LCP primer segmento               | ≤ 2,5 s       |                        | ☐ Pasa ☐ No pasa |           |
| MP-PE-02   | FPS paneo/zoom (32 canales)       | ≥ 30 FPS      |                        | ☐ Pasa ☐ No pasa |           |
| MP-PE-03   | Ingesta < 50 MB                   | ≤ 30 s        |                        | ☐ Pasa ☐ No pasa |           |
| MP-PE-04   | 100 usuarios concurrentes         | 0 errores 5xx |                        | ☐ Pasa ☐ No pasa |           |
| MP-PE-05   | Latencia bajo carga               | media < 3 s   |                        | ☐ Pasa ☐ No pasa |           |
| MP-RE-01   | Tasa de errores críticos          | < 1 %         |                        | ☐ Pasa ☐ No pasa |           |
| MP-PE-06   | CPU / RAM servidor                | < 80 %        |                        | ☐ Pasa ☐ No pasa |           |
| MP-CO-01   | Matriz cross-browser              | 100 %         |                        | ☐ Pasa ☐ No pasa |           |
| MP-US-04   | Responsive 32 canales / 1–2 móvil | Cumple        |                        | ☐ Pasa ☐ No pasa |           |

**4.3 Perfil de carga ejecutado:** rampa 10 → 25 → 50 → 100 usuarios, duración por escalón: ____ min; escenario: login → búsqueda → abrir señal → paneo/zoom.

**4.4 Análisis de cuellos de botella y recomendaciones:** ______________________  
**4.5 Conclusión:** ☐ Cumple ☐ Cumple con reservas ☐ No cumple

---

## 5. IC-03 — Informe de auditoría forense de cabeceras EDF

**5.1 Método:** script automatizado que recorre el 100 % de los archivos persistidos, lee la cabecera binaria (campos de 80 bytes de paciente y registro, fecha/hora de inicio), el canal _EDF Annotations_ y los metadatos asociados, y busca datos no permitidos (patrones de nombre, documento, fechas de nacimiento, etiquetas de ID local).  
**5.2 Control cruzado:** lectura con MNE-Python/pyedflib para confirmar que el archivo sigue siendo válido tras la sanitización y que las muestras no cambiaron.

| Verificación                     | Criterio                | Archivos evaluados | Hallazgos | Resultado        |
| -------------------------------- | ----------------------- | ------------------ | --------- | ---------------- |
| Campo paciente (80 bytes)        | Sin PII                 |                    |           | ☐ Pasa ☐ No pasa |
| Campo registro (80 bytes)        | Sin PII                 |                    |           | ☐ Pasa ☐ No pasa |
| Fecha/hora de inicio             | Según política          |                    |           | ☐ Pasa ☐ No pasa |
| Anotaciones EDF+                 | Sin PII                 |                    |           | ☐ Pasa ☐ No pasa |
| Nombre de archivo y metadatos BD | Sin PII                 |                    |           | ☐ Pasa ☐ No pasa |
| Integridad de muestras           | Idénticas al original   |                    |           | ☐ Pasa ☐ No pasa |
| Archivo sentinela                | PII sintética eliminada | 1                  |           | ☐ Pasa ☐ No pasa |

**Indicador global (MP-SE-01):** PII residual = ____ % (umbral 0 %).  
**Dictamen de cumplimiento Ley 25.326 (RNF-05):** ☐ Favorable ☐ Desfavorable — firmado por Revisor Legal/Normativo.  
**Nota de manejo:** el informe **no debe reproducir** datos personales hallados; se referencia solo por ID interno de registro.

---

## 6. IC-04 — Informe de defectos y tendencia

| Periodo  | Nuevos | Cerrados | Abiertos | Críticos abiertos | Mayores abiertos | Reabiertos | DRE (MPR-05) |
| -------- | ------ | -------- | -------- | ----------------- | ---------------- | ---------- | ------------ |
| Semana 1 |        |          |          |                   |                  |            |              |
| …        |        |          |          |                   |                  |            |              |

**Distribución por módulo/severidad:** ______  
**Análisis de Pareto (top 20 % de causas):** ______  
**Causa raíz de defectos críticos/mayores (5 Porqués / Ishikawa):** ______  
**Tendencia y pronóstico de cierre antes del Go/No-Go:** ______

---

## 7. IC-05 — Reporte Consolidado de Aseguramiento de la Calidad (EJ-04)

**7.1 Resumen ejecutivo** (≤ 1 página): estado general (semáforo), principales hallazgos, recomendación Go / No-Go.

**7.2 Cobertura de verificación de requisitos**

| Grupo         | Total | Verificados | Pasa | No pasa | Pendiente |
| ------------- | ----- | ----------- | ---- | ------- | --------- |
| RF-01…RF-14   | 14    |             |      |         |           |
| RNF-01…RNF-09 | 9     |             |      |         |           |
| RT-01, RT-02  | 2     |             |      |         |           |
| RP-01…RP-03   | 3     |             |      |         |           |

**7.3 Cumplimiento de criterios de aceptación (§4 del Enunciado)**

| Criterio            | Umbral                                | Resultado | Fuente            | Estado |
| ------------------- | ------------------------------------- | --------- | ----------------- | ------ |
| Tiempo de respuesta | ≤ 2,5 s (≥ 10 Mbps)                   |           | IC-02             |        |
| Fluidez             | ≥ 30 FPS                              |           | IC-02             |        |
| Concurrencia        | 100 usuarios sin fallas               |           | IC-02             |        |
| Tiempo de ingesta   | ≤ 30 s (< 50 MB)                      |           | IC-02             |        |
| Privacidad          | 0 % PII residual                      |           | IC-03             |        |
| Calidad de software | 0 críticos/bloqueantes                |           | IC-04             |        |
| Dataset semilla     | ≥ 30 EDF (≥ 15 ECG, ≥ 15 EEG)         |           | Inventario BD     |        |
| Despliegue y cierre | `*.unvime.edu.ar` + acta ≤ 15/02/2027 |           | Acta              |        |
| Adopción académica  | ≥ 2 programas de cátedra              |           | Planes de cátedra |        |

**7.4 Pruebas ejecutadas:** unitarias (cobertura ___ %), integración, E2E, carga, seguridad (ZAP, dependencias, TLS), cross-browser, usabilidad (Time-on-Task ___ min; SUS ___), UAT.  
**7.5 Telemetría de tiempos de respuesta:** adjuntar gráficos (LCP, latencia p50/p95, FPS).  
**7.6 Seguridad y privacidad:** resumen de IC-03 y escaneos.  
**7.7 Defectos pendientes y riesgos residuales:** tabla con ID, severidad, plan.  
**7.8 Desviaciones respecto del plan de calidad y justificación.**  
**7.9 Recomendación al PM:** ☐ GO ☐ NO-GO ☐ GO condicionado.  
**7.10 Anexos:** logs, reportes de herramientas, checklists LV-01…LV-13 completadas.

---

## 8. IC-06 — Registro de no conformidades (NC) y acciones

| ID NC  | Fecha | Origen (auditoría/prueba/PR) | Requisito/Norma incumplida | Severidad | Descripción | Causa raíz | Acción correctiva | Responsable | Fecha límite | Verificación | Estado  |
| ------ | ----- | ---------------------------- | -------------------------- | --------- | ----------- | ---------- | ----------------- | ----------- | ------------ | ------------ | ------- |
| NC-001 |       |                              |                            |           |             |            |                   |             |              |              | Abierta |

Estados: Abierta → En corrección → En verificación → Cerrada / Reabierta.  
Toda NC que modifique una línea base genera un RFC en el Change Log.

## 9. IC-07 — Informe de pruebas de aceptación (UAT)

| Dato                                                | Valor                                                                                           |
| --------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Fecha(s) / lugar                                    |                                                                                                 |
| Evaluadores designados (docentes, GAB, estudiantes) |                                                                                                 |
| Escenarios                                          | Buscar señal · abrir · configurar escala 25 mm/s y 10 mm/mV · reordenar canales · descargar EDF |
| Casos ejecutados / aprobados                        |                                                                                                 |
| Time-on-Task medio (RNF-09)                         |                                                                                                 |
| SUS                                                 |                                                                                                 |
| Incidencias                                         |                                                                                                 |
| Aprobación (100 % de evaluadores)                   | ☐ Sí ☐ No                                                                                       |

Firmas: ______________________

---

## 10. Tablero de calidad (resumen por hito)

| Hito                    | Informe(s)                 | Semáforo | Fecha emisión | Estado    |
| ----------------------- | -------------------------- | -------- | ------------- | --------- |
| H1 Acta de Constitución | Revisión documental        |          |               | Pendiente |
| H2 Requisitos aprobados | IC-01                      |          |               | Pendiente |
| H3 Autenticación        | IC-01, IC-04               |          |               | Pendiente |
| H4 Gestión de señales   | IC-01, IC-03, IC-04        |          |               | Pendiente |
| H5 Visualizador         | IC-01, IC-02, IC-04        |          |               | Pendiente |
| H6 Despliegue           | IC-02, IC-03, IC-05, IC-07 |          |               | Pendiente |
| H7 Cierre               | IC-01 (final), IC-05 final |          |               | Pendiente |

Semáforo: 🟢 conforme · 🟡 conforme con observaciones · 🔴 no conforme (bloquea el hito).

## 11. Ciclo de aprobación de informes

Elaboración (autor) → revisión (Process Owner / Líder técnico) → aprobación (PM) → publicación en repositorio central → comunicación por reunión semanal de QA o Informe de Hito al Patrocinador. Solo la versión publicada es vigente (Plan SCM §2.3).
