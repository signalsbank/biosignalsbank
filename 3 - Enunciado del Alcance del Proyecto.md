# **Enunciado del Alcance del Proyecto**

## **Descripción**

El proyecto **"BioSignal"** consiste en el diseño, desarrollo e implementación de una plataforma web centralizada para la carga, gestión, visualización interactiva y análisis académico de señales biomédicas fisiológicas. Su propósito es dotar a la Universidad Nacional de Villa Mercedes (UNViMe) de un repositorio propio que elimine la dependencia de sistemas externos rígidos (como LightWAVE), sirviendo como herramienta puente entre el desarrollo técnico de la Carrera de Bioingeniería y la práctica docente de la Escuela de Ciencias de la Salud (ECS) y la Escuela de Medicina (EM).

## Proyecto:

### Alcance

El alcance del proyecto abarca el ciclo completo de desarrollo de software desde el diseño de la arquitectura hasta el despliegue en producción.

#### _Incluye:_

- Gestión del proyecto técnico bajo un esfuerzo estimado de 260 a 360 horas de trabajo, dentro del período 1 de Agosto – 27 de Noviembre de 2026.
- Diseño e implementación de la arquitectura web utilizando herramientas gratuitas o institucionales ($0 costo recurrente directo).
- Cierre formal del proyecto, incluyendo la firma del Acta de Cierre.
  En síntesis: el alcance del proyecto comprende _todo el trabajo necesario_ —y únicamente ese trabajo— para entregar exitosamente el producto BioSignal con las características especificadas, dentro del tiempo, costo y calidad definidos.

#### _No incluye:_

- Mantenimiento correctivo o evolutivo del sistema _una vez finalizado y entregado_ el Release 1.0 (queda fuera del período del proyecto, aunque puede derivar en un proyecto/fase posterior).
- Soporte técnico indefinido a usuarios finales más allá del cierre del proyecto.
- Adquisición de hardware, licencias comerciales o servicios pagos de terceros (coherente con la restricción de $0 USD).
- Migración automática o importación masiva de datos históricos desde LightWAVE u otros sistemas externos.
- Actividades de difusión institucional o marketing de la plataforma fuera del ámbito académico de la UNViMe
- Código Fuente:** Repositorio completo del sistema (Frontend y Backend).
- Documentación Técnica de Arquitectura:** Detalles de los componentes, diagramas, API y dependencias para garantizar la mantenibilidad del sistema.
- Manuales de Usuario:** Material de apoyo para usuarios administradores y usuarios finales (estudiantes/docentes).

## Entregables — Documentación y Cierre (PREGUNTAR)

- **Reportes de QA:** Evidencias de pruebas de estrés, rendimiento cruzado en navegadores y auditoría de privacidad.

### Criterios de Aceptación asociados

- **Costo:** Evidencia comprobable de que el despliegue del Release 1.0 se realizó utilizando herramientas institucionales o capas gratuitas, incurriendo en $0 USD en infraestructura comercial.

## Supuestos

- Las Escuelas de Ciencias de la Salud y Medicina proveerán archivos de señal biomédica de prueba (reales y debidamente anonimizados) de forma oportuna para la fase de pruebas (antes del Hito 2/3).
- La UNViMe garantizará la disponibilidad y configuración de la infraestructura de servidor o proveerá los permisos necesarios institucionales para los despliegues planificados.
- La disponibilidad horaria del equipo de desarrollo, aunque condicionada a periodos de exámenes, permitirá mantener el rango estimado de 260 a 360 horas hombre de esfuerzo.

## Exclusiones

- Sustitución, homologación o certificación del software para reemplazar sistemas de uso hospitalario clínico oficial.

## Restricciones

- **Tiempo:** Fecha límite inflexible fijada para el 27 de noviembre de 2026 para sincronizarse con el cierre del calendario lectivo.
- **Costo:** El presupuesto asignado para infraestructura de terceros es estrictamente $0 USD.
- **Esfuerzo:** El rango de horas invertidas por el equipo de desarrollo no podrá exceder el tope de 360 horas.

## Producto:

### Alcance

El alcance del producto comprende las funcionalidades y características del sistema final "BioSignal":

#### Incluye:

- _Gestión de acceso y roles:_ Sistema de autenticación con perfiles diferenciados (Consultor y Administrador).
- _Procesamiento de datos:_ Motor capaz de analizar, extraer datos y convertir archivos estándar .edf para su transmisión.
- _Visualización en navegador:_ Visor interactivo que permite el paneo continuo, zoom temporal, ajuste de amplitud y selección de canales.
- _Exportación:_ Capacidad de descargar señales procesadas en formato estándar EDF.
- _Catálogo Base:_ Al menos 50 conjuntos de señales biomédicas de prueba, cargados y categorizados (buscar datos de prueba de otras fuentes).
- _Pruebas de calidad:_ Ejecución de pruebas de calidad (QA) exhaustivas en entornos controlados y navegadores web modernos.
- _Despliegue:_ Despliegue del sistema en un servidor proporcionado por la UNViMe o plataformas cloud en su capa gratuita (ej. Vercel/Render).

#### No incluye:

- Conexión física, integración de hardware o captura de señales biomédicas en tiempo real desde equipos médicos hospitalarios.
- Módulos de diagnóstico automático, algoritmos de detección de patologías mediante Inteligencia Artificial, o sistemas orientados a la toma de decisiones médicas (el uso del producto es estrictamente educativo/académico).
- _Certificación, homologación o habilitación regulatoria_ para operar como software de uso hospitalario/clínico oficial — ver aclaración en la Sección 13.
- Aplicaciones móviles nativas o clientes de escritorio instalables (el producto se consume 100% mediante navegador web).
- Soporte para formatos de archivo distintos a .edf.

## Entregables — Software

- **Módulo de Autenticación:** para el control de acceso de usuarios.
- **Modulo de Gestion de Señales**: Alta, baja y modificacion de señales.
- **Visor Web de Señales:** Interfaz web con controles de paneo, zoom y amplitud.
- **Módulo de Anotaciones:** Sistema para creación, edición y guardado de anotaciones clínicas sobre la onda.

### Criterios de Aceptación asociados

- **Visualizador Web:** Desarrollar e implementar un visor gráfico en el navegador capaz de renderizar al menos 100 muestras en simultaneo con una latencia de carga inicial menor a 10 segundos antes del **23 de Octubre de 2026**.
- **Gestión y Carga:** Permitir la carga y descarga exitosa de al menos 50 archivos EDF de señales biomédicas antes del **10 de Noviembre de 2026**, garantizando un tiempo medio de transferencia inferior a 3 minutos por archivo.
- **Adopción y Satisfacción Académica: Integrar BioSignal como herramienta obligatoria en al menos 2 trabajos prácticos por cátedra en 5 asignaturas de Salud y Medicina para diciembre de 2026.**

## Supuestos

- Los usuarios finales dispondrán de una conexión a internet estable y utilizarán equipos con navegadores web modernos y actualizados.

## Exclusiones

- Conexión física, integración de hardware o captura de señales biomédicas en tiempo real desde equipos médicos hospitalarios.
- Desarrollo de módulos de diagnóstico automático, algoritmos de detección de patologías mediante Inteligencia Artificial, o sistemas orientados a la toma de decisiones médicas (el uso es estrictamente educativo/académico).
- Desarrollo de aplicaciones móviles nativas o clientes de escritorio instalables (el uso es 100% mediante navegador web).

## Restricciones

- **Técnicas:** El formato de entrada soportado es exclusivamente .edf (European Data Format). El sistema no admitirá plugins o extensiones adicionales en el navegador.
- **Legales/Éticas:** Cumplimiento obligatorio de las normativas de salud referidas a la anonimización absoluta de cualquier dato vinculable a pacientes reales, imposibilitando el alojamiento de metadatos sensibles.
