---
project: BioSignal
version: 1.0
title: "Resultados PM-03 — Documentación de migraciones (Eber Chiecher)"
aliases:
  - "Resultado PM-03"
  - "Evaluación PM-03"
  - "Migraciones de esquema Eber"
authors: Mateo Astudillo, Ignacio Ávila
date: 2027-01-08
---

# Resultados PM-03 — Documentación de migraciones (Eber Chiecher)

> **Plan evaluado:** [[11-matriz-de-competencias#Plan de Mejora de Competencias|PM-03]] · **Tipo:** Capacitación · **Responsable:** Eber Chiecher + PM · **Plazo:** 31/12/2026 · **Evaluación:** 08/01/2027

## 1. Brecha y acción

| Campo                 | Detalle                                                                |
| :-------------------- | :--------------------------------------------------------------------- |
| **Brecha**            | Documentación previa insuficiente en cambios de esquema.               |
| **Acción**            | Usar plantilla de migración y avisar cambios con 48 h de anticipación. |
| **Indicador**         | 100 % de migraciones con up/down y aviso previo registrado.            |
| **Costo planificado** | 3 h · ARS 30.000 · USD 0 de caja.                                      |

## 2. Línea base

| Métrica                                  | Línea base | Fuente                                                                   |
| :--------------------------------------- | :--------- | :----------------------------------------------------------------------- |
| Migraciones de octubre sin script `down` | 2 de 3     | Registro de migraciones, octubre 2026                                    |
| Migraciones con aviso previo de 48 h     | 0 de 3     | Ibídem                                                                   |
| RDS de Eber                              | 3,80       | [[13-evaluaciones-de-desempeño\|Evaluación 360° preliminar]], 23/10/2026 |

## 3. Acciones ejecutadas

- **14/11/2026:** creación de la plantilla de migración con `up`, `down`, impacto, riesgo y plan de rollback.
- **21/11/2026:** acuerdo de aviso a backend, frontend y QA con 48 h de anticipación.
- **05/12/2026:** incorporación del checklist de migración al PR y revisión conjunta con el PM.
- **18/12/2026:** cierre de la capacitación y revisión de las migraciones del período.

## 4. Evidencia

| Evidencia                              | Resultado                   | Fuente                                         |
| :------------------------------------- | :-------------------------- | :--------------------------------------------- |
| Migraciones de noviembre a enero       | 5                           | Registro de migraciones, 01/11/2026–31/01/2027 |
| Migraciones con `up` y `down` probados | 5 de 5 (100 %)              | Ibídem                                         |
| Migraciones con aviso previo ≥ 48 h    | 5 de 5 (100 %); mínimo 52 h | Ibídem                                         |
| Rollbacks o incidentes de esquema      | 0                           | Registro de incidentes                         |

## 5. Resultado frente al indicador

| Indicador                               | Meta  | Resultado   | Cumplimiento |
| :-------------------------------------- | :---- | :---------- | :----------: |
| Migraciones con `up` y `down`           | 100 % | 100 % (5/5) |      Sí      |
| Migraciones con aviso previo registrado | 100 % | 100 % (5/5) |      Sí      |
| Rollbacks o incidentes de esquema       | 0     | 0           |      Sí      |

**Dictamen: Eficaz.** La plantilla y el aviso previo eliminaron el retrabajo en los cambios de esquema.

## 6. Costos

| Concepto                     | Planificado |  Ejecutado | Variación |
| :--------------------------- | ----------: | ---------: | --------: |
| Horas de esfuerzo            |         3 h |        3 h | 0 h (0 %) |
| Costo interno (ARS 10.000/h) |  ARS 30.000 | ARS 30.000 |     ARS 0 |
| Caja (USD)                   |       USD 0 |      USD 0 |         0 |

El plan se ejecutó con el esfuerzo estimado y sin compras.

## 7. Decisión y seguimiento

- **Brecha cerrada.** La plantilla de migración queda como estándar del repositorio y se incorpora a la Definition of Done.
- Eber mantiene el rol de DBA/Infraestructura y revisa las migraciones antes de cada release.
- **Lección:** el aviso previo de 48 h fue más efectivo que la revisión posterior; el costo de coordinación fue mínimo.

## 8. Trazabilidad

- Plan: [[11-matriz-de-competencias#Plan de Mejora de Competencias|Documento 11 — Plan de Mejora de Competencias]]
- Línea base: [[13-evaluaciones-de-desempeño|Documento 13 — Evaluaciones de desempeño]]
- Ficha: [[evaluaciones-de-desempeno/ficha-integral-eber-chiecher|Ficha integral de Eber Chiecher]]
- Tablero: [[evaluacion-de-planes/index|Evaluación de Planes de Mejora]]
