---
project: BioSignal
version: 2
title: "1.3.1.1 Interfaz de inicio de sesión"
aliases:
  - "1.3.1.1"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.1 Módulo de autenticación y seguridad

- **Código:** 1.3.1.1
- **Denominación:** Interfaz de inicio de sesión
- **Objetivo:** Permitir el ingreso seguro y controlado de los usuarios a la plataforma mediante verificación de identidad.
- **Descripción:** Pantalla responsiva de autenticación que valida usuario y contraseña contra el servicio de identidad, emite tokens de sesión seguros (JWT/OAuth2) e implementa mecanismos de protección contra ataques de fuerza bruta.
- **Prerequisitos:** 1.2.2 Entornos de desarrollo y pruebas disponibles.

## Actividades

| Código                                                                                                                                                                                                                 | Actividad                                                    | Tiempo estimado | Costo total |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/1-3-1-1-a-diseno-de-la-pantalla-de-inicio-de-sesion\|1.3.1.1.A]]                    | Diseño de la pantalla de inicio de sesión                    |             6 h |     $90.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/1-3-1-1-b-implementacion-de-la-ui-de-autenticacion\|1.3.1.1.B]]                     | Implementación de la UI de autenticación                     |            12 h |    $180.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/1-3-1-1-c-integracion-con-el-servicio-de-identidad-y-emision-de-tokens\|1.3.1.1.C]] | Integración con el servicio de identidad y emisión de tokens |            16 h |    $270.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/1-3-1-1-d-proteccion-contra-fuerza-bruta-y-bloqueo-tras-5-intentos\|1.3.1.1.D]]     | Protección contra fuerza bruta y bloqueo tras 5 intentos     |             6 h |    $110.000 |

- **Fechas:** Semanas 5 a 6 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H3]] — 18/12/2026).
- **Criterios de aceptación:** Tiempo de respuesta de autenticación menor a 1 segundo, tokens transmitidos únicamente por HTTPS y bloqueo efectivo tras 5 intentos erróneos.
- **Supuestos:** Protocolo de cifrado robusto para contraseñas (Argon2 o bcrypt) estandarizado en backend.
