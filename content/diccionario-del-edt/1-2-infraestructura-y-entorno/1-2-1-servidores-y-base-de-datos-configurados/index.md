---
project: BioSignal
version: 2
title: "1.2.1 Servidores y base de datos configurados"
aliases:
  - "1.2.1"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.2 Infraestructura y Entorno

- **Código:** 1.2.1
- **Denominación:** Servidores y base de datos configurados
- **Objetivo:** Proveer la infraestructura de cómputo, almacenamiento seguro de archivos masivos y base de datos optimizada para señales biomédicas.
- **Descripción:** Aprovisionamiento y configuración de máquinas virtuales/contenedores, repositorios de objetos (S3/MinIO) para archivos binarios de señales, y base de datos relacional/híbrida (PostgreSQL) para indexación de metadatos clínicos con copias de respaldo y certificados TLS/SSL.
- **Prerequisitos:** 1.1.2 Requisitos no funcionales de arquitectura y almacenamiento aprobados.

- **Fechas:** Semanas 2 a 3.
- **Criterios de aceptación:** Servidores operativos con monitoreo 24/7, almacenamiento escalable accesible por API y conexión a base de datos con latencia menor a 50 ms.
- **Supuestos:** Créditos cloud o servidores físicos disponibles a tiempo.
