---
project: BioSignal
version: 2
title: "1.3.3.3.C Funcionalidad de exportación EDF sanitizado"
aliases:
  - "1.3.3.3.C"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/index|1.3.3.3 Herramienta de exportación de registros]]

- **Código:** 1.3.3.3.C
- **Actividad:** Funcionalidad de exportación EDF sanitizado

## Alcance

Endpoint de descarga que recupera el EDF/EDF+ persistido, verifica que esté sanitizado, calcula su hash y lo entrega por streaming sin alterar la señal ni los metadatos clínicos permitidos

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: verificación de hash 8 h + streaming del archivo 12 h + verificación de sanitización 10 h + endpoint de descarga 10 h = 40 h
- **Tiempo estimado:** 40 h
- **Costo estimado:** $400.000
- **Tiempo de prevención:** 4 h
- **Costo de gestión del riesgo:** $40.000
- **Tiempo adicional si ocurre:** 12 h
- **Costo de contingencia si ocurre:** $120.000
- **Duración total:** 56 h
- **Costo total:** $560.000

## Gestión del riesgo

- **Riesgo:** Entregar un archivo no sanitizado o con identidad residual del paciente en cabecera o anotaciones TAL
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Verificación automática de cabecera/TAL y hash antes de habilitar la descarga
