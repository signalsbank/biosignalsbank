---
project: BioSignal
version: 1.0
title: "Resultados PM-05 — Pruebas de integración (equipo)"
aliases:
  - "Resultado PM-05"
  - "Evaluación PM-05"
  - "Taller de pruebas integradas"
authors: Mateo Astudillo, Ignacio Ávila
date: 2027-02-05
---

# Resultados PM-05 — Pruebas de integración (equipo)

> **Plan evaluado:** [[11-matriz-de-competencias#Plan de Mejora de Competencias|PM-05]] · **Tipo:** Capacitación · **Responsable:** Germán Herrera + Eber Chiecher · **Plazo:** 31/01/2027 · **Evaluación:** 05/02/2027

## 1. Brecha y acción

| Campo                 | Detalle                                                 |
| :-------------------- | :------------------------------------------------------ |
| **Brecha**            | Cobertura irregular de pruebas de integración.          |
| **Acción**            | Taller corto de pytest/Testcontainers y revisión en PR. |
| **Indicador**         | Cobertura > 80 % en lógica crítica y 0 fallas en CI.    |
| **Costo planificado** | 12 h · ARS 120.000 · USD 0 de caja.                     |

## 2. Línea base

| Métrica                                   | Línea base | Fuente                          |
| :---------------------------------------- | :--------- | :------------------------------ |
| Cobertura de lógica crítica               | 61 %       | Reporte de QA, noviembre 2026   |
| Fallas de CI en noviembre                 | 4          | Historial de CI, noviembre 2026 |
| Pruebas de integración con Testcontainers | 0 %        | Ibídem                          |

## 3. Acciones ejecutadas

- **09/01/2027:** sesión 1 — estructura de pruebas de integración y pytest.
- **16/01/2027:** sesión 2 — Testcontainers y base de datos efímera.
- **23/01/2027:** sesión 3 — integración en CI y revisión de PR.
- **24/01 al 31/01/2027:** acompañamiento en la migración de pruebas y revisión de cobertura.

Las 12 h corresponden a preparación, dictado y seguimiento de Germán y Eber; la asistencia del equipo se computa dentro de su jornada de trabajo.

## 4. Evidencia

| Evidencia                                  | Resultado | Fuente                                 |
| :----------------------------------------- | :-------- | :------------------------------------- |
| Cobertura de lógica crítica                | 84 %      | Reporte de cobertura, 31/01/2027       |
| Fallas de CI en las últimas 25 ejecuciones | 0         | Historial de CI, 15/12/2026–31/01/2027 |
| Pruebas de integración con Testcontainers  | 100 %     | Configuración del repositorio          |
| Pruebas inestables corregidas              | 2         | Registro de defectos                   |

## 5. Resultado frente al indicador

| Indicador                   | Meta   | Resultado | Cumplimiento |
| :-------------------------- | :----- | :-------- | :----------: |
| Cobertura de lógica crítica | > 80 % | 84 %      |      Sí      |
| Fallas de CI                | 0      | 0         |      Sí      |

**Dictamen: Eficaz.** El taller y la revisión en PR sostuvieron la cobertura y eliminaron las fallas de CI en el período medido.

## 6. Costos

| Concepto                     | Planificado |   Ejecutado | Variación |
| :--------------------------- | ----------: | ----------: | --------: |
| Horas de esfuerzo            |        12 h |        12 h | 0 h (0 %) |
| Costo interno (ARS 10.000/h) | ARS 120.000 | ARS 120.000 |     ARS 0 |
| Caja (USD)                   |       USD 0 |       USD 0 |         0 |

El taller se dictó con herramientas open source y sin compras.

## 7. Decisión y seguimiento

- **Brecha cerrada.** El umbral de cobertura > 80 % queda como condición de merge en CI.
- Se revisa la evolución de la cobertura en cada release y se repite el taller solo si baja del umbral.
- **Lección:** la métrica debe estar en el pipeline; una capacitación sin gate se diluye en pocas semanas.

## 8. Trazabilidad

- Plan: [[11-matriz-de-competencias#Plan de Mejora de Competencias|Documento 11 — Plan de Mejora de Competencias]]
- Línea base: [[13-evaluaciones-de-desempeño|Documento 13 — Evaluaciones de desempeño]]
- Calidad: [[12-gestion-de-calidad|Documento 12 — Gestión de Calidad]]
- Tablero: [[evaluacion-de-planes/index|Evaluación de Planes de Mejora]]
