ISO 9.001 (es para cualquier proyecto) y 90.003 (es de software)

## Estructura y Cláusulas Clave (Adaptación al Software)

Al basarse en la ISO 9001:2015, la ISO 90003 sigue la misma **Estructura de Alto Nivel (HLS)** y el ciclo Planificar-Hacer-Verificar-Actuar (PDCA), pero con interpretaciones específicas para el ciclo de vida del desarrollo de software (SDLC):

### 1. Contexto de la Organización

Exige comprender el entorno en el que se desarrolla el software. Esto incluye identificar las expectativas de todas las partes interesadas (clientes finales, usuarios, organismos reguladores, proveedores de servicios en la nube) y determinar cómo los factores externos (por ejemplo, nuevas leyes de privacidad de datos como el GDPR) afectan al Sistema de Gestión de Calidad (SGC).

Distinguimos las partes interesadas y factores externos

### 2. Liderazgo

La alta dirección debe comprometerse visiblemente con la calidad del software, promoviendo una cultura donde la calidad no sea solo "responsabilidad de QA", sino de todo el equipo. Implica asignar los recursos correctos, integrar la calidad en los procesos de negocio y establecer políticas claras sobre seguridad, codificación y pruebas.

Nuestro punto débil, por el momento solo delegamos responsabilidad sin tener clara la cultura de trabajo
No tenemos políticas claras sobre seguridad, codificación ni pruebas (todavía)

### 3. Planificación

Se centra en el enfoque basado en riesgos. En el desarrollo de software, esto significa identificar proactivamente riesgos técnicos (deuda técnica, vulnerabilidades de seguridad, fallos de integración) y riesgos de gestión (retrasos, sobrecostes, rotación de personal), estableciendo planes de mitigación y contingencia antes de escribir la primera línea de código.

Tenemos planes de mitigación y contingencia para riesgos de gestión y riesgos técnicos

### 4. Soporte

- **Infraestructura:** Entornos de desarrollo, servidores de prueba, herramientas de integración/despliegue continuo (CI/CD) y repositorios de código.

Sí especificamos la infraestructura necesaria

- **Competencia:** Garantizar que los desarrolladores, arquitectos y testers tengan las habilidades técnicas requeridas y formación continua.

Sí lo especificamos, salvo la formación continua

- **Información documentada:** Control de especificaciones, manuales de usuario y documentación del código fuente.

Sí tenemos control de especificaciones
No tenemos manuales de usuario
Sí tenemos documentación del código fuente

### 5. Operación

- **Requisitos del producto:** Gestión estricta de las historias de usuario o el Documento de Especificación de Requisitos (SRS).

Sí contamos con el documento de especificación de requisitos

- **Diseño y desarrollo:** Define cómo pasar de los requisitos a la arquitectura de software y al código, incluyendo la selección del modelo de ciclo de vida (metodologías Ágiles como Scrum, o tradicionales como Cascada).

Todavía no especificamos esto

- **Control de la producción:** Abarca la gestión de la configuración (control de versiones en Git, trazabilidad de cambios), la gestión de releases, el despliegue y el mantenimiento del software.

Sí está especificado en "Control de cambios del código"

- **Control de salidas no conformes:** Establece cómo se gestionan, documentan y corrigen los bugs, defectos y vulnerabilidades encontradas durante o después del desarrollo.

Todavía no especificamos esto

### 6. Evaluación del Desempeño

Requiere medir qué tan bien está funcionando el software y el equipo. Incluye revisiones de código, métricas de calidad (cobertura de pruebas, densidad de defectos, tiempo de resolución de bugs), encuestas de satisfacción de los usuarios y la realización de auditorías internas sobre los procesos de desarrollo.

Inluímos pruebas, revisiones de código, métricas de calidad
No incluímos encuestas de satisfacción de usuarios ni realizamos auditorías internas

### 7. Mejora

Obliga a la organización a aprender de sus errores. Si un fallo grave llega a producción (un incidente), no basta con hacer un parche rápido; se debe realizar un análisis de causa raíz para modificar el proceso (ej. agregar un nuevo caso de prueba automatizado) y evitar que vuelva a ocurrir. También fomenta la reducción proactiva de la deuda técnica y la optimización de procesos.

No tenemos un plan de mejora continua de procesos
