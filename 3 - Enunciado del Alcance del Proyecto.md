# Enunciado del Alcance del Proyecto

## 1. Descripción del Proyecto

El proyecto **"BioSignal"** consiste en el diseño, desarrollo, verificación y despliegue productivo de una plataforma web centralizada para la ingesta, gestión, gobernanza y visualización gráfica interactiva de registros de bioseñales biomédicas (ECG, EEG, EMG). Su objetivo es dotar a la Universidad Nacional de Villa Mercedes (UNViMe) de un repositorio y visualizador institucional soberano alojado en infraestructura propia, eliminando la dependencia de herramientas externas rígidas o bajo licencia (como LightWAVE), y sirviendo como recurso didáctico y de divulgación para la carrera de Bioingeniería, la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM).

## 2. Alcance

### 2.1. Alcance del Producto

Comprende las propiedades funcionales y los requerimientos técnicos y normativos de la solución de software:

#### Características del Producto (Propiedades Funcionales)

1. **Control de Acceso Basado en Roles (RBAC):** Autenticación y control de accesos diferenciado para dos perfiles: _Administrador_ (gestión integral de usuarios, carga masiva, curaduría de metadatos, baja lógica y auditoría) y _Consultor_ (exploración de catálogo, visualización interactiva multicanal, ajuste de escalas y descarga de señales).
2. **Cierre de Sesión por Inactividad:** Expiración y revocación automática de sesión tras 30 minutos sin interacción para el perfil Administrador.
3. **Acceso Público Demostrativo e Institucional:** Sección pública (sin credenciales) con un visualizador interactivo precargado con una señal de prueba y banners con enlaces directos al portal oficial de admisiones de la UNViMe.
4. **Ingesta y Validación Binaria de Cabecera:** Motor de procesamiento exclusivo para archivos `.edf` y `.edf+` con verificación de estructura (número de señales, duración del registro y transductores) antes de confirmar la carga.
5. **Sanitización y Anonimización Binaria Obligatoria:** Mecanismo en servidor que sobrescribe o elimina irreversiblemente los datos de identificación personal del paciente en la cabecera (nombre, ID, documento, fecha de nacimiento), dando cumplimiento a la Ley 25.326.
6. **Gestión de Metadatos Académicos:** Ficha técnica estructurada e indexable para cada estudio: tipo de señal (ECG, EEG, EMG), patología de referencia, grupo etario, equipamiento y notas clínicas.
7. **Visualización Gráfica Interactiva Multicanal:** Despliegue simultáneo de señales compartiendo una misma base temporal horizontal, con navegación fluida (paneo), zoom temporal (eje X) y de amplitud (eje Y) global o independiente, y ajuste a escalas clínicas normalizadas (25 mm/s, 10 mm/mV).
8. **Selector y Organización de Canales:** Controles para encender, apagar y reordenar visualmente las derivaciones en pantalla.
9. **Exportación y Descarga:** Funcionalidad para descargar el archivo `.edf` anonimizado y persistido en el repositorio.
10. **Dataset Semilla:** Base de datos productiva provista inicialmente con al menos 30 estudios EDF categorizados (15 ECG y 15 EEG multicanal).

#### Requerimientos del Producto (Condiciones Técnicas y Normativas)

- **Formato Estándar:** Soporte exclusivo de especificaciones `.edf` y `.edf+`, funcionando nativamente en el navegador sin extensiones ni complementos locales.

- **Seguridad y Privacidad:** Cumplimiento estricto de la Ley Nacional N° 25.326 de Protección de los Datos Personales (imposibilidad técnica y legal de reidentificación) y cifrado de comunicaciones cliente-servidor bajo protocolo HTTPS con TLS 1.3.

- **Desempeño y Rendimiento:**
- Soporte operativo para hasta 100 usuarios concurrentes en visualización simultánea sin degradación del servicio.
- Tiempo de respuesta inicial (despliegue del primer segmento interactivo) ≤ 2,5 segundos en conexiones de red ≥ 10 Mbps (arquitectura de carga por fragmentos / _chunking_).
- Tasa de refresco gráfica sostenida de al menos 30 FPS durante el paneo continuo y zoom interactivo.

- Tiempo de procesamiento de ingesta (validación, sanitización y persistencia) ≤ 30 segundos para archivos menores a 50 MB.

- **Compatibilidad Cross-Browser:** Ejecución idéntica y sin errores en las dos (2) versiones estables más recientes de los navegadores basados en Chromium (Chrome, Edge), Gecko (Firefox) y WebKit (Safari).

- **Diseño Adaptativo (_Responsive_):** Visualización multicanal de hasta 32 canales en pantallas de escritorio (≥ 1024 px) y modo táctil simplificado de 1 a 2 canales para dispositivos móviles (< 768 px).
- **Usabilidad Intuitiva:** Interfaz autocontenida que permite a un usuario sin formación previa buscar, abrir y configurar una señal en menos de 5 minutos, prescindiendo de manuales o capacitaciones.

### 2.2. Alcance del Proyecto

Abarca todo el trabajo técnico, de integración y de calidad necesario para construir y entregar la plataforma operativa, organizado en función de los hitos formales del proyecto:

```
[Hito 1: Aprobación del Acta de Constitución]
   ↓
[Hito 2: Documento de Requisitos Aprobado]
   ↓
[Hito 3: Módulo de Autenticación Listo]
   ↓
[Hito 4: Módulo de Gestión de Señales Listo]
   ↓
[Hito 5: Visualizador de Señales Listo]
   ↓
[Hito 6: Despliegue]
   ↓
[Hito 7: Aprobación del Acta de Cierre (≤ 15/Feb/2027)]

```

#### Fases de Ejecución del Proyecto

- **Fase 1: Iniciación y Definición de Requisitos:** Formalización del proyecto, relevamiento, análisis técnico y especificación de requisitos y criterios de aceptación.
- _Hito 1: Aprobación del Acta de Constitución._
- _Hito 2: Documento de Requisitos Aprobado._

- **Fase 2: Seguridad y Control de Acceso:** Desarrollo de la capa de autenticación, control de sesiones, caducidad por inactividad a los 30 minutos y permisos según perfiles RBAC.
- _Hito 3: Módulo de Autenticación Listo._

- **Fase 3: Backend, Ingesta y Gestión de Señales:** Desarrollo del parser EDF, validaciones binarias de cabecera, sanitización irreversible (Ley 25.326), endpoints de baja lógica y persistencia del catálogo de metadatos clínicos.
- _Hito 4: Módulo de Gestión de Señales Listo._

- **Fase 4: Frontend y Visualizador Gráfico:** Implementación de la interfaz de usuario, renderizado de señales por fragmentos (_chunking_), controles de navegación temporal y ganancia, calibración de escalas normalizadas (25 mm/s, 10 mm/mV), selector de canales y sección pública demostrativa.
- _Hito 5: Visualizador de Señales Listo._

- **Fase 5: Aseguramiento de Calidad y Despliegue en Servidores:** Ejecución de pruebas de carga concurrente (100 usuarios), verificación de latencia (≤ 2,5 s) y fluidez (≥ 30 FPS), pruebas de compatibilidad en navegadores, auditoría binaria de cabeceras, carga del dataset semilla (≥ 30 archivos EDF) y puesta en marcha en los servidores de la UNViMe bajo subdominio institucional.

- _Hito 6: Despliegue._

- **Fase 6: Homologación y Cierre del Proyecto:** Verificación final de criterios de aceptación con los interesados, entrega de repositorios de código y firma del acta formal de homologación y cierre.
- _Hito 7: Aprobación del Acta de Cierre (a más tardar el 15 de febrero de 2027)._

## 3. Entregables del Proyecto y del Producto

### 3.1. Entregables del Producto (Software)

- **EP-01: Módulo de Autenticación y Autorización:** Componente RBAC configurado para Administrador y Consultor, con revocación de sesión a los 30 minutos de inactividad.
- **EP-02: Módulo de Ingesta, Validación y Gestión de Señales:** Backend para carga, parseo de cabecera EDF/EDF+, sanitización definitiva de datos personales y confirmación de baja lógica con trazabilidad.
- **EP-03: Visualizador Web Interactivo de Bioseñales:** Interfaz de usuario con renderizado fluido a ≥ 30 FPS, paneo temporal, zoom bidireccional, ajuste de escalas diagnósticas y selector interactivo de canales.

- **EP-04: Módulo de Acceso Público y Enlace Institucional:** Vista de acceso libre con señal interactiva de prueba y banners de vinculación al portal de admisiones de la UNViMe.
- **EP-05: Módulo de Exportación:** Mecanismo de descarga directa de archivos EDF anonimizados.
- **EP-06: Dataset Semilla Cargado:** Repositorio en producción poblado con un mínimo de 30 registros biomédicos EDF catalogados.

### 3.2. Entregables del Proyecto (Gestión, Calidad y Cierre)

- **EJ-01: Acta de Constitución del Proyecto:** Documento formal de inicio debidamente aprobado y firmado.
- **EJ-02: Documento de Especificación de Requisitos y Matriz de Trazabilidad:** Documento de requisitos aprobado por las partes.
- **EJ-03: Repositorios de Código Fuente:** Código fuente versionado en Git (frontend y backend) con los scripts necesarios para la compilación y ejecución de la aplicación.
- **EJ-04: Reporte Consolidado de Aseguramiento de la Calidad (QA):** Informes y evidencias de pruebas de estrés (100 usuarios), telemetría de tiempos de respuesta, pruebas _cross-browser_ y auditoría forense de cabeceras EDF sanitizadas.

- **EJ-05: Acta de Despliegue Operativo:** Constancia técnica de instalación y puesta en marcha exitosa en los servidores institucionales de la UNViMe.
- **EJ-06: Acta de Homologación y Cierre:** Documento formal de aceptación final del proyecto debidamente firmado.

## 4. Criterios de Aceptación de los Entregables

| Entregable / Área                      | Criterio de Aceptación Medible (Pasa / No Pasa)                                                                                                                               | Método de Verificación                                                                        |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Tiempo de Respuesta (EP-03)**        | Despliegue del primer segmento interactivo en pantalla en un tiempo **≤ 2,5 segundos** en redes con ancho de banda ≥ 10 Mbps.                                                 | Telemetría de rendimiento y Core Web Vitals (LCP).                                            |
| **Fluidez de Renderizado (EP-03)**     | Tasa sostenida de **≥ 30 FPS** sin congelamiento de interfaz durante el paneo y zoom continuo.                                                                                | Perfilado de rendimiento en DevTools de navegadores.                                          |
| **Concurrencia (EP-01 a EP-03)**       | Estabilidad operativa sin fallas de conexión ante **100 usuarios concurrentes** visualizando señales simultáneamente.                                                         | Pruebas de estrés y carga automatizadas.                                                      |
| **Tiempo de Ingesta (EP-02)**          | Procesamiento completo (validación, sanitización y persistencia) en un tiempo **≤ 30 segundos** para archivos EDF < 50 MB.                                                    | Pruebas de benchmark en servidor.                                                             |
| **Privacidad de Datos (EP-02)**        | **0% de datos identificatorios personales residuales** en los campos de paciente de la cabecera EDF (`patient_id`, nombre, sexo, fecha nacimiento), cumpliendo la Ley 25.326. | Script de inspección y auditoría binaria automatizada sobre el 100% de los archivos cargados. |
| **Calidad de Software (EJ-04)**        | **Cero (0) defectos críticos o bloqueantes abiertos** al cierre de la fase de QA (sin caídas del servidor, fugas de datos o fallos de renderizado).                           | Reporte de cierre de incidencias en informe final de QA.                                      |
| **Dataset Semilla (EP-06)**            | Disponibilidad en el catálogo productivo de al menos **30 registros EDF** (mínimo 15 ECG y 15 EEG) correctamente catalogados.                                                 | Verificación de inventario en base de datos de producción.                                    |
| **Despliegue y Cierre (EJ-05, EJ-06)** | Sistema operativo en dominio institucional (`*.unvime.edu.ar`) con acta de homologación y cierre firmada a más tardar el **15 de febrero de 2027**.                           | Acta formal firmada por las autoridades institucionales.                                      |
| **Adopción Académica (Impacto)**       | Adopción formal del sistema en al menos **dos (2) programas de cátedra o guías oficiales de trabajos prácticos** de la UNViMe para el primer semestre de 2027.                | Planes de cátedra o guías de estudio aprobadas.                                               |

## 5. Supuestos del Proyecto

1. La Dirección de Informática/TIC de la UNViMe garantizará a tiempo el aprovisionamiento del servidor, las credenciales de administración, el subdominio (`*.unvime.edu.ar`) y un mínimo de 100 GB de almacenamiento persistente.
2. El Grupo de Bioingeniería (GAB) facilitará oportunamente los registros EDF necesarios para conformar el Dataset Semilla con el respaldo ético correspondiente.
3. El diseño de la interfaz gráfica resultará suficientemente intuitivo y autoexplicativo, permitiendo la operación directa de los usuarios sin necesidad de soporte documental o entrenamiento presencial.
4. Los usuarios finales contarán con conexión a Internet y navegadores actualizados compatibles con HTML5 Canvas / WebGL.

## 6. Exclusiones del Proyecto (_Out of Scope_)

1. **Elaboración, entrega o mantenimiento de manuales de usuario, guías de administración o documentación técnica de arquitectura de software.**
2. **Diseño, dictado, impartición o evaluación de cursos de capacitación, talleres, seminarios o sesiones de entrenamiento para usuarios finales o administradores.**
3. **Módulo de anotaciones clínicas (_Scribe_), etiquetado manual o marcado interactivo de eventos fisiológicos sobre la señal.**
4. Conexión directa a hardware, cables o captura de señales en tiempo real desde pacientes o equipos hospitalarios.
5. Desarrollo de modelos de inteligencia artificial, procesamiento asistido o algoritmos para diagnóstico clínico automatizado.

6. Certificación, validación o registro del software como producto médico de diagnóstico ante autoridades regulatorias (como la ANMAT).

7. Desarrollo de clientes de escritorio instalables o aplicaciones móviles nativas para Android o iOS.
8. Procesamiento o conversión de formatos de archivo distintos a la especificación estándar `.edf` y `.edf+`.
9. Migración automatizada o carga de registros históricos desde plataformas externas como LightWAVE.
10. Soporte técnico continuo o mantenimiento correctivo/evolutivo con posterioridad a la firma del Acta de Cierre.

## 7. Restricciones del Proyecto

- **Cronograma Comprometido (Fecha Límite):** La fecha límite inamovible de homologación, despliegue productivo y firma del Acta de Cierre es el **15 de febrero de 2027**, permitiendo la disponibilidad operativa para el ciclo lectivo 2027.
- **Costo de Licenciamiento e Infraestructura:** El despliegue se efectuará exclusivamente sobre la infraestructura provista por la UNViMe (garantizando soberanía total sobre los datos), con un presupuesto asignado para licencias de terceros o software comercial estrictamente de **$0 USD**.
- **Marco Legal y Ético:** Cumplimiento imperativo de la **Ley Nacional N° 25.326** (Protección de los Datos Personales) para garantizar la imposibilidad de reidentificación de pacientes, y exigencia de convenios y avales bioéticos para las señales provenientes de centros hospitalarios.
- **Restricción de Cliente:** El acceso a la plataforma debe operar íntegramente a través de estándares web nativos, sin requerir descargas adicionales, plugins ni extensiones locales por parte de los usuarios finales.
