Requisitos de Negocio
- La plataforma debe permitir a la UNViMe gestionar su propio catálogo local de señales biomédicas
- Debe concluir antes del inicio de cuatrimestre del 2027 (especificar fecha después)
Requisitos de Interesados 
- Universidad UNViMe
	- Que mejoren el desempeño de los alumnos
	- Promocionar carreras
- GAB (Grupo de Administradores de Bioingeniería)
	- Almacenar las señales que extraen de las máquinas de los hospitales
- Usuarios finales ECS/EM
	- Aprender a leer e interpretar señales biomédicas en la cursada y en sus momentos de estudio
- Equipo de desarrollo
	- Ganar plata (mediante publicidad)
	- Ganar experiencia (perfil profesional)
	- Precedentes académicos (proyecto vinculante con la Universidad)
Requisitos Funcionales
- El sistema debe implementar control de acceso diferenciado por roles: Consultor y Administrador
- El sistema debe permitir la carga de archivos biomédicos en formato ".edf".
- Subir señales
- Eliminar señales
- Editar metadatos / nombre de las señales
- Visualización
- Paneo
- Zoom
- Amplitud / Escala
- Canales
- Exportación / Descarga
Requisitos No Funcionales
- Soporte EDF
- Uso desde cualquier dispositivo (especificar cuales dispositivos, la idea es que sean los celulares y computadores que por lo general tienen los estudiantes, deben ser algo modernos y se debe especificar que tan modernas)
- Rendimiento: al menos 100 visualizaciones de una señal desde dispositivos distintos en simultáneo con una latencia menor a 10 segundos
- Compatibilidad: web en navegadores posteriores a 2022 (esto es arbitrario, se puede cambiar por algo que tenga más sentido)
Requisitos de Transición y Preparación Operativa
- Obtener un conjunto de señales biomédicas (especificar número)
- Se debe desplegar la plataforma en el servidor de producción
Requisitos de Proyecto
- Acceso al servidor
- Completar antes del inicio de cuatrimestre del 2027
- Sin datos personales (el sistema debe garantizar la privacidad de los pacientes de quienes se obtuvieron las señales)
Requisitos de Calidad
- Que cumplan las pruebas de calidad (ver)
- Portabilidad: web desde 2022 (arbitrario)
- Eficiencia operativa: el tiempo medio de carga por archivo para los colaboradores debe ser inferior a 3 minutos. (arbitrario)