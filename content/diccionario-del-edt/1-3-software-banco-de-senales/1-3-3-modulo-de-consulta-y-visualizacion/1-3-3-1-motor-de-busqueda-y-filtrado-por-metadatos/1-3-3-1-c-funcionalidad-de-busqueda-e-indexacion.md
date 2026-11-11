---
project: BioSignal
version: 2
title: "1.3.3.1.C Funcionalidad de búsqueda e indexación"
aliases:
  - "1.3.3.1.C"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/index|1.3.3.1 Motor de búsqueda y filtrado por metadatos]]

- **Código:** 1.3.3.1.C
- **Actividad:** Funcionalidad de búsqueda e indexación

## Alcance

Backend de indexación de metadatos y consulta multicriterio con paginación y ordenamiento; excluye los registros dados de baja y aplica los permisos del rol Consultor sin exponer datos identificatorios

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: indexación de metadatos 12 h + consulta multicriterio 14 h + paginación y ordenamiento 10 h + pruebas de rendimiento 12 h = 48 h
- **Tiempo estimado:** 48 h
- **Costo estimado:** $480.000
- **Tiempo de prevención:** 5 h
- **Costo de gestión del riesgo:** $50.000
- **Tiempo adicional si ocurre:** 12 h
- **Costo de contingencia si ocurre:** $120.000
- **Duración total:** 65 h
- **Costo total:** $650.000

## Gestión del riesgo

- **Riesgo:** Consultas que superan los 500 ms o se degradan al escalar a 1.000 registros indexados
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Índices sobre los campos de filtrado y benchmark con 1.000 registros sintéticos
