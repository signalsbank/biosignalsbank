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

## Actividades

| Código                                                                                                                                                                       | Actividad                                               | Tiempo estimado | Costo total |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------ | --------------: | ----------: |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/1-2-1-a-aprovisionamiento-de-servidores-y-contenedores\|1.2.1.A]]          | Aprovisionamiento de servidores y contenedores          |            12 h |    $200.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/1-2-1-b-configuracion-de-postgresql-y-almacenamiento-de-objetos\|1.2.1.B]] | Configuración de PostgreSQL y almacenamiento de objetos |            20 h |    $330.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/1-2-1-c-certificados-tls-y-respaldos-automaticos\|1.2.1.C]]                | Certificados TLS y respaldos automáticos                |             8 h |    $140.000 |

- **Fechas:** Semanas 2 a 3.
- **Criterios de aceptación:** Servidores operativos con monitoreo 24/7, almacenamiento escalable accesible por API y conexión a base de datos con latencia menor a 50 ms.
- **Supuestos:** Créditos cloud o servidores físicos disponibles a tiempo.
