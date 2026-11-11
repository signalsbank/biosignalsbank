---
project: BioSignal
version: 2
title: "1.3.3.3.B Implementar la UI de descarga"
aliases:
  - "1.3.3.3.B"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/index|1.3.3.3 Herramienta de exportación de registros]]

- **Código:** 1.3.3.3.B
- **Actividad:** Implementar la UI de descarga

## Alcance

Botón de descarga con confirmación, indicador de progreso, manejo de error y cancelación, y presentación del hash del archivo descargado

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (12 + 4·16 + 20) / 6 = 16 h
- **Tiempo estimado:** 16 h
- **Costo estimado:** $160.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 5 h
- **Costo de contingencia si ocurre:** $50.000
- **Duración total:** 23 h
- **Costo total:** $230.000

## Gestión del riesgo

- **Riesgo:** Estados de progreso, error y cancelación mal gestionados que dejan la pantalla bloqueada
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 3
- **Mitigación (preventiva):** Reutilizar los componentes de estado de la carga (1.3.2.1) y probar interrupciones
