---
project: BioSignal
version: 2
title: "1.2.3 Aprovisionamiento y carga de dataset semilla"
aliases:
  - "1.2.3"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.2 Infraestructura y Entorno

- **Código:** 1.2.3
- **Denominación:** Aprovisionamiento y carga de dataset semilla
- **Objetivo:** Conformar y cargar el dataset semilla EDF (≥ 30 registros, 15 ECG + 15 EEG) con metadatos y evidencia de anonimización, dejándolo disponible en el catálogo productivo (trazable con [[03-especificacion-de-requisitos#5. Requisitos de Transición y Preparación Operativa|RT-01]] y [[04-enunciado-del-alance-del-proyecto#3.1. Entregables del Producto (Software)|EP-06]]).
- **Descripción:** Selección/recolección de registros EDF/EDF+ (reales donados por el GAB o de fuentes abiertas/sintéticas como respaldo, según el riesgo R-01), verificación de anonimización irreversible de cabeceras, catalogación con metadatos académicos ([[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros|RF-07]]) y carga validada en el repositorio productivo.
- **Prerequisitos:** 1.2.1 Servidores y base de datos configurados; 1.2.2 Entornos de desarrollo y pruebas; dictamen legal/ético para los datos de origen hospitalario ([[03-especificacion-de-requisitos#6. Requisitos y Restricciones del Proyecto|RP-03]]).

## Actividades

| Código                                                                                                                                                               | Actividad                                       | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/1-2-3-a-recoleccion-y-seleccion-de-registros-edf\|1.2.3.A]]   | Recolección y selección de registros EDF        |            12 h |    $220.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/1-2-3-b-verificacion-de-anonimizacion-irreversible\|1.2.3.B]] | Verificación de anonimización irreversible      |             8 h |    $160.000 |
| [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/1-2-3-c-catalogacion-y-carga-validada\|1.2.3.C]]              | Catalogación y carga validada en el repositorio |            12 h |    $180.000 |

- **Fechas:** Semanas 3 a 5 (dataset disponible antes del Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H4]] — 15/01/2027).
- **Criterios de aceptación:** 30 registros EDF cargados y catalogados (≥ 15 ECG y ≥ 15 EEG); 0 % de PII residual en cabecera, TALs y metadatos; inventario verificado en BD de producción.
- **Supuestos:** El GAB entrega a tiempo los registros anonimizados; si no, se usa PhysioNet o señales sintéticas desde la semana 1 (riesgo R-01).
