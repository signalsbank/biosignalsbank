---
project: BioSignal
version: 2
title: "1.2.3.A Recolección y selección de registros EDF"
aliases:
  - "1.2.3.A"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/index|1.2.3 Aprovisionamiento y carga de dataset semilla]]

- **Código:** 1.2.3.A
- **Actividad:** Recolección y selección de registros EDF

## Alcance

Obtención de 30 registros EDF/EDF+ (15 ECG y 15 EEG) desde el GAB o, como respaldo, desde PhysioNet o generación sintética; verificación de formato, canales, frecuencia de muestreo y legibilidad

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·12 + 16) / 6 = 12 h
- **Tiempo estimado:** 12 h
- **Costo estimado:** $120.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 22 h
- **Costo total:** $220.000

## Gestión del riesgo

- **Riesgo:** Demora o faltante en la entrega de EDF por parte del GAB (R-01)
- **Probabilidad (1-5):** 4
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Iniciar en paralelo la búsqueda de señales en PhysioNet y la generación de registros sintéticos desde la semana 1
