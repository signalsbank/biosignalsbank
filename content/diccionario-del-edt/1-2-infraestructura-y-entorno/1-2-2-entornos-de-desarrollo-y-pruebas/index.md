---
project: BioSignal
version: 2
title: "1.2.2 Entornos de desarrollo y pruebas"
aliases:
  - "1.2.2"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.2 Infraestructura y Entorno

- **Código:** 1.2.2
- **Denominación:** Entornos de desarrollo y pruebas
- **Objetivo:** Establecer ambientes aislados, reproducibles y automatizados para la construcción, integración y verificación continua del software.
- **Descripción:** Implementación de pipelines de CI/CD (Integración y Despliegue Continuo), entornos de desarrollo local dockerizados y un ambiente de _staging/QA_ que simule producción con datos sintéticos o anonimizados de señales.
- **Prerequisitos:** 1.2.1 Servidores y base de datos configurados.

## Actividades

| Código                                                                                                                                                       | Actividad                                      | Tiempo estimado | Costo total |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/1-2-2-a-configuracion-de-entornos-locales-dockerizados\|1.2.2.A]] | Configuración de entornos locales dockerizados |            12 h |    $180.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/1-2-2-b-implementacion-del-pipeline-ci-cd\|1.2.2.B]]              | Implementación del pipeline CI/CD              |            20 h |    $310.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/1-2-2-c-ambiente-de-staging-qa-con-datos-sinteticos\|1.2.2.C]]    | Ambiente de staging/QA con datos sintéticos    |            12 h |    $200.000 |

- **Fechas:** Semanas 2 a 4.
- **Criterios de aceptación:** Pipelines automáticos que ejecuten compilación, análisis estático y despliegue en ambiente QA tras cada _merge_.
- **Supuestos:** Licencias y herramientas DevOps disponibles sin restricciones operativas.
