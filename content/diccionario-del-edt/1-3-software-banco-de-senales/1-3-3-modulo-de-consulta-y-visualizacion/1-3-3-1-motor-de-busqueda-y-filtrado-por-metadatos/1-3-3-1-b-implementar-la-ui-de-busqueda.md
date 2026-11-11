---
project: BioSignal
version: 2
title: "1.3.3.1.B Implementar la UI de búsqueda"
aliases:
  - "1.3.3.1.B"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/index|1.3.3.1 Motor de búsqueda y filtrado por metadatos]]

- **Código:** 1.3.3.1.B
- **Actividad:** Implementar la UI de búsqueda

## Alcance

Componente web de búsqueda con filtros combinables, chips de criterios activos, limpieza de filtros, paginación y estados de carga, sin resultados y error

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (22 + 4·28 + 34) / 6 = 28 h
- **Tiempo estimado:** 28 h
- **Costo estimado:** $280.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 38 h
- **Costo total:** $380.000

## Gestión del riesgo

- **Riesgo:** Combinaciones de filtros que generan estados inconsistentes o consultas vacías inesperadas
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 3
- **Mitigación (preventiva):** Definir una matriz de combinaciones de filtros y probar casos límite antes de cerrar la UI
