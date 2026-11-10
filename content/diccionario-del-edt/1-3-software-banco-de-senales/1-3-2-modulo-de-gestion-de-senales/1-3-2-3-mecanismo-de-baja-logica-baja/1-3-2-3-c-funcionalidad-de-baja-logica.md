---
project: BioSignal
version: 2
title: "1.3.2.3.C Funcionalidad de baja lógica"
aliases:
  - "1.3.2.3.C"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-3-mecanismo-de-baja-logica-baja/index|1.3.2.3 Mecanismo de baja lógica (baja)]]

- **Código:** 1.3.2.3.C
- **Actividad:** Funcionalidad de baja lógica

## Alcance

Baja lógica, guarda fecha y motivo, excluye bajas de las búsquedas y permite la restauración por administradores

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: bandera y migración 4 h + registro de fecha y motivo 4 h + filtro en búsquedas 5 h + restauración 5 h = 18 h
- **Tiempo estimado:** 18 h
- **Costo estimado:** $180.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 24 h
- **Costo total:** $240.000

## Gestión del riesgo

- **Riesgo:** Registros dados de baja que siguen apareciendo en consultas
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Filtro único en la capa de consulta y pruebas de búsqueda
