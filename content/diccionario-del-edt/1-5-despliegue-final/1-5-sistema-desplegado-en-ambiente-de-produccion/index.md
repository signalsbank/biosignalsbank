---
project: BioSignal
version: 2
title: "1.5 Sistema desplegado en ambiente de producción"
aliases:
  - "1.5"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.5 Despliegue Final

- **Código:** 1.5
- **Denominación:** Sistema desplegado en ambiente de producción
- **Objetivo:** Poner en marcha y dejar en régimen operativo el sistema integral del Banco de Señales Biomédicas accesible para la comunidad usuaria.
- **Descripción:** Ejecución de la puesta en producción en la infraestructura final, que incluye la migración de bases de datos, verificación de dominios, instalación de certificados de seguridad, configuración de copias de seguridad automáticas, monitoreo de disponibilidad y ejecución de pruebas de humo (_smoke testing_).
- **Prerequisitos:** 1.2.1 Infraestructura productiva lista y 1.4.2 Pruebas de aceptación formalmente aprobadas.

## Actividades

| Código                                                                                                                                                   | Actividad                                      | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/1-5-a-migracion-de-datos-y-configuracion-productiva\|1.5.A]] | Migración de datos y configuración productiva  |            12 h |    $200.000 |
| [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/1-5-b-certificados-respaldos-y-monitoreo-productivo\|1.5.B]] | Certificados, respaldos y monitoreo productivo |             8 h |    $140.000 |
| [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/1-5-c-pruebas-de-humo-y-pase-a-produccion\|1.5.C]]           | Pruebas de humo y pase a producción            |             8 h |    $140.000 |
| [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/1-5-d-elaboracion-del-acta-de-despliegue\|1.5.D]]            | Elaboración del acta de despliegue             |             6 h |     $90.000 |

- **Fechas:** Semanas 14 a 15 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H7]] — Puesta en Producción, 12/02/2027).
- **Criterios de aceptación:** Sistema 100% accesible vía web pública/institucional, tiempo de disponibilidad inicial de 99.9%, sin errores en logs y prueba de humo superada al 100%.
- **Supuestos:** Disponibilidad de la ventana de mantenimiento y red sin bloqueos perimetrales.
