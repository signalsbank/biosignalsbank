## 1. Requisitos de Negocio (_Business Requirements_)

Definen los objetivos estratégicos, la justificación institucional y el valor verificable que la solución entrega a la organización.

| ID        | Requisito                                       | Descripción                                                                                                                                                                                      | Criterio de Aceptación / Métrica (Pasa / No Pasa)                                                                                                                                                                                                                                                                                                                                                                  |
| --------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **RN-01** | **Soberanía y Gestión Local de Datos**          | La plataforma debe proveer a la UNViMe un repositorio centralizado y autónomo para almacenar, catalogar y gobernar registros de bioseñales generados en actividades de investigación y docencia. | **100% de los datos** alojados y procesados en infraestructura propia o bajo control administrativo directo de la universidad.                                                                                                                                                                                                                                                                                     |
| **RN-02** | **Ventana de Entrega Operativa**                | El sistema debe encontrarse desplegado, verificado y validado antes del inicio del ciclo lectivo 2027.                                                                                           | Acta formal de homologación y despliegue productivo firmada a más tardar el **15 de febrero de 2027**.                                                                                                                                                                                                                                                                                                             |
| **RN-03** | **Soporte y Adopción Curricular**               | El sistema debe integrarse formalmente como recurso didáctico en las asignaturas vinculadas al análisis y procesamiento de bioseñales.                                                           | Incorporación documentada del uso del software en al menos **dos (2) programas de cátedra o guías oficiales de trabajos prácticos** de la UNViMe durante el primer semestre de 2027.                                                                                                                                                                                                                               |
| **RN-04** | **Difusión y Promoción de la Oferta Académica** | La plataforma debe operar como un instrumento tecnológico de divulgación institucional para visibilizar las carreras de Bioingeniería y áreas de la salud afines ante potenciales ingresantes.   | Integración en la portada pública del sistema de un módulo o banner visible de información vocacional con hipervínculo directo al portal oficial de admisiones e inscripciones de la UNViMe.<br>Demostración interactiva y operativa del sistema en al menos **una (1) jornada institucional de difusión de carreras** (ej. Expo Carreras o Jornada de Puertas Abiertas) previa o concomitante al ingreso 2027<br> |

## 2. Requisitos de los Interesados (_Stakeholder Requirements_)

| Interesado                       | ID        | Necesidad / Expectativa                                                                                                                                            |
| -------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Universidad (UNViMe)**         | **RI-01** | Disponer de un desarrollo tecnológico propio con impacto en la comunidad académica que sirva como modelo de extensión y docencia.                                  |
| **GAB (Grupo de Bioingeniería)** | **RI-02** | Poder persistir y organizar las bioseñales recolectadas en hospitales e instituciones sanitarias asociadas.                                                        |
| **Estudiantes (ECS / EMA)**      | **RI-03** | Inspeccionar y ejercitar el análisis de señales clínicas sin depender de programas de escritorio con licencias comerciales o instalaciones complejas.              |
| **Docentes de Cátedra**          | **RI-04** | Contar con un repositorio ordenado de casos biomédicos con patologías clasificadas para formular actividades prácticas de evaluación y análisis.                   |
| **Equipo de Desarrollo**         | **RI-05** | • **Desarrollo de competencias profesionales:** Aplicar ingeniería de software, seguridad de datos médicos y procesamiento digital de señales en un caso real.<br> |

• **Precedente académico vinculante:** Consolidar el proyecto como antecedente formal curricular, proyecto de extensión o base para trabajo final de graduación.

## 3. Requisitos Funcionales (_Functional Requirements_)

### 3.1. Control de Acceso y Gestión de Perfiles

- **RF-01 (Control de Acceso Basado en Roles - RBAC):** El sistema debe proveer autenticación segura diferenciando dos perfiles:
- **Administrador (GAB / Docentes designados):** Carga masiva de señales, edición y curaduría de metadatos, eliminación de archivos, gestión de usuarios y trazabilidad de eventos.
- **Consultor (Estudiantes / Usuarios autorizados):** Exploración del catálogo, visualización interactiva multicanal, ajuste de escalas y exportación de datos autorizados.

- **RF-02 (Cierre de Sesión por Inactividad):** Toda sesión autenticada con rol Administrador debe expirar automáticamente tras 30 minutos sin interacción.
- **RF-03 (Acceso Público Demostrativo):** El sistema debe ofrecer una sección pública (sin credenciales) que permita visualizar una señal de demostración e incluya la vinculación institucional a las carreras de la UNViMe (soporte de RN-04).

### 3.2. Ingesta, Anonimización y Gestión de Registros

- **RF-04 (Soporte Estándar EDF/EDF+):** El sistema debe procesar la ingesta exclusiva de archivos bajo especificación `.edf` y `.edf+` (European Data Format).
- **RF-05 (Validación Estructural de Cabecera):** El sistema debe validar que el archivo posea una cabecera binaria válida, comprobando número de señales, duración del registro de datos y especificaciones de transductores antes de confirmar la carga.
- **RF-06 (Sanitización y Anonimización Binaria Obligatoria):** En el proceso de ingesta, el servidor debe sobrescribir o eliminar de manera definitiva e irreversible los campos de cabecera que contengan datos de identificación personal del paciente (nombre, documento, identificación local, fecha exacta de nacimiento), garantizando el cumplimiento de la Ley 25.326.
- **RF-07 (Gestión de Metadatos Académicos):** El Administrador debe poder indexar y modificar la ficha técnica de cada estudio: tipo de señal (ECG, EEG, EMG), patología de referencia, grupo etario del paciente, equipamiento empleado y notas clínicas de orientación académica.
- **RF-08 (Baja Lógica y Confirmación):** La eliminación de señales debe quedar restringida al Administrador, requiriendo doble confirmación en pantalla y registrándose en el log de auditoría.

### 3.3. Visualización Gráfica Interactiva

- **RF-09 (Despliegue Multicanal Sincronizado):** La interfaz debe mostrar múltiples canales o derivaciones en paralelo compartiendo una escala de tiempo horizontal idéntica.
- **RF-10 (Paneo Horizontal Fluido):** El usuario debe poder desplazarse hacia adelante y hacia atrás a lo largo de toda la extensión temporal de la señal.
- **RF-11 (Control de Zoom Independiente y Global):** El visualizador debe admitir zoom temporal (eje X) y zoom de amplitud (eje Y), aplicable a toda la pantalla o de manera individual a un canal específico.
- **RF-12 (Ajuste de Escalas Clínicas):** La plataforma debe permitir configurar escalas normalizadas de lectura diagnóstica (ej. 25 mm/s y 10 mm/mV para registros de electrocardiografía).
- **RF-13 (Selector y Organización de Canales):** El usuario debe poder encender, apagar y reordenar canales en pantalla para focalizar el análisis en derivaciones concretas.

### 3.4. Exportación y Descarga

- **RF-14 (Descarga):** El sistema debe permitir descargar el archivo `.edf`.

## 4. Requisitos No Funcionales y Atributos de Calidad

### 4.1. Eficiencia de Desempeño (_Performance Efficiency_)

- **RNF-01 (Capacidad Concurrente):** El sistema debe mantener su operatividad sin degradación ante un máximo de **100 usuarios concurrentes** visualizando señales simultáneamente.
- **RNF-02 (Tiempo de Respuesta en Visualización):** El tiempo transcurrido desde que un usuario solicita una señal hasta que el primer segmento interactivo se despliega en pantalla no debe exceder los **2,5 segundos** en redes con ancho de banda ≥ 10 Mbps.
- **RNF-03 (Fluidez de Renderizado):** Las acciones interactivas de paneo y zoom deben sostener una tasa de refresco mínima de **30 cuadros por segundo (FPS)**.
- **RNF-04 (Tiempo de Procesamiento de Ingesta):** Para archivos EDF convencionales (menores a 50 MB), el tiempo de validación estructural, sanitización y persistencia no debe superar los **30 segundos**.

### 4.2. Seguridad y Privacidad (_Security_)

- **RNF-05 (Cumplimiento Legal de Privacidad):** El sistema debe ajustarse a las disposiciones de la **Ley Nacional N° 25.326 de Protección de los Datos Personales** (República Argentina), imposibilitando la reidentificación de los pacientes.
- **RNF-06 (Cifrado en Tránsito):** Toda comunicación cliente-servidor debe estar protegida bajo protocolo seguro HTTPS empleando TLS 1.3.

### 4.3. Compatibilidad y Portabilidad (_Compatibility & Portability_)

- **RNF-08 (Compatibilidad de Navegadores):** La plataforma debe funcionar sin fallas ni plugins adicionales en las dos versiones estables más recientes de los navegadores basados en Chromium (Google Chrome, Microsoft Edge, Brave), Gecko (Mozilla Firefox) y WebKit (Apple Safari).
- **RNF-09 (Adaptabilidad a Dispositivos):**
- **Escritorio y Portátiles (ancho de pantalla ≥ 1024 px):** Modo completo multicanal con visualización simultánea de hasta 32 canales.
- **Dispositivos Móviles (smartphones y tablets con pantallas < 768 px):** Interfaz adaptativa que restrinja por defecto la vista a 1 o 2 canales seleccionados por el usuario, evitando sobrecarga de memoria gráfica y optimizando el espacio visual táctil.

### 4.4. Usabilidad (_Usability_)

- **RNF-10 (Facilidad de Aprendizaje):** Un estudiante sin formación previa en la plataforma debe ser capaz de buscar, abrir y configurar la visualización de una señal en un tiempo menor a 5 minutos.

## 5. Requisitos de Transición y Preparación Operativa (_Transition Requirements_)

| ID        | Requisito                                | Criterio de Aceptación                                                                                                   |
| --------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **RT-01** | **Dataset Semilla**                      | Carga y verificación previa de al menos **30 registros EDF** (ej. 15 registros de ECG y 15 registros de EEG multicanal). |
| **RT-02** | **Despliegue en Servidor de Producción** | Puesta en marcha en los servidores asignados por la UNViMe.                                                              |

## 6. Requisitos y Restricciones del Proyecto (_Project Constraints_)

| ID        | Restricción / Requisito                 | Detalle                                                                                                                                                                                               |
| --------- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RP-01** | **Infraestructura Institucional**       | La Dirección de Informática/TIC de la UNViMe debe proveer credenciales de despliegue, asignación de subdominio institucional (`*.unvime.edu.ar`) y un mínimo de 100 GB de almacenamiento persistente. |
| **RP-02** | **Cronograma Comprometido (Hito 2027)** | **15 de febrero de 2027**: Fecha límite inamovible de entrega con pruebas de integración superadas para su incorporación en el ciclo lectivo 2027.                                                    |
| **RP-03** | **Marco Ético y de Convenios**          | Toda señal proveniente de equipos hospitalarios debe contar con el respaldo de convenios interinstitucionales y la autorización de los comités de ética correspondientes.                             |

## 7. Fundamentación Técnica del Umbral de 2,5 Segundos (RNF-02)

1. **Estándares Internacionales de Experiencia de Usuario (Core Web Vitals):**

- El indicador estándar de la industria para el renderizado del elemento visual principal es el **Largest Contentful Paint (LCP)**. Google y los consorcios web determinan que cualquier respuesta superior a 2,5 segundos degrada la experiencia de navegación a un estado no óptimo, y superar los 4 segundos genera una tasa de abandono exponencial.

2. **Arquitectura de Carga por Fragmentos (_Chunking_):**

- Un archivo `.edf` completo puede pesar entre 10 MB y más de 100 MB. Descargar y parsear el archivo completo antes de graficar causaría bloqueos de red y memoria.
- Técnicamente, la cabecera ocupa únicamente entre **2 KB y 4 KB**, y para la primera pantalla solo se requiere un bloque inicial de pocos segundos de señal (menos de 200 KB de datos numéricos).
- Con una conexión estándar (10 Mbps), la transferencia del bloque inicial demora menos de 200 ms y el renderizado gráfico por hardware en el cliente insume menos de 400 ms. Por consiguiente, **2,5 segundos es un umbral técnicamente alcanzable, robusto y profesional**, que contempla incluso la latencia de red bajo carga de 100 usuarios simultáneos.
