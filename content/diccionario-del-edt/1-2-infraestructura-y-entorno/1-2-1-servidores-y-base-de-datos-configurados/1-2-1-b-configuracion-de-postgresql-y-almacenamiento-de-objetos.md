---
project: BioSignal
version: 2
title: "1.2.1.B Configuración de PostgreSQL y almacenamiento de objetos"
aliases:
  - "1.2.1.B"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/index|1.2.1 Servidores y base de datos configurados]]

- **Código:** 1.2.1.B
- **Actividad:** Configuración de PostgreSQL y almacenamiento de objetos

## Alcance

Instalación y ajuste de PostgreSQL, esquema inicial de metadatos, repositorio de objetos (S3/MinIO) para archivos EDF binarios y política de respaldo diario con RTO ≤ 4 h y RPO ≤ 24 h

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (12 + 4·20 + 28) / 6 = 20 h
- **Tiempo estimado:** 20 h
- **Costo estimado:** $200.000
- **Tiempo de prevención:** 3 h
- **Costo de gestión del riesgo:** $30.000
- **Tiempo adicional si ocurre:** 10 h
- **Costo de contingencia si ocurre:** $100.000
- **Duración total:** 33 h
- **Costo total:** $330.000

## Gestión del riesgo

- **Riesgo:** Capacidad o latencia insuficiente para almacenar y recuperar archivos de hasta 50 MB
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Prueba de escritura y lectura con archivos de 50 MB y dimensionamiento del volumen antes de habilitar el entorno
