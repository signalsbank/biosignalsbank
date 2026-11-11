---
project: BioSignal
version: 2
title: "1.3.1.2.D Pruebas de elevación de privilegios"
aliases:
  - "1.3.1.2.D"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/index|1.3.1.2 Sistema de control de acceso por roles (RBAC)]]

- **Código:** 1.3.1.2.D
- **Actividad:** Pruebas de elevación de privilegios

## Alcance

Casos de prueba de acceso indebido con el rol Consultor, verificación de respuestas 403, evidencia de ausencia de elevación y registro de hallazgos para QA

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·8 + 12) / 6 = 8 h
- **Tiempo estimado:** 8 h
- **Costo estimado:** $80.000
- **Tiempo de prevención:** 1 h
- **Costo de gestión del riesgo:** $10.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 13 h
- **Costo total:** $130.000

## Gestión del riesgo

- **Riesgo:** Hallazgos críticos de elevación de privilegios no detectados antes del hito
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Guion de pruebas basado en la matriz de roles y ejecución cruzada por un integrante distinto del autor del código
