---
project: BioSignal
version: 2
title: "1.3.2.2.C Funcionalidad de editar los metadatos"
aliases:
  - "1.3.2.2.C"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-2-interfaz-de-edicion-de-metadatos-modificacion/index|1.3.2.2 Interfaz de edición de metadatos (modificación)]]

- **Código:** 1.3.2.2.C
- **Actividad:** Funcionalidad de editar los metadatos

## Alcance

Backend que actualiza metadatos, aplica los catálogos y genera el registro de auditoría (autor, fecha, campo modificado)

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: actualización de metadatos 14 h + validación contra catálogos 10 h + registro de auditoría 14 h + prueba de integridad del binario 10 h = 48 h
- **Tiempo estimado:** 48 h
- **Costo estimado:** $480.000
- **Tiempo de prevención:** 5 h
- **Costo de gestión del riesgo:** $50.000
- **Tiempo adicional si ocurre:** 12 h
- **Costo de contingencia si ocurre:** $120.000
- **Duración total:** 65 h
- **Costo total:** $650.000

## Gestión del riesgo

- **Riesgo:** La edición corrompe o reescribe la señal cruda original
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Metadatos en tabla separada, binario de solo lectura y prueba de integridad (hash) antes y después
