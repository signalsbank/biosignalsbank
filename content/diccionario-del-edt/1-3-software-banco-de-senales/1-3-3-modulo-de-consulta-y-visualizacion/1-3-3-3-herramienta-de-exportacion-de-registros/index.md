---
project: BioSignal
version: 2
title: "1.3.3.3 Herramienta de exportación de registros"
aliases:
  - "1.3.3.3"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.3 Módulo de consulta y visualización

- **Código:** 1.3.3.3
- **Denominación:** Herramienta de exportación de registros
- **Objetivo:** Permitir la descarga de señales biomédicas en el formato estándar aprobado (EDF/EDF+ sanitizado), manteniendo la trazabilidad de las descargas.
- **Descripción:** Servicio de descarga del archivo EDF/EDF+ **sanitizado (anonimizado)** y persistido en el repositorio, con registro de auditoría de cada descarga (usuario, fecha, archivo). Las exportaciones a CSV, JSON o MATLAB quedaron **fuera de alcance**; si se requieren, se tramita un RFC y se actualizan [[03-especificacion-de-requisitos#3.4. Exportación y Descarga|RF-14]] y el Enunciado del Alcance.
- **Prerequisitos:** 1.3.3.1 Motor de búsqueda y 1.3.2.1 Procesador de señales.

## Actividades

| Código                                                                                                                                                                                                          | Actividad                                   | Tiempo estimado | Costo total |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------ | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/1-3-3-3-a-diseno-de-la-pantalla-de-descarga\|1.3.3.3.A]]           | Diseño de la pantalla de descarga           |             8 h |    $120.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/1-3-3-3-b-implementar-la-ui-de-descarga\|1.3.3.3.B]]               | Implementar la UI de descarga               |            16 h |    $230.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/1-3-3-3-c-funcionalidad-de-exportacion-edf-sanitizado\|1.3.3.3.C]] | Funcionalidad de exportación EDF sanitizado |            40 h |    $560.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/1-3-3-3-d-registro-de-auditoria-de-descargas\|1.3.3.3.D]]          | Registro de auditoría de descargas          |            16 h |    $220.000 |

- **Fechas:** Semanas 12 a 14 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H5]] — 29/01/2027).
- **Criterios de aceptación:** Archivo EDF descargado sanitizado, íntegro y trazable (hash verificable); validado con librerías estándar (MNE-Python / WFDB) como **método de verificación** de integridad de la señal.
- **Supuestos:** Capacidad de almacenamiento temporal en servidor suficiente para la descarga.
