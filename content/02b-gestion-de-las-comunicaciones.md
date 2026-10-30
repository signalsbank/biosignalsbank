---
project: BioSignal
version: 1.1
title: 2b. Gestión de las comunicaciones
aliases: Gestión de las comunicaciones
---

## Comunicaciones externas

| Información             | Formato                 | Emisor                          | Grupo Receptor                                           | Tecnología                                 | Frecuencia                               | Feedback / Cierre     |
| :---------------------- | :---------------------- | :------------------------------ | :------------------------------------------------------- | :----------------------------------------- | :--------------------------------------- | :-------------------- |
| Iniciación del Proyecto | Acta de Constitución    | Director del Proyecto           | Patrocinador (EICA), Bioingeniería, cátedras evaluadoras | Documento digital vía correo institucional | Una sola vez                             | Firma del Acta        |
| Estado del Proyecto     | Informe ejecutivo       | Director del Proyecto           | Patrocinador (Alejandro Rosas)                           | Documento digital + reunión formal         | Mensual + por hito (7 instancias: H1–H7) | Minuta con decisiones |
| Requisitos y alcance    | ERS + RTM + revisión    | Asistente del PM (APM)          | GAB, Dirección TIC, docentes                             | Repositorio + reunión                      | Por hito                                 | Acta de revisión      |
| Infraestructura         | Ticket + checklist      | Infraestructura (Eber Chiecher) | Dirección TIC                                            | Mesa de ayuda + reunión                    | Semanal durante infraestructura          | Confirmación TIC      |
| Legal y ética           | Dictamen                | Director del Proyecto           | Asesoría legal / comité de ética                         | Correo formal                              | En requisitos y auditoría (RP-03)        | Dictamen firmado      |
| Dataset semilla         | Inventario + validación | GAB                             | PM y QA                                                  | Repositorio + reunión                      | Quincenal hasta Hito H4                  | Inventario verificado |
| Cierre del Proyecto     | Acta de Cierre          | Director del Proyecto           | Patrocinador, cátedras evaluadoras, usuarios finales     | Documento digital + reunión formal         | Una sola vez, antes del 15/Feb/2027      | Firma del Acta        |

## Comunicaciones internas

| Qué se comunica                   | Responsable de Comunicar       | Grupo Receptor                           | Metodología o Tecnología                                          | Frecuencia de Comunicación  |
| :-------------------------------- | :----------------------------- | :--------------------------------------- | :---------------------------------------------------------------- | :-------------------------- |
| Coordinación del Proyecto         | Director del Proyecto          | Equipo completo                          | Reunión (presencial o virtual) + documento digital                | Semanal                     |
| Avance de tareas                  | Cada desarrollador             | Director del Proyecto y Asistente del PM | Gestor de tareas (GitHub Projects)                                | Continuo, con corte semanal |
| Bloqueos e impedimentos           | Quien lo detecta               | Director del Proyecto                    | Mensajería instantánea (discord #impedimentos) + gestor de tareas | Inmediato al detectarse     |
| Revisión técnica de código        | Desarrollador revisor asignado | Autor del cambio                         | Repositorio de código (github)                                    | Por cada entrega de código  |
| Resultados de pruebas             | QA                             | Equipo completo y Director del Proyecto  | Reunión semanal                                                   | Por ciclo de pruebas        |
| Riesgos                           | QA / PM                        | Equipo completo y Sponsor                | Informe de riesgos en repositorio                                 | Quincenal + por hito        |
| Cambios de alcance, plazo o costo | Director del Proyecto          | CCB y Equipo completo                    | RFC + reunión                                                     | Ante cada cambio aprobado   |
| Solicitud de ausentismo           | Integrante afectado            | Director del Proyecto                    | Correo o mensajería instantánea                                   | Con 2 días de anticipación  |
| Cierre de hito interno            | Director del Proyecto          | Equipo completo                          | Reunión + documento digital                                       | Al finalizar cada Hito      |

## Escalamiento

| Situación                           | Plazo de reacción | Instancia             |
| :---------------------------------- | :---------------- | :-------------------- |
| Bloqueo técnico                     | 24 h              | Director del Proyecto |
| Bloqueo que afecta un hito          | 48 h              | Sponsor               |
| Cambio de alcance, plazo o costo    | 5 días hábiles    | CCB + Sponsor         |
| Incidente de seguridad o privacidad | Inmediato         | PM + Legal + TIC      |

## Confidencialidad y clasificación

- No se envían datos de pacientes por chat ni correo; se usan IDs anonimizados.
- Los documentos se clasifican como `público`, `interno` o `restringido`.
- En idioma oficial: español (UNViMe).
- Los logs de auditoría se conservan durante el plazo que defina la UNViMe (mínimo recomendado: 5 años).
