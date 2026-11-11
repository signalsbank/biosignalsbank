---
project: BioSignal
version: 2
title: "1.5.B Certificados, respaldos y monitoreo productivo"
aliases:
  - "1.5.B"
---

> Paquete: [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/index|1.5 Sistema desplegado en ambiente de producción]]

- **Código:** 1.5.B
- **Actividad:** Certificados, respaldos y monitoreo productivo

## Alcance

Configuración de TLS 1.3 en el dominio institucional, respaldo diario con RTO ≤ 4 h y RPO ≤ 24 h, monitoreo de disponibilidad y alertas para el régimen operativo

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

- **Riesgo:** Respaldo no restaurable o monitoreo incompleto que afecta la disponibilidad
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Prueba de restauración completa y validación de alertas antes de declarar la puesta en producción
