---
project: BioSignal
version: 2
title: "1.3.1.2.A Definición de la matriz de roles y permisos"
aliases:
  - "1.3.1.2.A"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/index|1.3.1.2 Sistema de control de acceso por roles (RBAC)]]

- **Código:** 1.3.1.2.A
- **Actividad:** Definición de la matriz de roles y permisos

## Alcance

Matriz que asigna permisos a los roles Administrador y Consultor por módulo y operación, con criterios explícitos de denegación (403) y exclusiones del MVP (sin otros roles ni registro público)

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·6 + 8) / 6 = 6 h
- **Tiempo estimado:** 6 h
- **Costo estimado:** $60.000
- **Tiempo de prevención:** 1 h
- **Costo de gestión del riesgo:** $10.000
- **Tiempo adicional si ocurre:** 2 h
- **Costo de contingencia si ocurre:** $20.000
- **Duración total:** 9 h
- **Costo total:** $90.000

## Gestión del riesgo

- **Riesgo:** Permisos ambiguos que habilitan acciones indebidas
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Revisión de la matriz con el PM y QA y aprobación formal antes de implementar el motor de autorización
