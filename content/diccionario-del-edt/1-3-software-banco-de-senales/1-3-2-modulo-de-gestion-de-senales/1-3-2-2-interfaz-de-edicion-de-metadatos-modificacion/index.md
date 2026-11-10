---
project: BioSignal
version: 2
title: "1.3.2.2 Interfaz de edición de metadatos (modificación)"
aliases:
  - "1.3.2.2"
---

> [[06-diccionario-del-edt|Índice del Diccionario del EDT]] · Sección: 1.3 Software: Banco de Señales · Módulo: 1.3.2 Módulo de gestión de señales

- **Código:** 1.3.2.2
- **Denominación:** Interfaz de edición de metadatos (modificación)
- **Objetivo:** Facilitar la edición, enriquecimiento y categorización clínica de las señales almacenadas.
- **Descripción:** Interfaz administrativa que permite a los investigadores autorizados modificar datos contextuales de las señales, alineados con [[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros|RF-07]]: tipo de señal (ECG, EEG, EMG), patología de referencia, grupo etario del paciente, equipamiento empleado y notas clínicas de orientación académica, registrando auditoría de cada modificación.
- **Prerequisitos:** 1.3.2.1 Formulario y procesador de carga funcional.

## Actividades

| Código                                                                                                                                                                                                    | Actividad                             | Tiempo estimado | Costo total |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------ | --------------: | ----------: |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-2-interfaz-de-edicion-de-metadatos-modificacion/1-3-2-2-a-diseno-de-la-pagina\|1.3.2.2.A]]                   | Diseño de la página                   |            12 h |    $170.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-2-interfaz-de-edicion-de-metadatos-modificacion/1-3-2-2-b-implementar-la-ui\|1.3.2.2.B]]                     | Implementar la UI                     |            28 h |    $380.000 |
| [[diccionario-del-edt/1-3-software-banco-de-senales/1-3-2-modulo-de-gestion-de-senales/1-3-2-2-interfaz-de-edicion-de-metadatos-modificacion/1-3-2-2-c-funcionalidad-de-editar-los-metadatos\|1.3.2.2.C]] | Funcionalidad de editar los metadatos |            48 h |    $650.000 |

- **Fechas:** Semanas 9 a 10 (Hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H4]] — 15/01/2027).
- **Criterios de aceptación:** Cambios reflejados de inmediato en las consultas; generación obligatoria del registro de autor, fecha y campo modificado.
- **Supuestos:** La edición de metadatos no corrompe ni reescribe la señal biológica cruda original.
