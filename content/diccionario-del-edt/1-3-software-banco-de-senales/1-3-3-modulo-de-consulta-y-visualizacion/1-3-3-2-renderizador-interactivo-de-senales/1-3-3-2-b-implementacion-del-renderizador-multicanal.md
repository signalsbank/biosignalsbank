---
project: BioSignal
version: 2
title: "1.3.3.2.B Implementación del renderizador multicanal"
aliases:
  - "1.3.3.2.B"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/index|1.3.3.2 Renderizador interactivo de señales]]

- **Código:** 1.3.3.2.B
- **Actividad:** Implementación del renderizador multicanal

## Alcance

Renderizador Canvas/WebGL con carga por fragmentos, dibujo sincronizado de hasta 32 canales, ejes temporales, escalas clínicas (25 mm/s y 10 mm/mV) y selector para encender, apagar y reordenar canales

## Estimación y costos

- **Cálculo de tiempo estimado:** Descomposición: carga por fragmentos 12 h + render multicanal Canvas/WebGL 16 h + ejes y escalas clínicas 10 h + soporte de 32 canales 10 h = 48 h
- **Tiempo estimado:** 48 h
- **Costo estimado:** $480.000
- **Tiempo de prevención:** 5 h
- **Costo de gestión del riesgo:** $50.000
- **Tiempo adicional si ocurre:** 14 h
- **Costo de contingencia si ocurre:** $140.000
- **Duración total:** 67 h
- **Costo total:** $670.000

## Gestión del riesgo

- **Riesgo:** Renderizado por debajo de 30 FPS o bloqueo del navegador con 32 canales simultáneos
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Carga por fragmentos, límite de canales por vista y prueba temprana con 32 canales
