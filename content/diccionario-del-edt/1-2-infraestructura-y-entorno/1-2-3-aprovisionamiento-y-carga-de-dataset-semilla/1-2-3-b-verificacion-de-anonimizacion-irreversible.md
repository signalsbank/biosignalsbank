---
project: BioSignal
version: 2
title: "1.2.3.B Verificación de anonimización irreversible"
aliases:
  - "1.2.3.B"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/index|1.2.3 Aprovisionamiento y carga de dataset semilla]]

- **Código:** 1.2.3.B
- **Actividad:** Verificación de anonimización irreversible

## Alcance

Revisión de cabeceras, anotaciones TAL y metadatos para eliminar información personal identificable; documentación de la evidencia de anonimización por registro antes de su carga

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·8 + 12) / 6 = 8 h
- **Tiempo estimado:** 8 h
- **Costo estimado:** $80.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 6 h
- **Costo de contingencia si ocurre:** $60.000
- **Duración total:** 16 h
- **Costo total:** $160.000

## Gestión del riesgo

- **Riesgo:** PII residual no detectada en cabecera, TAL o metadatos
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Checklist de campos identificables y revisión cruzada por un segundo integrante antes de aprobar cada lote
