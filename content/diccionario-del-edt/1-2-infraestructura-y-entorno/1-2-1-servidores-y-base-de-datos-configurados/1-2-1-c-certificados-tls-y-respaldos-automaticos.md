---
project: BioSignal
version: 2
title: "1.2.1.C Certificados TLS y respaldos automáticos"
aliases:
  - "1.2.1.C"
---

> Paquete: [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/index|1.2.1 Servidores y base de datos configurados]]

- **Código:** 1.2.1.C
- **Actividad:** Certificados TLS y respaldos automáticos

## Alcance

Emisión y renovación de certificados TLS 1.3, configuración de HTTPS, programación de copias de seguridad y prueba de restauración documentada

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·8 + 12) / 6 = 8 h
- **Tiempo estimado:** 8 h
- **Costo estimado:** $80.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 14 h
- **Costo total:** $140.000

## Gestión del riesgo

- **Riesgo:** Certificado o respaldo mal configurado que impide cumplir TLS 1.3 y la política de backup
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Verificar la cadena TLS y ejecutar una restauración de prueba antes de declarar el entorno operativo
