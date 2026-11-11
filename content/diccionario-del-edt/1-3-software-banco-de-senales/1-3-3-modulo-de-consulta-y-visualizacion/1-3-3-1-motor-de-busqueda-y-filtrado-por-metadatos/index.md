---
project: BioSignal
version: 2
title: "1.3.3.1 Motor de búsqueda y filtrado por metadatos"
aliases:
  - "1.3.3.1"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.3 Módulo de consulta y visualización

- **Código:** 1.3.3.1
- **Denominación:** Motor de búsqueda y filtrado por metadatos
- **Objetivo:** Proveer a los usuarios una herramienta ágil y precisa para localizar registros de señales bajo múltiples criterios.
- **Descripción:** Mecanismo de consulta avanzada que indexa metadatos y permite filtrar registros biomédicos por tipo de señal (ECG, EEG, EMG), patología asociada, edad, género, frecuencia de muestreo, cantidad de derivaciones y fecha de captura.
- **Prerequisitos:** 1.3.2.1 y 1.3.2.2 completados con datos indexados.

## Actividades

| Código                                                                                                                                                                                                        | Actividad                              | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/1-3-3-1-a-diseno-de-la-pagina-de-busqueda\|1.3.3.1.A]]        | Diseño de la página de búsqueda        |            12 h |    $170.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/1-3-3-1-b-implementar-la-ui-de-busqueda\|1.3.3.1.B]]          | Implementar la UI de búsqueda          |            28 h |    $380.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/1-3-3-1-c-funcionalidad-de-busqueda-e-indexacion\|1.3.3.1.C]] | Funcionalidad de búsqueda e indexación |            48 h |    $650.000 |

- **Fechas:** Semanas 11 a 12 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H5]] — 29/01/2027).
- **Criterios de aceptación:** Tiempo de respuesta de consulta inferior a 500 ms sobre el catálogo de **30 registros semilla**, con prueba de escalabilidad a 1.000 registros indexados.
- **Supuestos:** Los metadatos de las señales se encuentran completos y normalizados.
