# Enunciado del Alcance del Proyecto

## 1. Descripción del Proyecto

El proyecto **"BioSignal"** consiste en el diseño, desarrollo, verificación y despliegue productivo de una plataforma web centralizada para la ingesta, gestión, gobernanza y visualización gráfica interactiva de registros de bioseñales biomédicas (ECG, EEG, EMG). Su objetivo es dotar a la Universidad Nacional de Villa Mercedes (UNViMe) de un repositorio y visualizador institucional soberano que almacene los datos en infraestructura propia, eliminando la dependencia de licencias o herramientas externas rígidas (como LightWAVE), y consolidándose como un recurso didáctico y de divulgación para la carrera de Bioingeniería, la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM).

## 2. Alcance

### 2.1. Alcance del Producto

#### Características del Producto (Propiedades Funcionales)

1. **Control de Acceso Basado en Roles (RBAC):** Autenticación y gestión de permisos con dos perfiles: _Administrador_ (gestión integral de usuarios, carga masiva, curaduría de metadatos, baja lógica y auditoría) y _Consultor_ (exploración del catálogo, visualización interactiva multicanal, configuración de escalas y descarga de señales).
2. **Cierre de Sesión por Inactividad:** Expiración automática y revocación de sesión tras 30 minutos continuos sin interacción en cuentas con perfil de Administrador.
3. **Acceso Público Demostrativo y Difusión Institucional:** Sección pública (sin requerimiento de credenciales) con un visualizador interactivo precargado con una señal de muestra y banners informativos enlazados al portal oficial de admisiones de la UNViMe.
4. **Ingesta y Validación Estructural Binaria:** Motor de recepción exclusivo para archivos `.edf` y `.edf+` con verificación automatizada de la cabecera binaria (cantidad de canales, duración del registro y especificaciones técnicas de transductores) antes de confirmar la persistencia.
5. **Sanitización y Anonimización Binaria Obligatoria:** Proceso automatizado e irreversible en servidor que sobrescribe o purga los campos de cabecera que contengan datos de identificación personal del paciente (nombre, ID, documento, fecha exacta de nacimiento e institución de procedencia), garantizando el cumplimiento de la Ley 25.326.
6. **Gestión de Metadatos Académicos:** Ficha técnica estructurada e indexable para cada estudio: tipología de señal (ECG, EEG, EMG), patología de referencia, grupo etario del paciente, equipamiento empleado y notas clínicas de orientación pedagógica.
7. **Visualización Gráfica Interactiva Multicanal:** Interfaz de renderizado de señales con despliegue paralelo de canales en una base temporal unificada, paneo horizontal fluido, zoom temporal (X) y de amplitud (Y) global o individual, y configuración de escalas clínicas estandarizadas (ej. 25 mm/s y 10 mm/mV).
8. **Selector y Organización de Canales:** Controles interactivos para encender, apagar y reorganizar visualmente las derivaciones en pantalla.
9. **Exportación y Descarga:** Mecanismo para la descarga directa del archivo `.edf` debidamente anonimizado y validado.
10. **Dataset Semilla:** Repositorio poblado y disponible en producción con al menos 30 registros EDF iniciales clasificados (15 ECG y 15 EEG multicanal).

#### Requerimientos del Producto (Condiciones Técnicas y Normativas)

- **Formato Único:** Procesamiento exclusivo de especificaciones `.edf` y `.edf+`, operando nativamente en el navegador sin extensiones ni plugins locales.

- **Seguridad y Privacidad:** Cumplimiento irrestricto de la Ley Nacional N° 25.326 de Protección de los Datos Personales (imposibilidad técnica y legal de reidentificación) y cifrado de extremo a extremo en tránsito bajo HTTPS con protocolo TLS 1.3.

- **Desempeño y Rendimiento:**
- Capacidad de soporte de hasta 100 usuarios concurrentes visualizando señales de manera simultánea sin degradación del servicio.
- Tiempo de respuesta inicial (renderizado del primer segmento) inferior o igual a 2,5 segundos en conexiones con ancho de banda ≥ 10 Mbps (arquitectura de carga por fragmentos / _chunking_).
- Tasa de refresco gráfica sostenida de al menos 30 FPS durante acciones interactivas de paneo y zoom.

- Tiempo de procesamiento de ingesta (validación, sanitización y persistencia) menor a 30 segundos para archivos inferiores a 50 MB.

- **Compatibilidad y Portabilidad:** Compatibilidad total comprobada en las dos (2) últimas versiones estables de navegadores basados en Chromium (Chrome, Edge), Gecko (Firefox) y WebKit (Safari).

- **Diseño Adaptativo (_Responsive_):** Modo de visualización completo de hasta 32 canales en pantallas de escritorio/portátiles (≥ 1024 px) y modo simplificado restringido por defecto a 1 o 2 canales en dispositivos móviles (< 768 px).
- **Usabilidad:** Curva de aprendizaje reducida, permitiendo a un usuario nuevo buscar, abrir y calibrar una señal en menos de 5 minutos.

### 2.2. Alcance del Proyecto

Comprende el trabajo de gestión, ingeniería, control de calidad y despliegue necesario para completar el ciclo de vida del software, articulado a través de los hitos formales del proyecto:

```
[Hito 1: Acta de Constitución Aprobada]
   ↓
[Hito 2: Documento de Requisitos Aprobado]
   ↓
[Hito 3: Módulo de Autenticación Listo]
   ↓
[Hito 4: Módulo de Gestión de Señales Listo]
   ↓
[Hito 5: Visualizador de Señales Listo]
   ↓
[Hito 6: Despliegue en Producción]
   ↓
[Hito 7: Acta de Cierre Aprobada (≤ 15/Feb/2027)]

```

#### Fases de Ejecución del Proyecto

- **Fase 1: Iniciación y Planificación de Requisitos:** Formalización del proyecto, definición de la línea base del alcance, elaboración y validación de la especificación técnica de requisitos y diseño de la matriz de trazabilidad.
- _Hito 1: Aprobación del Acta de Constitución._
- _Hito 2: Documento de Requisitos Aprobado._

- **Fase 2: Seguridad y Control de Acceso:** Desarrollo de la capa de autenticación, gestión de tokens, expiración por inactividad a los 30 minutos y estructura de permisos según perfiles RBAC.
- _Hito 3: Módulo de Autenticación Listo._

- **Fase 3: Motor de Ingesta, Anonimización y Datos:** Implementación del parser EDF binario, validación de cabeceras, módulo de sanitización irreversible según Ley 25.326, endpoints de baja lógica auditada y base de datos para catálogo de metadatos clínicos.
- _Hito 4: Módulo de Gestión de Señales Listo._

- **Fase 4: Desarrollo del Frontend y Visualizador Gráfico:** Construcción de la interfaz web, canvas de renderizado por _chunking_, navegación interactiva (paneo y zoom), calibración de escalas normalizadas (25 mm/s, 10 mm/mV), selector de canales y módulo público demostrativo con enlaces de difusión UNViMe.
- _Hito 5: Visualizador de Señales Listo._

- **Fase 5: Aseguramiento de Calidad (QA), Migración y Puesta en Producción:** Ejecución del plan de pruebas (carga concurrente para 100 usuarios, verificación de umbral de 2,5 s, fluidez a 30 FPS, auditoría de privacidad y pruebas cruzadas de navegadores), carga y validación del Dataset Semilla (≥ 30 registros), y configuración de infraestructura en servidores universitarios bajo subdominio institucional.

- _Hito 6: Despliegue._

- **Fase 6: Cierre del Proyecto, Homologación y Transferencia Operativa:** Validación final de criterios de aceptación con los interesados, entrega de manuales y código fuente, tramitación de convenios éticos y formalización del acta de homologación previa al inicio del ciclo lectivo 2027.
- _Hito 7: Aprobación del Acta de Cierre (a más tardar el 15 de febrero de 2027)._

## 3. Entregables del Proyecto y del Producto

### 3.1. Entregables del Producto (Software)

- **EP-01: Sistema de Autenticación y Control de Acceso (RBAC):** Servicio operativo con roles de Administrador y Consultor, y revocación de sesión a los 30 minutos de inactividad.
- **EP-02: Módulo de Ingesta, Validación y Anonimización:** Servicio backend con parser de cabeceras EDF/EDF+, sanitización de datos sensibles y confirmación de baja lógica con trazabilidad.
- **EP-03: Visualizador Web Interactivo:** Módulo frontend con renderizado continuo a ≥ 30 FPS, desplazamiento temporal, zoom bidireccional, ajuste de escalas clínicas (25 mm/s, 10 mm/mV) y filtrado de derivaciones.

- **EP-04: Módulo de Acceso Público y Promoción Académica:** Portal público que contiene el visor con señal demo interactiva y banner de vinculación al área de admisiones de la UNViMe.
- **EP-05: Módulo de Descarga y Exportación:** Función de exportación de registros EDF limpios.
- **EP-06: Dataset Semilla Desplegado:** Base de datos productiva poblada y catalogada con al menos 30 estudios EDF (15 ECG y 15 EEG).

### 3.2. Entregables del Proyecto (Gestión, Documentación y Calidad)

- **EJ-01: Acta de Constitución del Proyecto firmada.**
- **EJ-02: Especificación y Matriz de Trazabilidad de Requisitos aprobada.**
- **EJ-03: Repositorio de Código Fuente:** Repositorios Git consolidados (frontend, backend y scripts de base de datos) con su respectiva documentación de despliegue.
- **EJ-04: Documentación Técnica y de Arquitectura:** Diagramas de componentes, documentación de la API REST y esquemas de persistencia.
- **EJ-05: Manuales de Operación:** Manual de usuario para estudiantes/docentes (perfil Consultor) y manual de administración para el GAB/docentes designados.
- **EJ-06: Reporte Consolidado de Pruebas de QA:** Informes de pruebas de estrés (100 usuarios concurrentes), telemetría de carga inicial (≤ 2,5 s), pruebas _cross-browser_ y auditoría forense de cabeceras binarias (Ley 25.326).

- **EJ-07: Acta de Despliegue en Servidores de la UNViMe:** Certificación técnica de operatividad en infraestructura universitaria.
- **EJ-08: Acta de Homologación y Cierre del Proyecto firmada.**

## 4. Criterios de Aceptación de los Entregables

| Entregable / Área                      | Criterio de Aceptación Medible (Pasa / No Pasa)                                                                                                                                                 | Método de Verificación                                                                        |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **Tiempo de Respuesta (EP-03)**        | Despliegue del primer segmento interactivo de la señal en pantalla en un tiempo **≤ 2,5 segundos** en redes con ancho de banda ≥ 10 Mbps.                                                       | Telemetría de rendimiento y Core Web Vitals (LCP).                                            |
| **Fluidez de Renderizado (EP-03)**     | Mantenimiento de una tasa mínima de refresco de **30 FPS** sin congelamiento de UI durante el paneo horizontal continuo y zoom.                                                                 | Perfilado de rendimiento gráfico en DevTools de navegador.                                    |
| **Concurrencia (EP-01 a EP-03)**       | Estabilidad operativa sin degradación de servicio bajo una carga sostenida de **100 usuarios simultáneos** visualizando bioseñales.                                                             | Pruebas de carga y estrés con herramientas automatizadas.                                     |
| **Tiempo de Ingesta (EP-02)**          | Procesamiento íntegro (validación binaria, sanitización irreversible y persistencia) en un tiempo **≤ 30 segundos** para archivos EDF < 50 MB.                                                  | Pruebas de benchmark en servidor de pruebas.                                                  |
| **Privacidad y Legalidad (EP-02)**     | **0% de datos identificatorios personales residuales** en los campos de paciente de la cabecera EDF (`patient_id`, nombre, sexo, fecha nacimiento), garantizando cumplimiento de la Ley 25.326. | Script de inspección y auditoría binaria automatizada sobre el 100% de los archivos cargados. |
| **Calidad de Software (EJ-06)**        | **Cero (0) fallas críticas o bloqueantes abiertas** al momento de la auditoría final de QA (caídas del sistema, pérdidas de datos o fallos de renderizado).                                     | Matriz de reporte de defectos en informe final de QA.                                         |
| **Dataset Semilla (EP-06)**            | Disponibilidad en producción de al menos **30 registros EDF** (mínimo 15 ECG y 15 EEG multicanal) categorizados y accesibles para los usuarios.                                                 | Verificación y conteo en base de datos productiva.                                            |
| **Despliegue y Cierre (EJ-07, EJ-08)** | Plataforma operativa bajo dominio institucional (`*.unvime.edu.ar`) con acta de homologación y cierre firmada a más tardar el **15 de febrero de 2027**.                                        | Acta formal de entrega firmada por autoridades de la UNViMe.                                  |
| **Adopción Académica (Impacto)**       | Adopción documentada del sistema en al menos **dos (2) programas de cátedra o guías oficiales de trabajos prácticos** de la UNViMe durante el primer semestre de 2027.                          | Programas analíticos o guías de cátedra aprobadas.                                            |

## 5. Supuestos del Proyecto

1. La Dirección de Informática/TIC de la UNViMe proveerá de manera oportuna las credenciales de administración, configuración del subdominio institucional (`*.unvime.edu.ar`) y un espacio mínimo de 100 GB de almacenamiento persistente en sus servidores.
2. El Grupo de Bioingeniería (GAB) y las instituciones sanitarias asociadas facilitarán los archivos EDF requeridos para el Dataset Semilla bajo los debidos consentimientos institucionales.
3. Los usuarios finales (docentes y estudiantes) accederán al sistema a través de computadoras personales o institucionales con conexión a Internet estable y navegadores compatibles con HTML5 Canvas / WebGL.
4. El equipo del proyecto mantendrá la disponibilidad horaria necesaria para coordinar las etapas de pruebas, homologación y despliegue dentro del cronograma previsto.

## 6. Exclusiones del Proyecto (_Out of Scope_)

1. **Módulo de anotaciones clínicas (_Scribe_), etiquetado manual o inserción de marcas de eventos fisiológicos sobre la señal.**
2. Captura de señales en tiempo real o conexión de hardware físico a pacientes o equipamiento electromédico hospitalario.
3. Algoritmos de inteligencia artificial, procesamiento predictivo o diagnóstico automatizado de patologías (el uso es estrictamente pedagógico y académico).

4. Certificación, habilitación o validación regulatoria del software ante organismos de control médico (ej. ANMAT) como producto médico para uso clínico/diagnóstico formal.

5. Desarrollo de clientes de escritorio instalables o aplicaciones móviles nativas para Android/iOS (la solución es 100% web).
6. Procesamiento, ingesta o conversión de formatos de archivo distintos a la norma estándar `.edf` y `.edf+`.
7. Migración automatizada o importación masiva de bases de datos desde LightWAVE u otras plataformas externas.
8. Mantenimiento correctivo, evolutivo o soporte técnico indefinido con posterioridad a la firma del acta de homologación y cierre.

## 7. Restricciones del Proyecto

- **Cronograma Comprometido (Fecha Límite):** La fecha límite inamovible de entrega con pruebas de integración superadas, despliegue productivo y firma del Acta de Cierre es el **15 de febrero de 2027**, para garantizar su incorporación efectiva en el ciclo lectivo 2027.
- **Infraestructura y Costo de Licenciamiento:** El software debe desplegarse en infraestructura provista y controlada administrativamente por la UNViMe (100% soberanía de datos), con un costo recurrente en licencias comerciales de terceros estrictamente igual a **$0 USD**.
- **Marco Legal de Datos:** Obligación de cumplimiento de la **Ley Nacional N° 25.326** de Protección de los Datos Personales (República Argentina), imposibilitando la reidentificación de los pacientes.
- **Marco Ético y Convenios:** Toda bioseñal proveniente de instituciones hospitalarias debe contar con el respaldo de convenios interinstitucionales formales y la autorización de los comités de ética correspondientes.
- **Restricción de Cliente:** La visualización debe funcionar de manera nativa sin exigir a los usuarios finales la instalación de software adicional, plugins o extensiones en sus navegadores.
