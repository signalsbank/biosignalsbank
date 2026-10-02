### 1.3.2 Módulo de gestión de señales (MÁXIMO 2 MESES)

#### Paquete de Trabajo: 1.3.2.1 (4 SEMANAS)

- **Código:** 1.3.2.1
- **Denominación:** Formulario y procesador de carga (alta)
- **Objetivo:** Permitir la carga e ingesta controlada de registros biomédicos al repositorio con extracción automática de características técnicas.
- **Descripción:** Componente web de carga de archivos (con soporte de arrastrar y soltar) conectado a un motor de procesamiento que valida la integridad del archivo, detecta el formato (EDF, CSV, PhysioNet, etc.), extrae canales, frecuencia de muestreo y duración, y almacena el archivo binario y sus metadatos.
- **Prerequisitos:** 1.2.1 Almacenamiento configurado y 1.3.1.4 Control de roles operativo.
- **Actividades:**

| Código  | Actividad                 | Alcance | Cálculo de<br>tiempo estimado<br>Estimación por tres valores (promedio simple) | Tiempo estimado | Costo estimado<br>(h x $) | Riesgo | Probabilidad<br>de ocurrencia | Impacto | P x I | Mitigación | Tiempo adicional<br>si ocurre | Costo de gestión<br>del riesgo | Costo de contingencia<br>si ocurre | Costo total |
| ------- | ------------------------- | ------- | ------------------------------------------------------------------------------ | --------------- | ------------------------- | ------ | ----------------------------- | ------- | ----- | ---------- | ----------------------------- | ------------------------------ | ---------------------------------- | ----------- |
| 1.3.2.A | Diseño de la página       |         | TO 6h<br>TM 10h<br>TP 14h                                                      | 10h             |                           |        |                               |         |       |            | 10                            |                                |                                    | 20          |
| 1.3.2.B | Implementación de UI      |         |                                                                                | 30h             |                           |        |                               |         |       |            | 20                            |                                |                                    | 50          |
| 1.3.2.C | Funcionalidad de subida   |         |                                                                                | 25h             |                           |        |                               |         |       |            | 20                            |                                |                                    | 45          |
| 1.3.2.D | Funcionalidad de registro |         |                                                                                | 25h             |                           |        |                               |         |       |            | 20                            |                                |                                    | 45          |


- **Criterios de aceptación:** Ingesta exitosa de archivos de hasta 500 MB en menos de 20 segundos con lectura correcta de cabecera y canales.
- **Supuestos:** Los usuarios proporcionan archivos conformes a especificaciones estándar de señales biomédicas.
- **Riesgos:** Archivos corruptos, con formato no estándar o de gran volumen que saturen la memoria RAM del servidor.

---

#### Paquete de Trabajo: 1.3.2.2 (2 SEMANAS)

- **Código:** 1.3.2.2
- **Denominación:** Interfaz de edición de metadatos (modificación)
- **Objetivo:** Facilitar la edición, enriquecimiento y categorización clínica de las señales almacenadas.
- **Descripción:** Interfaz administrativa que permite a los investigadores autorizados modificar datos contextuales de las señales (edad del paciente, diagnóstico según CIE-10/SNOMED, derivaciones utilizadas, medicamentos o eventos marcadores), registrando auditoría de cada modificación.
- **Prerequisitos:** 1.3.2.1 Formulario y procesador de carga funcional.
- **Actividades:**

1. Mockup de la página (en figma) | 4 días
2. Implementar la UI | 3 días
3. Funcionalidad de editar los metadatos | 3 días

- **Criterios de aceptación:** Cambios reflejados de inmediato en las consultas; generación obligatoria del registro de autor, fecha y campo modificado.
- **Supuestos:** La edición de metadatos no corrompe ni reescribe la señal biológica cruda original.
- **Riesgos:** Inconsistencias clínicas por ingreso de diagnósticos no normalizados (mitigado con catálogos cerrados).

---

#### Paquete de Trabajo: 1.3.2.3

- **Código:** 1.3.2.3
- **Denominación:** Mecanismo de baja lógica (baja)
- **Objetivo:** Ocultar registros obsoletos o erróneos del catálogo público sin destruir la información física, preservando la trazabilidad.
- **Descripción:** Lógica de software que implementa la desactivación de registros mediante banderas de estado (`is_deleted = true`, fecha y motivo), excluyéndolos de las búsquedas habituales pero permitiendo su eventual auditoría o restauración por administradores.
- **Prerequisitos:** 1.3.2.1 Formulario de alta y 1.3.1.4 Roles de usuario configurados.
- **Actividades:**

* DURACIÓN 2 SEMANAS

1. Mockup de la página (en figma) | 4 días
2. Implementar la UI | 3 días
3. Funcionalidad de borrar los metadatos | 3 días

- **Fechas:** Semanas 14 a 15.
- **Criterios de aceptación:** El registro desaparece inmediatamente de las búsquedas generales pero permanece intacto en base de datos con justificación del borrado.
- **Supuestos:** Cumplimiento de políticas de retención de datos científicos que prohíben la pérdida irreversible de registros.
- **Riesgos:** Acumulación excesiva de señales dadas de baja que consuman cuotas de almacenamiento innecesariamente.
