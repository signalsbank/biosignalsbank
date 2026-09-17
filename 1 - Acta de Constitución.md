# **Acta de Constitución del Proyecto**
**Nombre del Proyecto:** Banco de Señales Biomédicas ("BioSignal")

## 1. _Director del Proyecto y Equipo del Proyecto_

### Director y Asistente del Proyecto
* **Director del Proyecto:** Astudillo, Mateo Tomás
* **Asistente del Director del Proyecto:** Ávila Gelbes, Ignacio Nicolás

### Responsabilidad y Nivel de Autoridad del Director del Proyecto
* **Autoridad:**
  * Asignación y redistribución de tareas dentro del equipo.
  * Punto de contacto formal para escalamiento de riesgos y coordinación con las autoridades de la UNViMe.
* **Responsabilidad:**
  * Garantizar la entrega de todos los módulos del proyecto.
  * Coordinar el seguimiento de hitos
  * Coordinar control de riesgos 
  * A cargo de la elaboración de la documentación del proyecto.

### Equipo del Proyecto
| Nombre | Rol y Responsabilidad |
| :--- | :--- |
| **Astudillo, Mateo** | Director del Proyecto (PM) |
| **Ávila Gelbes, Ignacio Nicolás** | Asistente del Director del Proyecto |
| **Herrera, Germán Ezequiel** | Desarrollador Backend / QA |
| **Mosainer, Martín David** | Desarrollador Full-Stack / Soporte Técnico |
| **Chiecher, Eber Blas** | Desarrollador Backend / Infraestructura |
| **Pereyra, Rocío** | Desarrolladora Frontend |

---

## 2. _Patrocinadores y Autorizadores_
* **Patrocinador Institucional (Sponsor):** Escuela de Ingeniería y Ciencias Ambientales (EICA) - Director de escuela: Alejandro Rosas.

---

## 3. _Necesidades del Cliente_

* **Necesidad del grupo de administradores de Bioingeniería:**
  * **Plataforma de carga centralizada:** Disponer de un repositorio web único para almacenar y organizar señales biomédicas fisiológicas.
  * **Gestión de datos:** Interfaz de administración para cargar datos del registro (frecuencia de muestreo, canales, unidades).
  * **Compatibilidad con EDF (European Data Format):** Verificación automática de formato ".edf" para asegurar que el visor gráfico pueda interpretarlos sin errores.
* **Necesidad del Usuario Final / Consumidor (Estudiantes y Docentes de Medicina y Salud):**
  * **Entorno web:** Acceso directo vía navegador web a señales clínicas reales para ejercitación académica.
  * **Visualización interactiva:** Capacidad de analizar registros gráficos.
  * **Anotación:** Disponer de herramientas para aplicar filtros, medir intervalos y agregar marcadores sobre las ondas.

---

## 4. _Restricciones del Proyecto_

* **Restricciones de Tiempo y Calendario:**
  * El proyecto debe finalizar el **27 de Noviembre de 2026** para adaptarse al cierre del calendario académico lectivo.
* **Restricciones Económicas y de Recursos:**
  * Despliegue bajo esquema de costo directo $0 USD en infraestructura comercial, priorizando el uso de servidores institucionales de la UNViMe o plataformas *cloud* en capas gratuitas (ej. Vercel).
* **Restricciones Técnicas:**
  * Soporte exclusivo para archivos biomédicos estándar .edf (European Data Format). 
  * Funcionamiento en navegadores web modernos sin instalación de plugins, clientes de escritorio ni extensiones.
* **Restricciones Legales:**
  * Anonimización absoluta e irreversible de cualquier dato personal o clínico de pacientes reales en cumplimiento con normativas éticas de salud.

---

## 5. _Propósito del Proyecto_
Desarrollar e implementar una plataforma web centralizada para la carga, gestión, visualización interactiva y análisis académico de señales biomédicas en la Universidad Nacional de Villa Mercedes (UNViMe).

---

## 6. _Objetivos Medibles del Proyecto y Criterios de Éxito_

### Objetivos Medibles (Criterios SMART)
* **Objetivo 1 (Visualizador Web):** Desarrollar e implementar un visor gráfico en el navegador capaz de renderizar al menos 100 muestras en simultaneo con una latencia de carga inicial menor a 10 segundos antes del **23 de Octubre de 2026**.
* **Objetivo 2 (Gestión y Carga):** Permitir la carga y descarga exitosa de al menos 50 archivos EDF de señales biomédicas antes del **10 de Noviembre de 2026**, garantizando un tiempo medio de transferencia inferior a 3 minutos por archivo.
* **Objetivo 3 (Adopción y Satisfacción Académica): Integrar BioSignal como herramienta obligatoria en al menos 2 trabajos prácticos por cátedra en 5 asignaturas de Salud y Medicina para diciembre de 2026.**

### Criterios de Éxito por Parte Interesada (Stakeholder)

| Parte Interesada | Criterio de Éxito Específico |
| :--- | :--- |
| **1. Patrocinador (EICA / Autoridades)** | Despliegue del sistema funcional antes del 27 de Noviembre de 2026 con $0 USD de costo recurrente extra en infraestructura. |
| **2. Colaboradores (Estudiantes de Bioingeniería)** | Disponer de una plataforma centralizada para la carga, validación y descarga de archivos de señales (.edf). |
| **3. Clientes / Usuarios Finales (Escuela de Ciencias de la Salud y Medicina)** | Que al menos 50 estudiantes o docentes puedan buscar, visualizar y realizar anotaciones en las señales en menos de 10 minutos sin requerir soporte técnico ni software adicional. |
| **4. Equipo de Desarrollo del Proyecto (PM y Devs)** | Concluir el alcance planificado dentro del rango de 260 a 360 horas de trabajo. |

---

## 7. _Requisitos de Alto Nivel_ (REVISAR ANTES EL DOCUMENTO DE REQUISITOS)

* **Requisitos Funcionales (RF):**
  * **RF-01 (Autenticación y Roles):** Sistema de control de acceso diferenciando roles (Administrador/Bioingeniería vs. Estudiante/Docente de Salud).
  * **RF-02 (Ingesta y Parseo):** Módulo de carga de archivos biomédicos en formato ".edf" con extracción automática de frecuencia de muestreo y número de canales.
  * **RF-03 (Visualización Interactiva):** Visor gráfico con herramientas de desplazamiento (paneo), zoom temporal, ajuste de amplitud y selección de canales.
  * **RF-04 (Módulo Scribe):** Sistema de marcado de eventos fisiológicos sobre la señal con almacenamiento persistente en la base de datos.
  * **RF-05 (Exportación):** Función para descargar registros de señales en formato estandarizado EDF.
* **Requisitos No Funcionales (RNF):**
  * **RNF-01 (Usabilidad):** Interfaz limpia e intuitiva adaptada a usuarios sin conocimientos de programación.
  * **RNF-02 (Rendimiento):** Renderizado fluido de curvas biomédicas sin congelamiento de pantalla (mínimo 30 FPS durante el desplazamiento continuo de la señal).
  * **RNF-03 (Compatibilidad):** Compatibilidad garantizada en las últimas versiones de Google Chrome, Mozilla Firefox y Microsoft Edge.
  * **RNF-04 (Privacidad):** Garantía estricta de anonimización de datos médicos previo al almacenamiento definitivo.

---

## 8. _Descripción, Límites y Entregables Claves_

### **Descripción**
El proyecto **"BioSignal"** consiste en desarrollar una plataforma web para la carga, gestión y visualización de bancos de señales biomédicas. El sistema permitirá a los Estudiantes de Bioingeniería (EB) cargar señales propias en formato ".edf" para que la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM) las utilicen interactivamente con fines didácticos, superando la limitación del sistema LightWAVE de PhysioNet que no permite la carga personalizada de registros.

### **Límites (Alcance)**
* **Incluye:**
  * Módulo de administración para carga y catálogo de registros.
  * Visualizador interactivo en navegador.
  * Sistema de marcado y anotaciones.
  * Módulo de descarga de archivos en formato EDF.
* **Excluye:**
  * Conexión física o captura en tiempo real desde equipamiento de hardware biomédico.
  * Módulos de diagnóstico automático, algoritmos de detección clínica o toma de decisiones médicas (uso 100% educativo).
  * Sustitución de software de procesamiento médico avanzado certificado para uso hospitalario.

### **Entregables Clave**
1. **Módulo de Autenticación:** para el control de acceso de usuarios.
2. **Modulo de Gestion de Señales**: Alta, baja y modificacion de señales.
3. **Visor Web de Señales:** Interfaz web con controles de paneo, zoom y amplitud.
4. **Módulo de Anotaciones:** Sistema para creación, edición y guardado de anotaciones clínicas sobre la onda.

---

## 9. _Riesgos, Supuestos y Dependencias_

* **Supuestos:**
  * Los usuarios finales disponen de conexión a internet estable y dispositivos con navegadores web modernos.
  * El grupo de administradores de Bioingeniería proveerán archivos de señal biomédica de prueba debidamente anonimizados de manera oportuna.
* **Restricciones:**
  * Desarrollo estrictamente acotado al rango de 260 a 360 horas de esfuerzo dentro del período del 1 de Agosto al 27 de Noviembre de 2026.
* **Dependencias:**
  * Disponibilidad y configuración de la infraestructura de servidor/alojamiento provista por la UNViMe.
* **Riesgos Principales:**
  * **R1 (Retraso en entrega de datos):** Demora en la provisión de archivos EDF reales por parte del grupo de administradores de Bioingenieria para la etapa de pruebas. *Mitigación:* Obtener señales de otras fuentes desde el Hito 1.
  * **R2 (Rendimiento del visualizador):** Latencia o congelamiento del navegador al graficar registros muy extensos. *Mitigación:* Utilizar parseo por bloques (chunking) y renderizado acelerado con HTML5 Canvas/WebGL.
  * **R3 (Disponibilidad del equipo):** Reducción de horas de desarrollo durante períodos de exámenes. *Mitigación:* Planificar un margen de flexibilidad en el cronograma entre los Hitos 2 y 3.

---

## 10. _Cronograma de Hitos_

| Hito | Período | Esfuerzo Est. | Entregable Clave |
| :--- | :--- | :--- | :--- |
| **Hito 1: Arquitectura Base** | 01/Ago - 14/Ago | ~35 hs | Entorno de desarrollo, repositorio inicial y prueba de concepto de lectura de señales vía consola mediante librería WFDB (Wave Form Data Base). |
| **Hito 2: Desarrollo del Motor Backend** | 15/Ago - 11/Sep | ~80 hs | API REST completa para conversión y streaming de muestras biomédicas en formato JSON con metadatos. |
| **Hito 3: Visor Frontend de Señales** | 12/Sep - 23/Oct | ~120 hs | Interfaz web interactiva funcional con renderizado (Canvas/WebGL), controles de zoom, paneo y amplitud. |
| **Hito 4: Módulo Anotaciones** | 24/Oct - 10/Nov | ~35 hs | Módulo de lectura/escritura de marcadores de eventos fisiológicos persistentes en base de datos. |
| **Hito 5: QA, Optimización y Entrega Final** | 11/Nov - 27/Nov | ~40 hs | Pruebas de estrés, corrección de bugs, despliegue en servidor de producción (Release 1.0) y entrega de documentación. |

---

## 11. _Estimación de Costos y Recursos_

### **Presupuesto Financiero y Sostenibilidad**
* **Costo Directo del Proyecto:** $0 USD.
* **Infraestructura:** Esquema $0 costo recurrente mediante utilización de servidores UNViMe / cuentas gratuitas de despliegue cloud (Vercel/Render).
* **Derechos de publicidad:** El equipo de desarrollo se queda con las ganancias generadas por la publicidad del sistema.


---

## 12. _Interesados Clave (Stakeholders)_
1. **Patrocinador Institucional (Sponsor):** Escuela de Ingenierica y Ciencias Ambientales (EICA) - Alejandro Rosas.
2. **Colaboradores de Carga de Datos:** Grupo de administradores de Bioingeniería.
3. **Usuarios Finales / Clientes Académicos:** Estudiantes y Cuerpo Docente de la Escuela de Ciencias de la Salud (ECS) y Escuela de Medicina (EM).
4. **Equipo de Gestión y Desarrollo:** Director del Proyecto (Mateo Astudillo), Asistente de PM (Ignacio Ávila Gelbes) y Desarrolladores (Germán Herrera, Martín Mosainer, Eber Chiecher, Rocío Pereyra).

---

## 13. _Requisitos de Aprobación del Proyecto_

* **Criterios de Aprobación Final:**
  * Funcionamiento correcto y validado de los 4 entregables clave descritos en la Sección 8.
  * Superación exitosa de las pruebas de QA.
* **Autoridad que Otorga la Aprobación:**
  * Director de la Escuela de Ingenieria y Ciencias Ambientales (EICA), Alejandro Rosas, en conjunto con el Director del Proyecto (Mateo Tomás Astudillo).

---

## 14. _Criterios de Salida y Cierre del Proyecto_

* **Cierre Normal / Exitoso:**
  * Despliegue completado de la versión Release 1.0 en el entorno de producción de la universidad antes del 27 de Noviembre de 2026.
  * Firma formal del Acta de Cierre por parte del Patrocinador y el Director del Proyecto.
* **Cierre Anticipado / Cancelación (Criterios de Salida):**
  * Imposibilidad técnica no solucionable para renderizar registros biomédicos en el navegador web respetando los estándares de tiempo y rendimiento.
  * Suspensión institucional del proyecto por parte de la UNViMe.
  * Falta prolongada e insuperable de disponibilidad de datos iniciales o infraestructura de servidores que impida la ejecución del proyecto con un retraso superior al 30% del cronograma total.

---

## 15. _Aprobación del Acta de Constitución_

Con la firma de este documento se autoriza formalmente el inicio del proyecto **BioSignal** y se otorga al Director del Proyecto la autoridad para aplicar los recursos organizacionales asignados a las actividades del mismo.

| Firma del Patrocinador | Rol | Fecha |
| :--- | :--- | :--- |
| **Rosas, Alejandro** | Director de EICA | 1 de Agosto de 2026 |
| **Astudillo, Mateo Tomás** | Director del Proyecto (PM) | 1 de Agosto de 2026 |
