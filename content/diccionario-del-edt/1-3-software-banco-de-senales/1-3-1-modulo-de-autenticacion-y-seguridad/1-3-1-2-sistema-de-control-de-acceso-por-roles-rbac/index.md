---
project: BioSignal
version: 2
title: "1.3.1.2 Sistema de control de acceso por roles (RBAC)"
aliases:
  - "1.3.1.2"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.1 Módulo de autenticación y seguridad

- **Código:** 1.3.1.2
- **Denominación:** Sistema de control de acceso por roles (RBAC)
- **Objetivo:** Garantizar que los usuarios accedan únicamente a los datos y funciones según su perfil asignado.
- **Descripción:** Mecanismo de autorización granular que define y aplica permisos para los dos roles aprobados: **Administrador** (GAB / docentes designados) y **Consultor** (estudiantes / usuarios autorizados), asegurando que sólo personal acreditado acceda a datos sensibles. Incluye la creación de cuentas por parte del Administrador (no existe registro público ni recuperación autónoma de credenciales en el MVP).
- **Prerequisitos:** 1.3.1.1 Interfaz de inicio de sesión terminada.

## Actividades

| Código                                                                                                                                                                                                               | Actividad                                   | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------ | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/1-3-1-2-a-definicion-de-la-matriz-de-roles-y-permisos\|1.3.1.2.A]] | Definición de la matriz de roles y permisos |             6 h |     $90.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/1-3-1-2-b-implementacion-del-motor-de-autorizacion\|1.3.1.2.B]]    | Implementación del motor de autorización    |            16 h |    $260.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/1-3-1-2-c-administracion-de-cuentas\|1.3.1.2.C]]                   | Administración de cuentas                   |            10 h |    $160.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/1-3-1-2-d-pruebas-de-elevacion-de-privilegios\|1.3.1.2.D]]         | Pruebas de elevación de privilegios         |             8 h |    $130.000 |

- **Fechas:** Semanas 6 a 7 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H3]] — 18/12/2026).
- **Criterios de aceptación:** Bloqueo estricto (código HTTP 403 Forbidden) para cualquier acción no permitida por la matriz de roles; aprobación de pruebas de elevación de privilegios.
- **Supuestos:** Los perfiles institucionales están previamente homologados con las normativas éticas correspondientes.
