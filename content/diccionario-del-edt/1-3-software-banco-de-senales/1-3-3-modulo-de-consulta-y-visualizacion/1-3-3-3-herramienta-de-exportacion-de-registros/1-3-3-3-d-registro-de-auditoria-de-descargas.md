---
project: BioSignal
version: 2
title: "1.3.3.3.D Registro de auditoría de descargas"
aliases:
  - "1.3.3.3.D"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/index|1.3.3.3 Herramienta de exportación de registros]]

- **Código:** 1.3.3.3.D
- **Actividad:** Registro de auditoría de descargas

## Alcance

Persistencia de cada descarga con usuario, fecha, archivo, resultado y hash; consulta de auditoría para el Administrador y exclusión de datos personales en el registro

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: modelo y tabla de auditoría 4 h + registro por descarga 6 h + consulta de auditoría 6 h = 16 h
- **Tiempo estimado:** 16 h
- **Costo estimado:** $160.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 22 h
- **Costo total:** $220.000

## Gestión del riesgo

- **Riesgo:** Descargas no registradas o registros de auditoría incompletos
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Registrar dentro de la misma transacción de la descarga y probar la inspección de logs
