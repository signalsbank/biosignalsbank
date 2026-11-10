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

- **Fechas:** Semanas 2 a 4.
- **Criterios de aceptación:** Pipelines automáticos que ejecuten compilación, análisis estático y despliegue en ambiente QA tras cada _merge_.
- **Supuestos:** Licencias y herramientas DevOps disponibles sin restricciones operativas.
