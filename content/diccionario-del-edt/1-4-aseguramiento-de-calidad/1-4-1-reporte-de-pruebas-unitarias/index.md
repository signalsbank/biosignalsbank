---
project: BioSignal
version: 2
title: "1.4.1 Reporte de pruebas unitarias"
aliases:
  - "1.4.1"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.4 Aseguramiento de Calidad

- **Código:** 1.4.1
- **Denominación:** Reporte de pruebas unitarias
- **Objetivo:** Validar el correcto funcionamiento de los componentes algorítmicos y funciones individuales de forma aislada.
- **Descripción:** Informe técnico que documenta el diseño, ejecución y resultados de las baterías de pruebas automatizadas sobre la lógica de negocio: algoritmos de procesamiento de señales, validadores de formatos, parseo de metadatos y reglas de negocio del RBAC.
- **Prerequisitos:** Módulos de desarrollo de la sección 1.3 implementados.

## Actividades

| Código                                                                                                                                                   | Actividad                                       | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-1-reporte-de-pruebas-unitarias/1-4-1-a-diseno-de-la-bateria-de-pruebas-unitarias\|1.4.1.A]]       | Diseño de la batería de pruebas unitarias       |             6 h |     $90.000 |
| [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-1-reporte-de-pruebas-unitarias/1-4-1-b-automatizacion-y-ejecucion-de-pruebas-unitarias\|1.4.1.B]] | Automatización y ejecución de pruebas unitarias |            16 h |    $240.000 |
| [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-1-reporte-de-pruebas-unitarias/1-4-1-c-elaboracion-del-reporte-de-cobertura\|1.4.1.C]]            | Elaboración del reporte de cobertura            |             8 h |    $110.000 |

- **Fechas:** Semanas 13 a 14 (cierre antes del Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H6]] — 05/02/2027).
- **Criterios de aceptación:** Cobertura de código superior al 80% en lógica crítica de negocio y 100% de pruebas unitarias ejecutadas satisfactoriamente (cero fallas).
- **Supuestos:** Los componentes fueron desarrollados siguiendo principios de código desacoplado y testeable.
