---
project: BioSignal
version: 2
title: "1.2.2.B Implementación del pipeline CI/CD"
aliases:
  - "1.2.2.B"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/index|1.2.2 Entornos de desarrollo y pruebas]]

- **Código:** 1.2.2.B
- **Actividad:** Implementación del pipeline CI/CD

## Alcance

Pipeline automático que ejecuta compilación, análisis estático, pruebas y despliegue al ambiente de QA tras cada _merge_, con protección de la rama principal y control de versiones

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (12 + 4·20 + 28) / 6 = 20 h
- **Tiempo estimado:** 20 h
- **Costo estimado:** $200.000
- **Tiempo de prevención:** 3 h
- **Costo de gestión del riesgo:** $30.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 31 h
- **Costo total:** $310.000

## Gestión del riesgo

- **Riesgo:** Pipeline inestable o demasiado lento que bloquea las integraciones del equipo
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Etapas mínimas obligatorias, caché de dependencias y ejecución de prueba sobre una rama de ensayo antes de activar la protección de `main`
