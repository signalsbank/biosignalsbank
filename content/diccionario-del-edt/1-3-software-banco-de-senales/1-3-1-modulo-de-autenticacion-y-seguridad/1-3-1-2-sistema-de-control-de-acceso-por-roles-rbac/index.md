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

- **Fechas:** Semanas 6 a 7 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H3]] — 18/12/2026).
- **Criterios de aceptación:** Bloqueo estricto (código HTTP 403 Forbidden) para cualquier acción no permitida por la matriz de roles; aprobación de pruebas de elevación de privilegios.
- **Supuestos:** Los perfiles institucionales están previamente homologados con las normativas éticas correspondientes.
