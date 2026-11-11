---
project: BioSignal
version: 2
title: "1.3.1.1.B Implementación de la UI de autenticación"
aliases:
  - "1.3.1.1.B"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/index|1.3.1.1 Interfaz de inicio de sesión]]

- **Código:** 1.3.1.1.B
- **Actividad:** Implementación de la UI de autenticación

## Alcance

Construcción del formulario responsivo con validaciones en cliente, estados de carga y error, mensajes accesibles y adaptación a escritorio y móvil

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·12 + 16) / 6 = 12 h
- **Tiempo estimado:** 12 h
- **Costo estimado:** $120.000
- **Tiempo de prevención:** 2 h
- **Costo de gestión del riesgo:** $20.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 18 h
- **Costo total:** $180.000

## Gestión del riesgo

- **Riesgo:** Incumplimiento de accesibilidad o comportamiento inconsistente entre navegadores
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 2
- **Mitigación (preventiva):** Pruebas de teclado, contraste y lectura con las dos últimas versiones de Chromium, Gecko y WebKit
