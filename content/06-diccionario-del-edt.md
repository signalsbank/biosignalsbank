---
project: BioSignal
version: 2.3
title: "6. Diccionario del EDT"
aliases:
  - "Diccionario del EDT"
  - "6. Diccionario del EDT"
  - "Diccionario EDT"
---

> **Método de estimación:** distribución beta (_PERT_): **E = (TO + 4·TM + TP) / 6**, con desvío estándar σ = (TP – TO) / 6. Los valores publicados son la esperanza de cada actividad (nivel de confianza ≈ 50 % por actividad). Cuando el valor es simétrico, coincide con la media simple; se usa la fórmula PERT como método único.
>
> **Contenido:** 19 paquetes de trabajo y 66 actividades con ficha individual. Cada paquete tiene un archivo principal con sus características y el desglose de sus actividades.

## 1.1 Gestión del Proyecto

| Código | Paquete                                                                                                                                                   | Actividades |
| :----- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.1.1  | [[diccionario-del-edt/1-1-gestion-del-proyecto/1-1-1-acta-de-constitucion-del-proyecto/index\|Acta de constitución del proyecto]]                         | 3           |
| 1.1.2  | [[diccionario-del-edt/1-1-gestion-del-proyecto/1-1-2-especificacion-de-requisitos-de-software-srs/index\|Especificación de requisitos de software (SRS)]] | 5           |
| 1.1.3  | [[diccionario-del-edt/1-1-gestion-del-proyecto/1-1-3-plan-para-la-direccion-del-proyecto/index\|Plan para la dirección del proyecto]]                     | 3           |
| 1.1.4  | [[diccionario-del-edt/1-1-gestion-del-proyecto/1-1-4-reportes-de-avance-y-seguimiento/index\|Reportes de avance y seguimiento]]                           | 3           |
| 1.1.5  | [[diccionario-del-edt/1-1-gestion-del-proyecto/1-1-5-acta-de-cierre-del-proyecto/index\|Acta de cierre del proyecto]]                                     | 3           |

## 1.2 Infraestructura y Entorno

| Código | Paquete                                                                                                                                                      | Actividades |
| :----- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.2.1  | [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-1-servidores-y-base-de-datos-configurados/index\|Servidores y base de datos configurados]]           | 3           |
| 1.2.2  | [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-2-entornos-de-desarrollo-y-pruebas/index\|Entornos de desarrollo y pruebas]]                         | 3           |
| 1.2.3  | [[diccionario-del-edt/1-2-infraestructura-y-entorno/1-2-3-aprovisionamiento-y-carga-de-dataset-semilla/index\|Aprovisionamiento y carga de dataset semilla]] | 3           |

## 1.3 Software: Banco de Señales

### 1.3.1 Módulo de autenticación y seguridad

| Código  | Paquete                                                                                                                                                                                                  | Actividades |
| :------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.3.1.1 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-1-interfaz-de-inicio-de-sesion/index\|Interfaz de inicio de sesión]]                                 | 4           |
| 1.3.1.2 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-1-modulo-de-autenticacion-y-seguridad/1-3-1-2-sistema-de-control-de-acceso-por-roles-rbac/index\|Sistema de control de acceso por roles (RBAC)]] | 4           |

### 1.3.2 Módulo de gestión de señales

| Código  | Paquete                                                                                                                                                                                               | Actividades |
| :------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.3.2.1 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-1-formulario-y-procesador-de-carga-alta/index\|Formulario y procesador de carga (alta)]]                 | 4           |
| 1.3.2.2 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-2-interfaz-de-edicion-de-metadatos-modificacion/index\|Interfaz de edición de metadatos (modificación)]] | 3           |
| 1.3.2.3 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-3-mecanismo-de-baja-logica-baja/index\|Mecanismo de baja lógica (baja)]]                                 | 3           |

### 1.3.3 Módulo de consulta y visualización

| Código  | Paquete                                                                                                                                                                                             | Actividades |
| :------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.3.3.1 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-1-motor-de-busqueda-y-filtrado-por-metadatos/index\|Motor de búsqueda y filtrado por metadatos]] | 3           |
| 1.3.3.2 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-2-renderizador-interactivo-de-senales/index\|Renderizador interactivo de señales]]               | 4           |
| 1.3.3.3 | [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-3-modulo-de-consulta-y-visualizacion/1-3-3-3-herramienta-de-exportacion-de-registros/index\|Herramienta de exportación de registros]]       | 4           |

## 1.4 Aseguramiento de Calidad

| Código | Paquete                                                                                                                                                         | Actividades |
| :----- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- |
| 1.4.1  | [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-1-reporte-de-pruebas-unitarias/index\|Reporte de pruebas unitarias]]                                     | 3           |
| 1.4.2  | [[diccionario-del-edt/1-4-aseguramiento-de-calidad/1-4-2-reporte-de-pruebas-de-integracion-y-aceptacion/index\|Reporte de pruebas de integración y aceptación]] | 4           |

## 1.5 Despliegue Final

| Código | Paquete                                                                                                                                           | Actividades |
| :----- | :------------------------------------------------------------------------------------------------------------------------------------------------ | :---------- |
| 1.5    | [[diccionario-del-edt/1-5-despliegue-final/1-5-sistema-desplegado-en-ambiente-de-produccion/index\|Sistema desplegado en ambiente de producción]] | 4           |

## Registro de Cambios

| Versión | Fecha      | Cambio                                                                                                                                                                                                                                                                                                                  | Responsable | Estado    |
| :------ | :--------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- | :-------- |
| v1      | —          | Versión inicial                                                                                                                                                                                                                                                                                                         | PM          | Histórico |
| v2.0    | 29/10/2026 | Alineación con ERS/Alcance: métricas 30 FPS, < 50 MB en ≤ 30 s y solo EDF/EDF+; eliminados registro/recuperación de credenciales, roles extra, calibradores y exportación CSV/JSON/MATLAB; renumeración RBAC → 1.3.1.2; paquete 1.2.3 completado; fórmula PERT corregida; fechas re-mapeadas a la Opción A (15 semanas) | PM + QA     | Aprobado  |
| v2.1    | 10/11/2026 | Reestructuración del diccionario: índice en 06 y archivos por paquete/actividad; enlaces de trazabilidad actualizados                                                                                                                                                                                                   | PM          | Aprobado  |
| v2.2    | 10/11/2026 | Desglose de actividades del módulo 1.3.3 (11 actividades en 1.3.3.1, 1.3.3.2 y 1.3.3.3) y actualización de los índices                                                                                                                                                                                                  | PM          | Aprobado  |
| v2.3    | 11/11/2026 | Desglose de actividades de los paquetes 1.2.1, 1.2.2, 1.2.3, 1.3.1.1, 1.3.1.2, 1.4.1, 1.4.2 y 1.5 (28 actividades) y actualización de los índices                                                                                                                                                                       | PM          | Aprobado  |
