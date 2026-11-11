---
project: BioSignal
version: 2
title: "1.5.C Pruebas de humo y pase a producción"
aliases:
  - "1.5.C"
---

> Paquete: [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/index|1.5 Sistema desplegado en ambiente de producción]]

- **Código:** 1.5.C
- **Actividad:** Pruebas de humo y pase a producción

## Alcance

Ejecución de pruebas de humo sobre los flujos críticos en producción, verificación de acceso público y privado, y pase formal dentro de la ventana de mantenimiento acordada

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·8 + 12) / 6 = 8 h
- **Tiempo estimado:** 8 h
- **Costo estimado:** $80.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 14 h
- **Costo total:** $140.000

## Gestión del riesgo

- **Riesgo:** Falla en producción que obliga a revertir el despliegue fuera de la ventana prevista
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Plan de reversión documentado y smoke test ejecutado primero en staging sobre la misma versión
