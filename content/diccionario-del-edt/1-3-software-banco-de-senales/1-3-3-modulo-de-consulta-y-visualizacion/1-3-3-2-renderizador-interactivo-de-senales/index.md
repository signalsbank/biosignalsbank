---
project: BioSignal
version: 2
title: "1.3.3.2 Renderizador interactivo de señales"
aliases:
  - "1.3.3.2"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.3 Módulo de consulta y visualización

- **Código:** 1.3.3.2
- **Denominación:** Renderizador interactivo de señales
- **Objetivo:** Visualizar de forma gráfica e interactiva las series temporales de señales biomédicas en el navegador sin retrasos.
- **Descripción:** Componente web de alto rendimiento basado en Canvas/WebGL que permite visualizar múltiples canales simultáneos, realizar acercamientos (_zoom in/out_), paneos temporales y ajuste de amplitud. Las herramientas de medición/calibradores sobre la señal quedaron **fuera del MVP**.
- **Prerequisitos:** 1.3.2.1 Procesador de señales y 1.3.3.1 Motor de búsqueda listos.

- **Fechas:** Semanas 11 a 13 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H5]] — 29/01/2027).
- **Criterios de aceptación:** Visualización fluida a **≥ 30 FPS** ([[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño|RNF-03]]) con capacidad de renderizar archivos de menos de 50 MB y hasta 32 canales, sin congelamiento del navegador.
- **Supuestos:** Los navegadores de los clientes soportan estándares modernos de HTML5 y WebGL.
