---
project: BioSignal
version: 2
title: "1.5.A Migración de datos y configuración productiva"
aliases:
  - "1.5.A"
---

> Paquete: [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/index|1.5 Sistema desplegado en ambiente de producción]]

- **Código:** 1.5.A
- **Actividad:** Migración de datos y configuración productiva

## Alcance

Migración del esquema y del dataset a la infraestructura productiva, configuración de variables de entorno, dominios institucionales y cuentas iniciales, con verificación de integridad

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·12 + 16) / 6 = 12 h
- **Tiempo estimado:** 12 h
- **Costo estimado:** $120.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 6 h
- **Costo de contingencia si ocurre:** $60.000
- **Duración total:** 20 h
- **Costo total:** $200.000

## Gestión del riesgo

- **Riesgo:** Pérdida o corrupción de datos durante la migración al ambiente productivo
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Ensayo de migración sobre una copia, respaldo previo y verificación del conteo e integridad al finalizar
