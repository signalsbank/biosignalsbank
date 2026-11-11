---
project: BioSignal
version: 2
title: "1.3.1.2.B Implementación del motor de autorización"
aliases:
  - "1.3.1.2.B"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/index|1.3.1.2 Sistema de control de acceso por roles (RBAC)]]

- **Código:** 1.3.1.2.B
- **Actividad:** Implementación del motor de autorización

## Alcance

Middleware de autorización que aplica la matriz de roles en API y frontend, deniega accesos no permitidos con HTTP 403 y registra los intentos rechazados

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (12 + 4·16 + 20) / 6 = 16 h
- **Tiempo estimado:** 16 h
- **Costo estimado:** $160.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 26 h
- **Costo total:** $260.000

## Gestión del riesgo

- **Riesgo:** Bypass de autorización por endpoints no protegidos o controles solo en el frontend
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Control obligatorio en backend para cada endpoint y revisión de rutas antes de habilitar el módulo
