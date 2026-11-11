---
project: BioSignal
version: 2
title: "1.3.1.1.C Integración con el servicio de identidad y emisión de tokens"
aliases:
  - "1.3.1.1.C"
---

> Paquete: [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/index|1.3.1.1 Interfaz de inicio de sesión]]

- **Código:** 1.3.1.1.C
- **Actividad:** Integración con el servicio de identidad y emisión de tokens

## Alcance

Validación de credenciales contra el servicio de identidad, emisión de tokens JWT/OAuth2, expiración de la sesión de Administrador a los 30 minutos y transporte exclusivo por HTTPS

## Estimación y costos

- **Cálculo de tiempo estimado:** Tres valores: (8 + 4·16 + 24) / 6 = 16 h
- **Tiempo estimado:** 16 h
- **Costo estimado:** $160.000
- **Tiempo de prevención:** 3 h
- **Costo de gestión del riesgo:** $30.000
- **Tiempo adicional si ocurre:** 8 h
- **Costo de contingencia si ocurre:** $80.000
- **Duración total:** 27 h
- **Costo total:** $270.000

## Gestión del riesgo

- **Riesgo:** Fuga de tokens o expiración incorrecta de la sesión de Administrador
- **Probabilidad (1-5):** 2
- **Impacto (1-5):** 5
- **Mitigación (preventiva):** Firmar tokens con secreto gestionado fuera del repositorio y probar la expiración automática a los 30 minutos
