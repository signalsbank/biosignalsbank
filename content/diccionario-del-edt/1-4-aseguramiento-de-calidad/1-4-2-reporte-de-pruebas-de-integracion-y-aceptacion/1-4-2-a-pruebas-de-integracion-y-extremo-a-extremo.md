---
project: BioSignal
version: 2
title: "1.4.2.A Pruebas de integración y extremo a extremo"
aliases:
  - "1.4.2.A"
---

> Paquete: [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-2-reporte-de-pruebas-de-integracion-y-aceptacion/index|1.4.2 Reporte de pruebas de integración y aceptación]]

- **Código:** 1.4.2.A
- **Actividad:** Pruebas de integración y extremo a extremo

## Alcance

Ejecución de flujos completos de autenticación, carga, búsqueda, visualización y exportación, verificando la integración entre módulos y el tratamiento de errores de borde

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

- **Riesgo:** Defectos de integración detectados tarde, próximos al cierre de QA
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Ejecutar flujos E2E sobre cada release candidato y mantener una lista priorizada de defectos bloqueantes
