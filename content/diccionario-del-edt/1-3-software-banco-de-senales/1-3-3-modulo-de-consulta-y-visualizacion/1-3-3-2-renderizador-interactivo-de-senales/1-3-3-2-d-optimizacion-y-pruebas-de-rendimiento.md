---
project: BioSignal
version: 2
title: "1.3.3.2.D Optimización y pruebas de rendimiento"
aliases:
  - "1.3.3.2.D"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/index|1.3.3.2 Renderizador interactivo de señales]]

- **Código:** 1.3.3.2.D
- **Actividad:** Optimización y pruebas de rendimiento

## Alcance

Perfilado del renderizado, ajuste del bucle de dibujo y de la carga por fragmentos, medición de TTIS y de FPS sostenidos, y verificación en los navegadores soportados

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: perfilado 6 h + optimización del dibujo 8 h + prueba de TTIS 5 h + prueba cross-browser 5 h = 24 h
- **Tiempo estimado:** 24 h
- **Costo estimado:** $240.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 34 h
- **Costo total:** $340.000

## Gestión del riesgo

- **Riesgo:** No alcanzar TTIS ≤ 2,5 s ni 30 FPS sostenidos en equipos de gama media
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Presupuesto de rendimiento por release y medición con PerformanceObserver y DevTools
