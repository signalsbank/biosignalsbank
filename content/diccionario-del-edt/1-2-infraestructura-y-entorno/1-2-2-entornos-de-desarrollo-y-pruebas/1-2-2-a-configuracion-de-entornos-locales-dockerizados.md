---
project: BioSignal
version: 2
title: "1.2.2.A Configuración de entornos locales dockerizados"
aliases:
  - "1.2.2.A"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/index|1.2.2 Entornos de desarrollo y pruebas]]

- **Código:** 1.2.2.A
- **Actividad:** Configuración de entornos locales dockerizados

## Alcance

Definición de Docker Compose con frontend, backend, PostgreSQL y almacenamiento de objetos; variables de entorno, datos de ejemplo y guía de arranque reproducible para el equipo

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·12 + 16) / 6 = 12 h
- **Tiempo estimado:** 12 h
- **Costo estimado:** $120.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 18 h
- **Costo total:** $180.000

## Gestión del riesgo

- **Riesgo:** Diferencias entre entornos que provocan fallas que no se reproducen en local
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 3
- **Mitigación (preventiva):** Fijar versiones de imágenes y documentar el arranque limpio desde cero antes de incorporar el entorno al flujo de trabajo
