---
project: BioSignal
version: 2
title: "1.2.2.C Ambiente de staging/QA con datos sintéticos"
aliases:
  - "1.2.2.C"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/index|1.2.2 Entornos de desarrollo y pruebas]]

- **Código:** 1.2.2.C
- **Actividad:** Ambiente de staging/QA con datos sintéticos

## Alcance

Ambiente de _staging_ que replica la topología de producción, con dataset sintético o anonimizado, accesos restringidos y verificación de que no se utilicen datos personales reales

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

- **Riesgo:** Uso accidental de registros reales o identificables en el ambiente de pruebas
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Carga exclusiva de señales sintéticas y control de acceso al ambiente de QA con credenciales separadas
