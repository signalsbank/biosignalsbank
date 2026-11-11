---
project: BioSignal
version: 2
title: "1.4.2.B Pruebas de estrés y rendimiento"
aliases:
  - "1.4.2.B"
---

> Paquete: [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-2-reporte-de-pruebas-de-integracion-y-aceptacion/index|1.4.2 Reporte de pruebas de integración y aceptación]]

- **Código:** 1.4.2.B
- **Actividad:** Pruebas de estrés y rendimiento

## Alcance

Pruebas de concurrencia con 100 usuarios, verificación de TTIS ≤ 2,5 s, fluidez ≥ 30 FPS en paneo y zoom, y carga de EDF de menos de 50 MB en ≤ 30 s

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·12 + 16) / 6 = 12 h
- **Tiempo estimado:** 12 h
- **Costo estimado:** $120.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 6 h
- **Costo de contingencia si ocurre:** $60.000
- **Duración total:** 20 h
- **Costo total:** $200.000

## Gestión del riesgo

- **Riesgo:** No alcanzar los umbrales RNF-01, RNF-02, RNF-03 o RNF-04 en el ambiente de pruebas
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Escenarios de carga reproducibles y medición temprana en cada release para detectar regresiones de rendimiento
