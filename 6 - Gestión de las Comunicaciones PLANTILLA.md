# PROCEDIMIENTO DE COMUNICACIÓN INTERNA Y EXTERNA — PLAN DE GESTIÓN DE COMUNICACIONES

## CONTROL DE VERSIONES

| Versión | Hecha por                     | Revisada por           | Aprobada por     | Fecha    | Motivo           |
| :------ | :---------------------------- | :--------------------- | :--------------- | :------- | :--------------- |
| 1.0     | Ávila Gelbes, Ignacio Nicolás | Astudillo, Mateo Tomás | Rosas, Alejandro | Sep/2026 | Versión original |

| NOMBRE DEL PROYECTO                                                           | SIGLAS DEL PROYECTO |
| :---------------------------------------------------------------------------- | :------------------ |
| Banco de Señales Biomédicas — Universidad Nacional de Villa Mercedes (UNViMe) | **BIOS**            |

---

# PARTE I — PROCEDIMIENTO DE COMUNICACIÓN INTERNA Y EXTERNA

## 1. OBJETIVO

Definir y mejorar los mecanismos de comunicación interna y externa del proyecto BioSignal, con el fin de cumplir con las exigencias formales de gestión de proyectos de la UNViMe y permitir una comunicación eficaz entre los integrantes del equipo de desarrollo, el Patrocinador, los colaboradores de carga de datos, los usuarios finales y las áreas de apoyo institucional.

## 2. ALCANCE

Este procedimiento aplica a la difusión de toda comunicación interna y/o externa del proyecto BioSignal, en cualquier soporte, durante todo su ciclo de vida (01/Ago/2026 – 27/Nov/2026), desde el Hito 1 hasta la firma del Acta de Cierre.

No forma parte del alcance la asignación de tareas técnicas del EDT (corresponde al RACI del Diccionario del EDT) ni la difusión institucional que la UNViMe realice por sus canales oficiales de prensa una vez entregado el producto.

## 3. PROPÓSITO

El presente documento tiene como propósito establecer y estandarizar el procedimiento de comunicación, tanto interna como externa, del equipo de proyecto y de las demás partes interesadas (Patrocinador, Grupo de Administradores de Bioingeniería, estudiantes y docentes de la Escuela de Ciencias de la Salud y de la Escuela de Medicina, Área de Infraestructura/TI y cátedras evaluadoras), garantizando la transferencia oportuna de información para el desarrollo del proyecto y de sus entregables.

## 4. RESPONSABILIDADES

Es responsabilidad de todos y cada uno de los integrantes del proyecto que la información difundida sea veraz, adecuada y consistente con el Acta de Constitución, el Plan de Gestión de Partes Interesadas y el Documento de Requisitos. Es obligación de todo integrante, y de cualquier persona vinculada al proyecto, aplicar las pautas determinadas en el presente documento.

| Rol                                                                     | Responsabilidad específica                                                                                                                                                                                                            |
| :---------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Patrocinador — Alejandro Rosas (Director EICA)**                      | Provee el respaldo institucional y los permisos necesarios para ejecutar los parámetros establecidos en este procedimiento. Resuelve los escalamientos de última instancia.                                                           |
| **Director del Proyecto — Astudillo, Mateo Tomás**                      | Propietario del procedimiento. Único vocero formal ante el Patrocinador y las autoridades de la UNViMe. Aprueba toda comunicación externa formal y todo informe de estado. Divulga el procedimiento y verifica su cumplimiento.       |
| **Asistente del Director del Proyecto — Ávila Gelbes, Ignacio Nicolás** | Redacta y mantiene actualizado este documento. Recepciona, controla y responde la documentación externa. Emite las actas de reunión y administra el repositorio documental. Reemplaza al PM como vocero ante su ausencia justificada. |
| **Desarrollador Backend / Infraestructura — Chiecher, Eber Blas**       | Interlocutor técnico formal con el Área de Infraestructura/TI de la UNViMe. Comunica requisitos de despliegue y ventanas de mantenimiento.                                                                                            |
| **Desarrollador Backend / QA — Herrera, Germán Ezequiel**               | Comunica resultados de pruebas, defectos detectados y su criticidad. Emite el Informe de QA.                                                                                                                                          |
| **Desarrolladora Frontend — Pereyra, Rocío**                            | Prepara el material visual de demos y canaliza el feedback de usabilidad de los usuarios finales.                                                                                                                                     |
| **Desarrollador Full-Stack / Soporte Técnico — Mosainer, Martín David** | Recepciona y registra las consultas de soporte de usuarios finales y las deriva según el método de escalamiento.                                                                                                                      |

## 5. MARCO CONCEPTUAL

- **Actas:** herramienta de comunicación en la que se plasman la participación, discusión, conclusiones y compromisos de toda reunión o convocatoria del proyecto.
- **Comunicación:** proceso en el que intervienen un emisor y un receptor, en un ambiente físico o virtual, mediante el cual se logra la transmisión e intercambio de ideas e información comprensible entre las partes.
- **Comunicación interna:** todo intercambio de información entre integrantes del equipo de gestión y desarrollo del proyecto (ST-04 a ST-09 del Registro de Interesados).
- **Comunicación externa:** conjunto de mensajes emitidos por el proyecto hacia sus públicos externos (ST-01, ST-02, ST-03, ST-10 y ST-11), orientados a mantener o mejorar la relación con ellos, informar avances y promover la adopción de la plataforma.
- **Comunicación directa:** modo de comunicación mediante lengua natural, en la que la emisión y la comprensión del mensaje son simultáneas, producida por relación interpersonal.
- **Comunicación formal:** aquella que deja registro escrito, cuenta con aprobación del PM y se archiva en el repositorio documental.
- **Comunicación informal:** intercambio operativo cotidiano, sin valor de aprobación (mensajería instantánea, comentarios en el gestor de tareas).
- **Polémica:** discrepancia, duda o conflicto que surge durante el proyecto y que requiere tratamiento, seguimiento y eventual escalamiento.
- **Vocero autorizado:** persona habilitada para representar al proyecto ante un interesado externo; por defecto, el Director del Proyecto.
- **EDF (European Data Format):** formato estándar de archivo de señales biomédicas soportado por la plataforma; término de uso frecuente en las comunicaciones con el Grupo de Administradores de Bioingeniería.
- **Anonimización:** proceso irreversible de eliminación de todo dato identificatorio de pacientes en los registros biomédicos, previo a su transmisión o almacenamiento.
- **Medio de comunicación:** toda forma oral y/o escrita que permita transmitir información dentro del proyecto.

## 6. MEDIOS DE COMUNICACIÓN

1. Reuniones de equipo (standup semanal).
2. Reuniones formales de hito con el Patrocinador.
3. Reuniones técnicas con el Área de Infraestructura/TI.
4. Correo electrónico institucional de la UNViMe.
5. Mensajería instantánea del grupo del proyecto.
6. Gestor de tareas y repositorio de código (issues y revisiones de código).
7. Informes escritos (informe de hito, informe de QA, informe de feedback).
8. Actas de reunión.
9. Presentaciones y demostraciones (demos) a usuarios finales.
10. Comunicación directa (verbal).
11. Encuestas y formularios de feedback de usabilidad.
12. Repositorio documental del proyecto.
13. Entrega formal de documentación a cátedras evaluadoras.

## 7. PROCEDIMIENTO DE COMUNICACIÓN INTERNA

### 7.1 Aspectos generales

De forma general, la comunicación interna del proyecto se presenta en documentos oficiales (actas, informes y registros del gestor de tareas). El Director del Proyecto y su Asistente informan internamente sobre las actividades con los siguientes objetivos:

- Notificar al equipo el estado de avance, los desvíos de cronograma y los cambios de alcance aprobados.
- Atender dudas, bloqueos e impedimentos que afecten la ejecución de los entregables.
- Difundir las decisiones tomadas y los compromisos asumidos, con responsable y fecha.
- Comunicar los resultados de las pruebas de QA y las acciones correctivas derivadas.

### 7.2 Temas a tratar en la comunicación interna

- Estado de tareas, bloqueos y cambios de alcance.
- Difusión de versiones nuevas de los documentos de gestión del proyecto.
- Resultados de revisiones de código y de ciclos de prueba.
- Cambios de disponibilidad del equipo (períodos de examen — riesgo R3 del Acta).
- Actas de reunión y acuerdos alcanzados.
- Documentación compartida interna y externa.

### 7.3 Flujo del procedimiento interno

1. **Identificación de la necesidad.** Cualquier integrante detecta información que debe comunicarse (avance, bloqueo, defecto, cambio de disponibilidad).
2. **Selección del medio.** Si la información es operativa y no compromete alcance, cronograma, calidad ni riesgos, se emplea un medio informal; en caso contrario, un medio formal.
3. **Emisión.** Se emite indicando asunto, hito de referencia y acción esperada del destinatario.
4. **Registro.** El Asistente del PM asegura que quede asentada en el acta semanal o en el gestor de tareas.
5. **Seguimiento.** El PM verifica el cumplimiento de las acciones comprometidas en la reunión semanal y las reasigna si corresponde.

> **Regla general:** toda decisión relevante acordada por un medio informal debe confirmarse por un medio formal. Lo que no está registrado, no fue decidido.

## 8. PROCEDIMIENTO DE COMUNICACIÓN EXTERNA

### 8.1 Aspectos generales

Se considera comunicación externa la dirigida a:

- Patrocinador Institucional (Escuela de Ingeniería y Ciencias Ambientales — EICA).
- Grupo de Administradores de Bioingeniería (colaboradores de carga de datos).
- Usuarios finales: estudiantes y docentes de la Escuela de Ciencias de la Salud y de la Escuela de Medicina.
- Área de Infraestructura / TI de la UNViMe.
- Cátedras y evaluadores académicos.

### 8.2 Flujo del procedimiento externo

1. **Elaboración del borrador** por el responsable de comunicar indicado en la Matriz de Comunicaciones.
2. **Revisión y aprobación previa del Director del Proyecto.** En su ausencia justificada, del Asistente del PM.
3. **Emisión por canal oficial:** exclusivamente correo institucional o reunión formal. No se admite el uso de canales personales para comunicaciones formales.
4. **Solicitud de acuse de recibo** en toda comunicación que requiera aprobación, entrega de datos o provisión de infraestructura.
5. **Archivo** de la comunicación y su respuesta en el repositorio documental, por parte del Asistente del PM.

### 8.3 Recepción, documentación y respuesta

Se responde a las solicitudes de información o comunicaciones de las partes externas interesadas cuando son relevantes. Se consideran relevantes:

- Quejas, reclamos o reportes de fallas de la plataforma por parte de usuarios finales.
- Observaciones o solicitudes de cambio provenientes del Patrocinador.
- Requerimientos, restricciones o negativas del Área de Infraestructura/TI respecto del entorno de despliegue.
- Consultas del Grupo de Administradores de Bioingeniería sobre formato, anonimización o fechas límite de carga de archivos EDF.
- Observaciones formales de las cátedras evaluadoras sobre la documentación entregada.

La recepción, control y respuesta de la documentación externa es responsabilidad del Asistente del Director del Proyecto, con aprobación previa del PM. El plazo máximo de respuesta es de **72 horas hábiles**.

### 8.4 Requisitos de confidencialidad y privacidad

Dado que el proyecto opera con señales biomédicas de origen clínico, rigen las siguientes reglas sobre la información comunicada:

1. Ninguna comunicación, interna o externa, puede incluir datos personales o clínicos identificables de pacientes (restricción legal del Acta de Constitución y requisito RNF-04).
2. El intercambio de archivos EDF con el Grupo de Administradores de Bioingeniería se realiza exclusivamente por los canales institucionales acordados.
3. Antes de incorporar un lote de señales al catálogo, el Asistente del PM confirma por escrito que la anonimización fue realizada en origen.
4. El material de demos y presentaciones emplea únicamente registros anonimizados ya validados.
5. Toda comunicación externa debe dejar explícito que la plataforma tiene fines exclusivamente académicos y no constituye una herramienta de diagnóstico clínico.

---

# PARTE II — PLAN DE GESTIÓN DE COMUNICACIONES

## 9. COMUNICACIONES DEL PROYECTO

Ver **Matriz de Comunicaciones del Proyecto — versión 1.0**, adjunta en la Sección 14 del presente documento.

## 10. PROCEDIMIENTO PARA TRATAR POLÉMICAS

1. Se captan las polémicas a través de la observación y la conversación, o mediante una persona o grupo que las exprese formalmente (reunión semanal, correo institucional o gestor de tareas).
2. Se codifican y registran en el **Log de Control de Polémicas**:

### LOG DE CONTROL DE POLÉMICAS

| Código de Polémica | Descripción | Involucrados | Enfoque de Solución | Acciones de Solución | Responsable | Fecha | Resultado Obtenido |
| :----------------- | :---------- | :----------- | :------------------ | :------------------- | :---------- | :---- | :----------------- |
| POL-01             |             |              |                     |                      |             |       |                    |
| POL-02             |             |              |                     |                      |             |       |                    |
| POL-03             |             |              |                     |                      |             |       |                    |

3. Se revisa el Log de Control de Polémicas en la reunión semanal de coordinación, con el fin de:
   a. Determinar las soluciones a aplicar a las polémicas pendientes de análisis, designar un responsable y un plazo de solución, y registrar la programación en el Log.
   b. Verificar si las soluciones programadas se están aplicando; de no ser así, se toman acciones correctivas.
   c. Verificar si las soluciones aplicadas fueron efectivas y si la polémica quedó resuelta; de no ser así, se diseñan nuevas soluciones (se retorna al paso «a»).

4. Si una polémica no puede resolverse, o evolucionó hasta convertirse en un problema, se aborda mediante el siguiente método de escalamiento:

| Instancia   | Quiénes intervienen                                                                         | Método                                     | Plazo máximo de respuesta          |
| :---------- | :------------------------------------------------------------------------------------------ | :----------------------------------------- | :--------------------------------- |
| **Primera** | Director del Proyecto y Asistente del PM                                                    | Método estándar de resolución de problemas | 24 h hábiles                       |
| **Segunda** | Director del Proyecto, Asistente del PM y los miembros pertinentes del equipo de desarrollo | Método estándar de resolución de problemas | 48 h hábiles                       |
| **Tercera** | Patrocinador (Alejandro Rosas), Director del Proyecto y miembros pertinentes                | Negociación y/o solución de conflictos     | 72 h hábiles                       |
| **Última**  | Patrocinador, o Patrocinador junto con las autoridades de la EICA si lo considera necesario | Decisión institucional                     | Según disponibilidad institucional |

> Todo escalamiento a tercera instancia o superior debe registrarse por escrito consignando: hecho, impacto sobre el cronograma o el alcance, alternativas evaluadas y decisión solicitada.

## 11. PROCEDIMIENTO PARA ACTUALIZAR EL PLAN DE GESTIÓN DE COMUNICACIONES

El Plan de Gestión de Comunicaciones deberá revisarse y/o actualizarse cada vez que:

1. Se apruebe una solicitud de cambio que impacte el Plan de Proyecto.
2. Se adopte una acción correctiva que impacte los requerimientos o necesidades de información de los interesados.
3. Ingresen o salgan personas del proyecto.
4. Se modifiquen las asignaciones de personas a roles del proyecto.
5. Cambie la matriz de poder/influencia de los interesados respecto del Plan de Gestión de Partes Interesadas.
6. Se reciban solicitudes inusuales de informes o reportes adicionales.
7. Existan quejas, sugerencias, comentarios o evidencias de requerimientos de información no satisfechos.
8. Se evidencie resistencia al cambio o baja adopción por parte de los usuarios finales.
9. Se evidencien deficiencias de comunicación dentro del proyecto o hacia el exterior.
10. Se produzca el cierre de cada uno de los cinco hitos del cronograma.

La actualización deberá seguir los siguientes pasos:

1. Identificación y clasificación de interesados.
2. Determinación de requerimientos de información.
3. Elaboración o ajuste de la Matriz de Comunicaciones del Proyecto.
4. Actualización del Plan de Gestión de Comunicaciones.
5. Aprobación del Plan por parte del Director del Proyecto y del Patrocinador.
6. Difusión de la nueva versión del Plan al equipo y a los interesados externos afectados.

## 12. GUÍAS PARA EVENTOS DE COMUNICACIÓN

### 12.1 Guías para reuniones

Todas las reuniones deberán seguir las siguientes pautas:

1. Debe fijarse la agenda con anterioridad (mínimo 48 h para reuniones formales).
2. Debe coordinarse e informarse fecha, hora y lugar (o enlace) con los participantes.
3. Debe comenzar puntualmente.
4. Deben fijarse los objetivos de la reunión, los roles (al menos facilitador y anotador), el modo de trabajo grupal y el método de solución de controversias.
5. Deben cumplirse cabalmente los roles de facilitador (dirige el proceso grupal) y de anotador (registra los resultados formales). Por defecto, el facilitador es el PM y el anotador es el Asistente del PM.
6. Debe terminar puntualmente.
7. Debe emitirse un Acta de Reunión, distribuida a los participantes dentro de las 48 h posteriores y sujeta a revisión por parte de ellos. Si no se reciben observaciones en 72 h, se considera aprobada.

### 12.2 Guías para correo electrónico

Todos los correos electrónicos deberán seguir las siguientes pautas:

1. Los correos entre el equipo de proyecto y los interesados externos (Patrocinador, Bioingeniería, Infraestructura/TI, usuarios finales, cátedras) deben ser enviados por el Director del Proyecto, o con copia a él, de modo de establecer una única vía formal de comunicación externa.
2. Los correos enviados por un interesado externo y recibidos por cualquier integrante del equipo deben reenviarse con copia al Director del Proyecto y al Asistente del PM, si no fueron incluidos originalmente, para que las comunicaciones externas estén en conocimiento de los responsables de la dirección del proyecto.
3. Los correos internos entre miembros del equipo deben copiarse a la lista de distribución del proyecto, para que todos permanezcan informados de lo que sucede.
4. Todo correo debe consignar en el asunto el código del proyecto y el hito de referencia (ejemplo: `BIOS — Hito 3 — Convocatoria a demo`).
5. Se utiliza exclusivamente el correo institucional de la UNViMe para comunicaciones formales.

## 13. GUÍAS PARA DOCUMENTACIÓN DEL PROYECTO

### 13.1 Guías para codificación de documentos

La codificación de los documentos del proyecto será la siguiente:

**AAAA_BBB_CCC.DDD**

Donde:

- **AAAA** = Código del Proyecto = `BIOS`
- **BBB** = Abreviatura del Tipo de Documento = `act` (acta de constitución), `req` (documento de requisitos), `edt` (EDT), `dedt` (diccionario del EDT), `sth` (plan de interesados), `com` (plan/procedimiento de comunicaciones), `rsk` (registro de riesgos), `qa` (informe de QA), `min` (acta de reunión), `cie` (acta de cierre), etc.
- **CCC** = Versión del Documento = `v1_0`, `v2_0`, etc.
- **DDD** = Formato del Archivo = `md`, `docx`, `pdf`, `xlsx`, etc.

Ejemplo: `BIOS_com_v1_0.md` (el presente documento).

### 13.2 Guías para almacenamiento de documentos

1. Durante la ejecución del proyecto, cada integrante mantendrá una carpeta con la misma estructura que el EDT del proyecto, donde guardará en las subcarpetas correspondientes las versiones de los documentos que vaya generando.
2. Al cierre de cada hito, cada integrante eliminará los archivos temporales de trabajo y conservará únicamente las versiones controladas y numeradas, las cuales se enviarán al Director del Proyecto.
3. El Director del Proyecto consolidará todas las versiones controladas en el archivo final del proyecto, organizado con la misma estructura del EDT. Esta carpeta se archivará en el repositorio documental del proyecto y se guardará protegida contra escritura.
4. Se publicará una Relación de Documentos del Proyecto con su ruta de acceso para consulta.
5. Los integrantes eliminarán sus carpetas de trabajo para evitar redundancia de información y multiplicidad de versiones.

### 13.3 Guías para recuperación y reparto de documentos

1. La recuperación de documentos desde el repositorio del proyecto es libre para todos los integrantes del equipo.
2. La recuperación por parte de miembros de la UNViMe ajenos al equipo requiere autorización del Director del Proyecto.
3. El acceso a la información del proyecto por parte de personas externas a la UNViMe requiere autorización del Patrocinador, ya que la información se considera de uso interno del proyecto.
4. El reparto de documentos digitales e impresos es responsabilidad del Director del Proyecto, con apoyo del Asistente del PM.
5. Ningún documento que contenga registros biomédicos no anonimizados puede ser repartido ni almacenado, conforme a la Sección 8.4.

## 14. GUÍAS PARA EL CONTROL DE VERSIONES

1. Todos los documentos de gestión del proyecto están sujetos a control de versiones, el cual se realiza insertando una cabecera estándar con el siguiente diseño:

### CONTROL DE VERSIONES

| Código de Versión | Hecha por | Revisada por | Aprobada por | Fecha | Motivo |
| :---------------- | :-------- | :----------- | :----------- | :---- | :----- |
|                   |           |              |              |       |        |
|                   |           |              |              |       |        |

2. Cada vez que se emite una versión del documento se completa una fila de la cabecera, anotando la versión, quién la emitió, quién la revisó, quién la aprobó, a qué fecha corresponde y por qué motivo se emitió.
3. Debe existir correspondencia entre el código de versión de la cabecera y el que figura en el nombre del archivo, según la guía de codificación:

**AAAA_BBB_CCC.DDD** — donde `AAAA` = `BIOS`, `BBB` = tipo de documento, `CCC` = versión, `DDD` = formato.

## 15. GLOSARIO DE TERMINOLOGÍA DEL PROYECTO

Ver **Marco Conceptual** (Sección 5 del presente documento) y el Glosario de Terminología del Proyecto — versión 1.0.

---

# MATRIZ DE COMUNICACIONES DEL PROYECTO

## CONTROL DE VERSIONES

| Versión | Hecha por                     | Revisada por           | Aprobada por     | Fecha    | Motivo           |
| :------ | :---------------------------- | :--------------------- | :--------------- | :------- | :--------------- |
| 1.0     | Ávila Gelbes, Ignacio Nicolás | Astudillo, Mateo Tomás | Rosas, Alejandro | Sep/2026 | Versión original |

| NOMBRE DEL PROYECTO                  | SIGLAS DEL PROYECTO |
| :----------------------------------- | :------------------ |
| Banco de Señales Biomédicas — UNViMe | **BIOS**            |

## Comunicaciones externas

| Información                       | Contenido                                                                                        | Formato                   | Nivel de Detalle | Responsable de Comunicar                          | Grupo Receptor                                           | Metodología o Tecnología                       | Frecuencia de Comunicación                         | Elemento EDT / Hito        |
| :-------------------------------- | :----------------------------------------------------------------------------------------------- | :------------------------ | :--------------- | :------------------------------------------------ | :------------------------------------------------------- | :--------------------------------------------- | :------------------------------------------------- | :------------------------- |
| Iniciación del Proyecto           | Datos y comunicación sobre la iniciación del proyecto                                            | Acta de Constitución      | Medio            | Director del Proyecto                             | Patrocinador (EICA), Bioingeniería, cátedras evaluadoras | Documento digital vía correo institucional     | Una sola vez                                       | 1.1 Inicio                 |
| Planificación del Proyecto        | Planificación detallada: alcance, tiempo, calidad, comunicaciones, interesados y riesgos         | Plan del Proyecto         | Muy alto         | Director del Proyecto                             | Patrocinador, cátedras evaluadoras                       | Documento digital vía correo institucional     | Una sola vez                                       | 1.2 Planificación          |
| Estado del Proyecto               | Estado actual, avance sobre el hito, riesgos, desvíos y aprobaciones requeridas                  | Informe de Hito           | Alto             | Director del Proyecto                             | Patrocinador (Alejandro Rosas)                           | Documento digital + reunión formal             | Por hito (5 instancias)                            | 1.3 Seguimiento y control  |
| Escalamiento de riesgos           | Riesgo identificado, impacto, alternativas y decisión solicitada                                 | Nota de escalamiento      | Alto             | Director del Proyecto                             | Patrocinador                                             | Correo institucional + reunión extraordinaria  | Dentro de las 48 h de identificado                 | 1.3 Seguimiento y control  |
| Provisión de señales EDF          | Requerimientos de datos, formatos aceptados, criterios de anonimización y fechas límite de carga | Solicitud formal de datos | Alto             | Asistente del Director del Proyecto               | Grupo de Administradores de Bioingeniería                | Correo institucional / reunión                 | Quincenal o según necesidad, desde el Hito 1       | Hito 1 — Arquitectura Base |
| Recepción y validación de datos   | Confirmación de recepción, resultado de la verificación de formato ".edf" y de anonimización     | Registro de recepción     | Medio            | Asistente del Director del Proyecto               | Grupo de Administradores de Bioingeniería                | Correo institucional                           | Dentro de los 5 días hábiles de cada lote recibido | Hito 2 — Motor Backend     |
| Disponibilidad de la plataforma   | Anuncio de disponibilidad, instructivos de uso y convocatoria a demostración                     | Comunicado + instructivo  | Medio            | Director del Proyecto / Asistente del PM          | Usuarios finales (ECS y EM)                              | Correo institucional + presentación presencial | Al finalizar el Hito 3 y en el cierre              | Hito 3 — Visor Frontend    |
| Feedback de usabilidad            | Observaciones de usuarios sobre visor, anotaciones y facilidad de uso                            | Informe de Feedback       | Medio            | Desarrolladora Frontend                           | Equipo del proyecto y Director del Proyecto              | Formulario en línea / relevamiento en demo     | Posterior a cada demo                              | Hito 3 — Visor Frontend    |
| Requisitos de despliegue          | Requerimientos técnicos del entorno de producción y permisos necesarios                          | Requerimiento Técnico     | Alto             | Desarrollador de Infraestructura                  | Área de Infraestructura / TI de la UNViMe                | Correo institucional + reunión técnica         | Contacto formal antes del Hito 5                   | Hito 5 — Entrega Final     |
| Ventanas de mantenimiento         | Fechas y duración de intervenciones sobre el entorno de producción                               | Comunicado técnico        | Medio            | Desarrollador de Infraestructura (V.° B.° del PM) | Área de Infraestructura / TI                             | Correo institucional                           | Con 7 días de anticipación a cada intervención     | Hito 5 — Entrega Final     |
| Documentación formal del proyecto | Acta de Constitución, requisitos, EDT, riesgos, interesados y comunicaciones                     | Entrega documental        | Muy alto         | Director del Proyecto                             | Cátedras / evaluadores académicos                        | Entrega formal + presentación                  | Según cronograma académico                         | 1.4 Documentación          |
| Cierre del Proyecto               | Datos y comunicación sobre el cierre del proyecto y aceptación de entregables                    | Acta de Cierre            | Medio            | Director del Proyecto                             | Patrocinador, cátedras evaluadoras, usuarios finales     | Documento digital + reunión formal             | Una sola vez, antes del 27/Nov/2026                | 1.5 Cierre                 |

## Comunicaciones internas

| Información                     | Contenido                                                                        | Formato                           | Nivel de Detalle | Responsable de Comunicar            | Grupo Receptor                           | Metodología o Tecnología                           | Frecuencia de Comunicación                  | Elemento EDT / Hito       |
| :------------------------------ | :------------------------------------------------------------------------------- | :-------------------------------- | :--------------- | :---------------------------------- | :--------------------------------------- | :------------------------------------------------- | :------------------------------------------ | :------------------------ |
| Coordinación del Proyecto       | Información detallada de la reunión de coordinación: avance, bloqueos y acuerdos | Acta de Reunión                   | Alto             | Director del Proyecto               | Equipo completo                          | Reunión (presencial o virtual) + documento digital | Semanal                                     | 1.3 Seguimiento y control |
| Avance de tareas                | Estado individual de tareas asignadas y estimación de finalización               | Registro en gestor de tareas      | Medio            | Cada desarrollador                  | Director del Proyecto y Asistente del PM | Gestor de tareas                                   | Continuo, con corte semanal                 | Hitos 1 a 5               |
| Bloqueos e impedimentos         | Descripción del bloqueo, impacto y apoyo requerido                               | Ticket de bloqueo                 | Alto             | Quien lo detecta                    | Director del Proyecto                    | Mensajería instantánea + gestor de tareas          | Inmediato al detectarse                     | Hitos 1 a 5               |
| Revisión técnica de código      | Observaciones sobre los cambios propuestos y su aprobación                       | Revisión de código (pull request) | Alto             | Autor del cambio                    | Desarrollador revisor asignado           | Repositorio de código                              | Por cada entrega de código                  | Hitos 2 a 4               |
| Resultados de pruebas           | Defectos detectados, criticidad, casos de prueba ejecutados y resultados         | Informe de QA                     | Alto             | Desarrollador Backend / QA          | Equipo completo y Director del Proyecto  | Gestor de tareas + reunión semanal                 | Por ciclo de pruebas y al cierre del Hito 5 | Hito 5 — QA y Entrega     |
| Disponibilidad del equipo       | Períodos de examen y reducción prevista de horas de dedicación                   | Aviso de disponibilidad           | Medio            | Integrante afectado                 | Director del Proyecto                    | Correo o mensajería instantánea                    | Con 7 días de anticipación                  | 1.3 Seguimiento y control |
| Cambios de alcance o cronograma | Cambio aprobado, justificación e impacto sobre tareas y fechas                   | Acta + cronograma actualizado     | Alto             | Director del Proyecto               | Equipo completo                          | Reunión + documento digital                        | Ante cada cambio aprobado                   | 1.3 Seguimiento y control |
| Control de polémicas            | Polémicas registradas, soluciones programadas y resultados obtenidos             | Log de Control de Polémicas       | Alto             | Asistente del Director del Proyecto | Equipo completo                          | Reunión semanal + documento digital                | Semanal                                     | 1.3 Seguimiento y control |
| Cierre de hito interno          | Revisión de entregables del hito, lecciones aprendidas y pendientes              | Acta de Cierre de Hito            | Alto             | Director del Proyecto               | Equipo completo                          | Reunión + documento digital                        | Al finalizar cada uno de los 5 hitos        | Hitos 1 a 5               |

---

## APROBACIÓN

| Firma                         | Rol                                 | Fecha |
| :---------------------------- | :---------------------------------- | :---- |
| Rosas, Alejandro              | Director de EICA (Patrocinador)     |       |
| Astudillo, Mateo Tomás        | Director del Proyecto (PM)          |       |
| Ávila Gelbes, Ignacio Nicolás | Asistente del Director del Proyecto |       |
