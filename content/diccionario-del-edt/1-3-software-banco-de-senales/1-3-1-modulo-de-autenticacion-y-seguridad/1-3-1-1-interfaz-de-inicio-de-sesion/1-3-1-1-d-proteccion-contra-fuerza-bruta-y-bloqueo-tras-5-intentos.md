---
project: BioSignal
version: 2
title: "1.3.1.1.D Protección contra fuerza bruta y bloqueo tras 5 intentos"
aliases:
  - "1.3.1.1.D"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/index|1.3.1.1 Interfaz de inicio de sesión]]

- **Código:** 1.3.1.1.D
- **Actividad:** Protección contra fuerza bruta y bloqueo tras 5 intentos

## Alcance

Mecanismo de limitación de intentos, bloqueo de la cuenta al quinto error consecutivo, registro de eventos de autenticación y mensajes de recuperación asistida por el Administrador

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (4 + 4·6 + 8) / 6 = 6 h
- **Tiempo estimado:** 6 h
- **Costo estimado:** $60.000
- **Tiempo de prevención:** 1 h
- **Costo de gestión del riesgo:** $10.000
- **Tiempo adicional si ocurre:** 4 h
- **Costo de contingencia si ocurre:** $40.000
- **Duración total:** 11 h
- **Costo total:** $110.000

## Gestión del riesgo

- **Riesgo:** Ataque de fuerza bruta exitoso o bloqueo indebido de usuarios legítimos
- **Probabilidad (1-5):** 3
- **Impacto (1-5):** 4
- **Mitigación (preventiva):** Rate limiting por IP y cuenta, con prueba de los umbrales de bloqueo y desbloqueo antes del cierre
