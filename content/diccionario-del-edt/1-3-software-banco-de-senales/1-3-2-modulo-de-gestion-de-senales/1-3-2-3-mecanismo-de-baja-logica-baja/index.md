---
project: BioSignal
version: 2
title: "1.3.2.3 Mecanismo de baja lógica (baja)"
aliases:
  - "1.3.2.3"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.2 Módulo de gestión de señales

- **Código:** 1.3.2.3
- **Denominación:** Mecanismo de baja lógica (baja)
- **Objetivo:** Ocultar registros obsoletos o erróneos del catálogo público sin destruir la información física, preservando la trazabilidad.
- **Descripción:** Lógica de software que implementa la desactivación de registros mediante banderas de estado (`is_deleted = true`, fecha y motivo), excluyéndolos de las búsquedas habituales pero permitiendo su eventual auditoría o restauración por administradores.
- **Prerequisitos:** 1.3.2.1 Formulario de alta y 1.3.1.2 Roles de usuario configurados.

## Actividades

| Código                                                                                                                                                                           | Actividad                    | Tiempo estimado | Costo total |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------- | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-3-mecanismo-de-baja-logica-baja/1-3-2-3-a-diseno-de-la-pagina\|1.3.2.3.A]]          | Diseño de la página          |             3 h |     $40.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-3-mecanismo-de-baja-logica-baja/1-3-2-3-b-implementar-la-ui\|1.3.2.3.B]]            | Implementar la UI            |             8 h |    $120.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-3-mecanismo-de-baja-logica-baja/1-3-2-3-c-funcionalidad-de-baja-logica\|1.3.2.3.C]] | Funcionalidad de baja lógica |            18 h |    $240.000 |

- **Fechas:** Semanas 10 a 11 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H4]] — 15/01/2027).
- **Criterios de aceptación:** El registro desaparece inmediatamente de las búsquedas generales pero permanece intacto en base de datos con justificación del borrado.
- **Supuestos:** Cumplimiento de políticas de retención de datos científicos que prohíben la pérdida irreversible de registros.
