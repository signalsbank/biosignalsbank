---
project: BioSignal
version: 2
title: "1.4.1.B Automatización y ejecución de pruebas unitarias"
aliases:
  - "1.4.1.B"
---

> Paquete: [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-1-reporte-de-pruebas-unitarias/index|1.4.1 Reporte de pruebas unitarias]]

- **Código:** 1.4.1.B
- **Actividad:** Automatización y ejecución de pruebas unitarias

## Alcance

Implementación y ejecución de pruebas automatizadas sobre algoritmos de procesamiento de señales, validadores de formato, parseo de metadatos y reglas de negocio del RBAC, integradas al pipeline de CI

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (12 + 4·16 + 20) / 6 = 16 h
- **Tiempo estimado:** 16 h
- **Costo estimado:** $160.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 6 h
- **Costo de contingencia si ocurre:** $60.000
- **Duración total:** 24 h
- **Costo total:** $240.000

## Gestión del riesgo

- **Riesgo:** Pruebas inestables (_flaky_) que reducen la confianza en el pipeline
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 3
- **Mitigación (preventiva):** Aislar dependencias externas, fijar datos de prueba y repetir la suite en el pipeline antes de habilitarla como obligatoria
