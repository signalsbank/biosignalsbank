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

## Actividades

| Código                                                                                                                                                                                                     | Actividad                                  | Tiempo estimado | Costo total |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/1-3-3-2-a-diseno-de-la-vista-del-visor\|1.3.3.2.A]]               | Diseño de la vista del visor               |            16 h |    $240.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/1-3-3-2-b-implementacion-del-renderizador-multicanal\|1.3.3.2.B]] | Implementación del renderizador multicanal |            48 h |    $670.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/1-3-3-2-c-interacciones-de-paneo-zoom-y-amplitud\|1.3.3.2.C]]     | Interacciones de paneo, zoom y amplitud    |            32 h |    $450.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/1-3-3-2-d-optimizacion-y-pruebas-de-rendimiento\|1.3.3.2.D]]      | Optimización y pruebas de rendimiento      |            24 h |    $340.000 |

- **Fechas:** Semanas 11 a 13 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H5]] — 29/01/2027).
- **Criterios de aceptación:** Visualización fluida a **≥ 30 FPS** ([[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño|RNF-03]]) con capacidad de renderizar archivos de menos de 50 MB y hasta 32 canales, sin congelamiento del navegador.
- **Supuestos:** Los navegadores de los clientes soportan estándares modernos de HTML5 y WebGL.
