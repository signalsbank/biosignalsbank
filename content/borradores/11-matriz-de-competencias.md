# Documento N° 10 — Gestión de Adquisiciones, Compras, Competencias y Plan de Mejoras

**Nombre del Proyecto:** Banco de Señales Biomédicas ("BioSignal")  
**Universidad:** Universidad Nacional de Villa Mercedes (UNViMe)  
**Materia:** Ingeniería de Software II  
**Profesor:** Walter Lucero  
**Director del Proyecto:** Astudillo, Mateo Tomás  
**Asistente del Director:** Ávila Gelbes, Ignacio Nicolás  
**Equipo de Desarrollo:** Herrera, Germán Ezequiel | Mosainer, Martín David | Chiecher, Eber Blas | Pereyra, Rocío

---

## 1. Lista de Insumos y Productos a Comprar (Análisis de Hacer o Comprar)

### 1.1. Contexto Metodológico y Restricción Financiera

Conforme al estándar **PMBOK 7** (dominio de desempeño de **Trabajo del Proyecto**, prácticas de adquisiciones), el equipo del proyecto aplica el **Análisis de Hacer o Comprar (_Make-or-Buy Analysis_)**; las técnicas de proceso de PMBOK 6 se usan solo como fuente de método, y las decisiones de adaptación quedan registradas en el registro de tailoring.

Aunque el proyecto **BioSignal** opera bajo una restricción formal de **$0 USD de costo directo recurrente** en infraestructura comercial por sustentarse en los servidores institucionales de la **Universidad Nacional de Villa Mercedes (UNViMe)**, el marco académico dictado por el profesor Walter Lucero exige identificar y listar exhaustivamente todos los insumos, licencias, servicios profesionales, equipamiento y conjuntos de datos requeridos para la ejecución, aseguramiento de la calidad y contingencia del sistema.

### 1.2. Matriz Consolidada de Insumos y Productos

A continuación se presenta la nómina detallada de adquisiciones necesarias para el ciclo de vida del proyecto BioSignal, vinculando cada ítem con las especificaciones técnicas abiertas (sin marcas impuestas en la solicitud inicial) y su trazabilidad directa con la **Estructura de Desglose del Trabajo (EDT/WBS)** y los **Requisitos del Proyecto**:

|    Ítem    | Nombre del Insumo / Producto                                   | Categoría               | Especificaciones Técnicas y Criterios de Calidad Requeridos                                                                       |                     Paquete de Trabajo EDT / Req. Asociado                     | Justificación Técnica en BioSignal                                                                                      |
| :--------: | :------------------------------------------------------------- | :---------------------- | :-------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------- |
| **INS-01** | **Servidor VPS / Cloud de Reserva (Failover)**                 | Hardware / Hosting      | Instancia virtual de cómputo Linux (4 vCPUs, 8 GB RAM, 100 GB SSD NVMe, red ≥ 10 Mbps, soporte Docker, uptime 99.9%).             |    `1.2.1 Servidores y base de datos configurados`<br>([RNF-01], [RNF-02])     | Garantizar la alta disponibilidad y contingencia ante mantenimientos o caídas de la infraestructura local de la UNViMe. |
| **INS-02** | **Registro de Nombre de Dominio Web Dedicado**                 | Dominio / Red           | Dominio TLD de segundo/tercer nivel (.org / .com.ar) con soporte DNS dinámico, registros CNAME/A y privacidad WHOIS.              |   `1.5 Sistema desplegado en ambiente de producción`<br>([RT-02], [RNF-06])    | Asegurar acceso web público de respaldo si se demorase la delegación del subdominio `*.unvime.edu.ar`.                  |
| **INS-03** | **Licencia de Plataforma de Pruebas de Carga y Estrés (SaaS)** | Software / QA           | Plan SaaS para simulación de concurrencia masiva (≥ 100 VUs - Virtual Users simultáneos) con métricas de latencia LCP y tasa FPS. | `1.4.2 Reporte de pruebas de integración y aceptación`<br>([RNF-01], [RNF-02]) | Certificar objetivamente la capacidad operativa de 100 usuarios simultáneos y LCP ≤ 2,5 s sin degradación.              |
| **INS-04** | **Suscripción de Integración Continua (CI/CD)**                | Software / DevOps       | Plan de organización en plataforma Git con runners dedicados y minutos extendidos para automatización de builds y tests.          |             `1.2.2 Entornos de desarrollo y pruebas`<br>([EJ-03])              | Automatizar la ejecución de pruebas unitarias, análisis estático y despliegue continuo en cada entrega de código.       |
| **INS-05** | **Servicio de Auditoría de Seguridad y Anonimización**         | Servicios Profesionales | Servicio de Pentesting web y auditoría forense binaria sobre cabeceras .edf/.edf+ con dictamen normativo Ley 25.326.              |       `1.3.2.1 Formulario y procesador de carga`<br>([RF-06], [RNF-05])        | Auditar la eliminación 100% irreversible de datos personales de pacientes en cumplimiento legal estricto.               |
| **INS-06** | **Servicio de Diseñador UI/UX y Accesibilidad Web**            | Servicios Profesionales | Maquetado de interfaz responsiva (escritorio y mobile), kit de componentes visuales de bioseñales y pautas WCAG 2.1.              |     `1.3.3.2 Renderizador interactivo de señales`<br>([RNF-08], [RNF-09])      | Garantizar un visor multicanal intuitivo (operación en < 5 min) optimizado para pantallas táctiles.                     |
| **INS-07** | **Dataset Semilla de Bioseñales (.EDF) Curado**                | Insumos de Datos        | Banco de 30 registros biomédicos anonimizados (15 ECG y 15 EEG) con metadatos clínicos y patologías clasificadas.                 |   `1.2.3 Aprovisionamiento y carga de dataset semilla`<br>([RT-01], [EP-06])   | Poblar el repositorio productivo para uso inmediato en las cátedras de Medicina y Salud en el primer semestre de 2027.  |
| **INS-08** | **Bolsa de Créditos/Tokens de API de Procesamiento e IA**      | Software / AI           | Créditos/tokens para servicio de IA/LLM enfocado en extracción automática de metadatos clínicos e indexación de patologías.       |            `1.3.2.2 Interfaz de edición de metadatos`<br>([RF-07])             | Asistir al administrador en la sugerencia y etiquetado automático de patologías durante la ingesta.                     |

### 1.3. Fichas de Solicitud de Compra para Insumos Clave

Para dar cumplimiento a la buena práctica expresada por el profesor Walter Lucero de **especificar niveles de calidad y requisitos técnicos sin amarrar marcas comerciales fijas**, se detallan las fichas técnicas formales de los insumos principales:

#### Ficha de Solicitud INS-01: Servidor VPS de Contingencia (Failover)

- **Categoría:** Hosting / Infraestructura Cloud.
- **Especificación Técnica:** Servidor virtual con sistema operativo Linux (Ubuntu Server 24.04 LTS), 4 vCPUs, 8 GB RAM, 100 GB de almacenamiento SSD NVMe, tasa de transferencia mensual de al menos 1 TB, soporte nativo para Docker/Docker-Compose, dirección IP pública dedicada y protocolo TLS 1.3 preconfigurado.
- **Cantidad:** 1 Instancia (contratación por 6 meses).
- **Criterio de Aceptación:** Uptime comprobado ≥ 99.9% e instalación exitosa del contenedor Docker de BioSignal en menos de 15 minutos.
- **Justificación EDT:** Paquete `1.2.1 Servidores`.

#### Ficha de Solicitud INS-03: Licencia SaaS para Pruebas de Carga y Concurrencia

- **Categoría:** Software de QA / Monitoreo.
- **Especificación Técnica:** Plataforma en la nube capaz de ejecutar scripts de pruebas de estrés mediante simulación distribuida de 100 usuarios virtuales concurrentes navegando el visualizador gráfico Canvas/WebGL, midiendo métricas de LCP (Largest Contentful Paint), TTFB y tasa de refresco en FPS.
- **Cantidad:** 1 Licencia corporativa (período de pruebas de 3 meses).
- **Criterio de Aceptación:** Generación automática de informe telemétrico auditable en PDF.
- **Justificación EDT:** Paquete `1.4.2 Reporte de pruebas de integración`.

---

## 2. Procedimiento y Circuito Operativo del Proceso de Compras (Efectuar las Adquisiciones)

### 2.1. Circuito Flujo de Compras Paso a Paso

El proceso de adquisición en el proyecto **BioSignal** se rige por un procedimiento administrativo y técnico estructurado en 7 etapas secuenciales, garantizando transparencia, trazabilidad y libre concurrencia de proveedores:

```
 [1. Solicitud de Compra (SOW / TOR)]
               │
               ▼
 [2. Emisión de Pliegos de Licitación (RFP / RFQ)]
   (Con plazo estricto de cotización: 3-5 días)
               │
               ▼
 [3. Difusión a Registro/Padrón de Proveedores]
               │
               ▼
 [4. Recepción, Apertura y Evaluación de Ofertas]
   (Matriz de Ponderación Criterios Técnicos y Económicos)
               │
               ▼
 [5. Adjudicación y Notificación] ──► [Feedback a Oferentes No Seleccionados]
               │
               ▼
 [6. Orden de Compra (OC) y Entrega del Insumo/Servicio]
               │
               ▼
 [7. Inspección Técnica por QA y Recepción Conformada]
```

### 2.2. Detalle Operativo de las Etapas del Circuito

1. **Identificación de Necesidades y Solicitud de Compra (Requisitoria Interna):**
   El responsable de un paquete de la EDT (ej. Backend, Frontend, QA) completa el formulario interno de Solicitud de Compra adjuntando el **Enunciado del Trabajo Relativo a las Adquisiciones (SOW — _Statement of Work_)** o Términos de Referencia (TOR), detallando las especificaciones de calidad requeridas sin indicar marcas exclusivas.
2. **Elaboración y Emisión de Documentos de Licitación (RFP / RFQ):**
   Se redactan los pliegos de bases y condiciones: **Solicitud de Cotización (RFQ — _Request for Quotation_)** para productos estandarizados (dominios, VPS) o **Solicitud de Propuesta (RFP — _Request for Proposal_)** para servicios complejos (auditoría Ley 25.326, UI/UX). Como requisito de dinamismo procesal, se fija un **plazo estricto de presentación de ofertas de 3 a 5 días hábiles**.
3. **Convocatoria al Registro de Proveedores:**
   El pedido se notifica a las empresas inscriptas en el **Registro/Padrón de Proveedores** de la organización según el rubro correspondiente (Hardware, Software, Consultoría).
4. **Recepción, Apertura y Evaluación Ponderada de Ofertas:**
   Cumplido el plazo, se realiza la apertura formal de propuestas. El equipo evaluador encabezado por el PM (Mateo Astudillo) aplica una **Matriz de Selección Multi-criterio** considerando:
   - _Capacidad Técnica y Adherencia al SOW:_ 40%
   - _Propuesta Económica / Precio:_ 30%
   - _Tiempo de Entrega / Despliegue:_ 20%
   - _Soporte Técnico y Garantía:_ 10%
5. **Adjudicación, Firma de Contrato y Retroalimentación (_Feedback_):**
   Se emite el Dictamen de Adjudicación al proveedor ganador. Como pilar de mejora continua remarcado en la materia, se envía una **notificación formal con feedback técnico a los proveedores no seleccionados**, indicando los motivos (ej. precio fuera de rango, tiempos extendidos) para impulsar la competitividad futura.
6. **Emisión de Orden de Compra (OC) y Entrega:**
   Se formaliza la Orden de Compra de compromiso financiero y el proveedor adjudicado procede a la provisión o habilitación del servicio.
7. **Inspección Técnica, Recepción Conformada y Cierre Operativo:**
   El área técnica del proyecto (QA / Infraestructura) realiza las pruebas de homologación. Si el insumo satisface los criterios de aceptación, se firma la **Constancia de Recepción Conformada**, autorizando el pago y cerrando el circuito de compra.

---

### 2.3. Simulación Práctica de una Compra Real

A modo de caso práctico demostrativo para la materia, se simula el proceso de selección competitiva para el insumo **INS-03 (Licencia de Plataforma de Pruebas de Carga y Estrés SaaS)**:

#### Datos de la Compra Simula

- **Objeto:** Licencia SaaS para simulación de 100 usuarios concurrentes en visualizador WebGL.
- **Presupuesto Máximo de Referencia:** $150 USD / trimestre.
- **Plazo de Cotización:** 3 días hábiles.

#### Cuadro Comparativo de Ofertas Recibidas

| Criterio Evaluado                       | Peso (%) | Proveedor A (LoadMaster Cloud) |    Proveedor B (StressTester Pro)    | Proveedor C (QA-Metric SaaS)  |
| :-------------------------------------- | :------: | :----------------------------: | :----------------------------------: | :---------------------------: |
| **Capacidad Técnica (100 VUs + WebGL)** |   40%    |     5.0 (Cumple 100% SOW)      | 4.0 (Soporta Canvas, WebGL limitado) | 2.0 (No soporta métricas FPS) |
| **Precio Propuesto**                    |   30%    |     $120 USD (Score: 4.5)      |         $90 USD (Score: 5.0)         |     $140 USD (Score: 3.0)     |
| **Tiempo de Despliegue / Activación**   |   20%    |     Inmediata (Score: 5.0)     |        24 horas (Score: 4.0)         |     48 horas (Score: 2.0)     |
| **Soporte Técnico y SLA de Atención**   |   10%    |  24/7 en español (Score: 5.0)  |      Horario hábil (Score: 3.0)      |   Solo e-mail (Score: 2.0)    |
| **PUNTAJE PONDERADO TOTAL**             | **100%** |       **4.85 (GANADOR)**       |               **4.20**               |           **2.30**            |

**Dictamen de Adjudicación:** Se selecciona al **Proveedor A (LoadMaster Cloud)** con una puntuación de **4.85/5.00** por ofrecer la mejor relación calidad-precio y soporte integral para gráficos WebGL/Canvas.

---

## 3. Sistema de Evaluación de Desempeño de Proveedores (_Ex Post_)

### 3.1. Distinción Metodológica Clave

En concordancia con las aclaraciones del profesor Walter Lucero en la Clase 6 y Clase 13-10-2026, debe trazarse una distinción conceptual estricta:

- **Selección de Ofertas (_Ex Ante_):** Proceso de comparación de presupuestos y propuestas _antes de comprar_ para elegir al proveedor adjudicado.
- **Evaluación de Desempeño (_Ex Post_):** Auditoría de calidad _posterior a la entrega_ que califica el comportamiento real del proveedor durante la ejecución del contrato.

### 3.2. Criterios de Calificación Post-Compra y Termómetro de Desempeño

Finalizada la entrega del producto o servicio, el responsable del paquete de trabajo completa la Ficha de Evaluación Post-Compra ponderando 4 dimensiones en una escala de 1 a 5 estrellas:

1. **Puntualidad en la Entrega (30%):** Cumplimiento exacto del plazo estipulado en la Orden de Compra.
2. **Calidad Técnica y Ajuste al SOW (40%):** Ausencia de fallas, estabilidad y rendimiento del producto/servicio.
3. **Atención y Soporte Post-Venta (15%):** Velocidad y efectividad de respuesta ante incidentes técnicos.
4. **Cumplimiento Presupuestario (15%):** Inexistencia de sobrecostos o cargos adicionales no acordados.

#### Clasificación por Termómetro de Desempeño

- **Rango Verde (4.5 a 5.0 Estrellas) — Proveedor Preferente / Aliado Estratégico:** Elegible para contratación directa, renovaciones automáticas y prioridad en nuevas licitaciones.
- **Rango Amarillo (3.0 a 4.4 Estrellas) — Proveedor Aceptable en Observación:** Mantiene su inscripción activa pero requiere seguimiento estricto en próximas compras.
- **Rango Rojo (< 3.0 Estrellas) — Proveedor Sancionado / Bloqueado:** Penalización con suspensión del padrón por un período de 3 a 12 meses o baja definitiva del registro por incumplimiento grave.

```
 [1.0 ────────────── 2.9] ─────── [3.0 ────────────── 4.4] ─────── [4.5 ────────────── 5.0]
     ZONA ROJA (Bloqueado)            ZONA AMARILLA (Observación)         ZONA VERDE (Preferente)
```

### 3.3. Historial de Proveedores y Precios Testigo

Las calificaciones _ex post_ se alimentan en una base de datos centralizada de adquisiciones que genera los siguientes beneficios operativos:

- **Precios Testigo / Referencia:** Guarda el histórico de montos abonados por insumo para detectar cotizaciones infladas en futuras licitaciones.
- **Control de Documentación Impositiva y Legal:** Alerta automáticamente sobre vencimientos de certificados fiscales o comerciales del proveedor, bloqueando su participación si no mantiene la documentación al día.

---

## 4. Acuerdo de Nivel de Servicio (SLA — _Service Level Agreement_)

### 4.1. Propósito y Aplicabilidad en BioSignal

En proyectos como BioSignal, donde la infraestructura principal de servidores y conectividad no se adquiere en el mercado abierto sino que es provista por un **sponsor institucional (UNViMe)** a costo directo $0 USD, resulta indispensable formalizar un **Acuerdo de Nivel de Servicio (SLA)** para garantizar los estándares técnicos requeridos por el alcance del software.

### 4.2. Matriz de Especificaciones y Métricas del SLA con UNViMe

| Dimensión Técnica                          | Parámetro / Métrica Garantizada                                                                       | Método de Medición / Verificación                                         | Penalidad o Plan de Contingencia ante Incumplimiento                             |
| :----------------------------------------- | :---------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ | :------------------------------------------------------------------------------- |
| **Disponibilidad del Servidor (_Uptime_)** | **≥ 99.9% mensual** (máximo 43 minutos de parada no programada al mes).                               | Monitoreo continuo mediante ping/HTTP health-check cada 60 segundos.      | Reubicación inmediata del servicio al Servidor VPS de Reserva Failover (INS-01). |
| **Capacidad de Cómputo Asignada**          | 4 vCPUs dedicados, 8 GB RAM DDR4, 100 GB almacenamiento SSD NVMe.                                     | Telemetría de consumo de recursos en panel de control del servidor.       | Ajuste dinámico de cuotas de memoria o escalado horizontal provisional.          |
| **Ancho de Banda y Conectividad**          | Conexión simétrica de **≥ 10 Mbps sostenidos** con latencia < 50 ms.                                  | Benchmark periódico de velocidad de red y tiempo TTFB.                    | Redirección de tráfico mediante CDN / proxy inverso externo.                     |
| **Rendimiento de Ingesta (.EDF)**          | Procesamiento y validación binaria de cabecera **≤ 30 segundos** para archivos < 50 MB.               | Logs de auditoría de tiempo de ejecución en backend.                      | Optimización de hilos de ejecución y procesamiento asincrónico.                  |
| **Tiempo de Respuesta a Incidentes**       | Respuesta técnica inicial **< 2 horas** ante caídas críticas de servidor (24/7).                      | Sistema de tickets con marcas de tiempo automáticas.                      | Escalado directo de soporte a la Dirección de TIC de la UNViMe.                  |
| **Respaldos de Seguridad (_Backups_)**     | Copia de seguridad **diaria automatizada** de base de datos y archivos .edf con retención de 30 días. | Script de verificación de integridad y restauración semanal automatizada. | Generación manual inmediata de snapshot de base de datos.                        |

---

## 5. Matriz de Competencias del Personal (Gestión de Recursos)

### 5.1. Marco Teórico y los Cuatro Pilares de la Competencia

De acuerdo con el **PMBOK (Área de Gestión de Recursos del Proyecto)** y las directivas expuestas por el profesor Walter Lucero en la Clase 13-10-2026, la competencia es la capacidad de una persona para ejecutar las actividades asignadas de forma **eficaz** (cumplir el objetivo correctamente) y **eficiente** (optimizando tiempo y recursos).

Para evaluar integralmente a cada integrante, la competencia se compone de **cuatro pilares fundamentales**:

1. **Educación / Nivel de Instrucción:** Formación académica dentro del sistema educativo formal (Secundario, Terciario, Universitario, Posgrado).
2. **Formación Específica / Conocimientos Técnicos:** Cursos, capacitaciones, certificaciones, dominio de tecnologías, lenguajes, frameworks y estándares de la industria.
3. **Experiencia Requerida:** Tiempo ejercido en puestos similares, proyectos previos realizados o años de manejo práctico de un stack tecnológico.
4. **Habilidades (_Soft & Hard Skills_):** Capacidades operativas e interpersonales (liderazgo, comunicación asertiva, negociación, resolución de conflictos, trabajo en equipo).

---

### 5.2. Descripción Detallada de Actividades por Rol en BioSignal

A continuación se especifican los 6 roles del proyecto BioSignal con el desglose pormenorizado de las tareas y responsabilidades a su cargo:

#### 1. Director del Proyecto (PM) — Astudillo, Mateo Tomás

- **Descripción de Actividades:** Liderar la planificación estratégica y ejecución del proyecto; gestionar el alcance, cronograma y riesgos; actuar como nexo formal con las autoridades de la UNViMe y el sponsor EICA; coordinar las reuniones semanales de sincronización; supervisar la elaboración de los entregables formales de la materia.

#### 2. Asistente del Director del Proyecto — Ávila Gelbes, Ignacio Nicolás

- **Descripción de Actividades:** Asistir al PM en el seguimiento operativo de tareas y control del cronograma; administrar el repositorio documental y actas de reuniones; gestionar el plan de comunicaciones internas y externas; consolidar métricas de avance semanal.

#### 3. Desarrollador Backend / QA — Herrera, Germán Ezequiel

- **Descripción de Actividades:** Diseñar e implementar las APIs RESTful para la gestión de usuarios y metadatos; desarrollar el conjunto de pruebas unitarias e integración (Jest/PyTest); ejecutar las pruebas de carga y concurrencia (100 VUs); elaborar el informe consolidado de aseguramiento de calidad (QA).

#### 4. Desarrollador Full-Stack / Soporte Técnico — Mosainer, Martín David

- **Descripción de Actividades:** Implementar la integración de servicios entre frontend y backend; configurar el módulo de autenticación basada en roles (RBAC) y control de sesión por inactividad; gestionar la atención de incidentes técnicos; brindar soporte durante las fases de homologación.

#### 5. Desarrollador Backend / Infraestructura — Chiecher, Eber Blas

- **Descripción de Actividades:** Desarrollar el motor binario de parseo y validación de cabeceras de archivos .edf/.edf+; implementar el algoritmo de sanitización irreversible de datos personales (Ley 25.326); configurar contenedores Docker, servidor Nginx, certificados SSL/TLS y entornos de despliegue.

#### 6. Desarrolladora Frontend — Pereyra, Rocío

- **Descripción de Actividades:** Diseñar e implementar la interfaz de usuario interactiva y responsiva; construir el visor gráfico multicanal de bioseñales utilizando HTML5 Canvas/WebGL con renderizado acelerado (≥ 30 FPS); implementar los controles de paneo, zoom temporal/amplitud y calibración de escalas clínicas.

---

### 5.3. Matriz Consolidada de Competencias Requeridas (El Ideal del Proyecto)

| Rol del Proyecto                  | Integrante Asignado   | Educación / Instrucción Requerida (Pilar 1)                    | Formación / Conocimientos Específicos (Pilar 2)                                            | Experiencia Requerida (Pilar 3)                                                             | Habilidades Requeridas (_Skills_) (Pilar 4)                                                   |
| :-------------------------------- | :-------------------- | :------------------------------------------------------------- | :----------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------- |
| **Director del Proyecto (PM)**    | Astudillo, Mateo T.   | Universitario en cursado (Ing. en Sistemas - UNViMe).          | Marcos PMBOK 6/7, Gestión de Alcance, Riesgos, Compras y Metodologías Ágiles.              | ≥ 1 año en gestión de proyectos informáticos académicos o profesionales.                    | Liderazgo, negociación, gestión de conflictos, visión holística, comunicación técnica.        |
| **Asistente del PM**              | Ávila Gelbes, Ignacio | Universitario en cursado (Ing. en Sistemas - UNViMe).          | Gestión de comunicaciones, control de cronogramas, herramientas de gestión (Obsidian/Git). | Asistencia en proyectos de desarrollo de software o gestión de equipos.                     | Organización, atención al detalle, comunicación asertiva, capacidad analítica.                |
| **Dev Backend / QA**              | Herrera, Germán E.    | Universitario en cursado (Ing. en Sistemas / Cs. Computación). | Node.js / Python, diseño de APIs REST, Jest/PyTest, herramientas de carga (k6/JMeter).     | ≥ 1 año en desarrollo backend y diseño de suites de pruebas automatizadas.                  | Rigurosidad metodológica, pensamiento analítico, capacidad de debugging, trabajo en equipo.   |
| **Dev Full-Stack / Soporte**      | Mosainer, Martín D.   | Universitario en cursado (Ing. en Sistemas / Cs. Computación). | TypeScript, React/Node.js, PostgreSQL/SQL, gestión de autenticación JWT y RBAC.            | Experiencia en desarrollo web integrado y soporte técnico a usuarios.                       | Versatilidad, orientación al usuario, autonomía operativa, resolución de problemas.           |
| **Dev Backend / Infraestructura** | Chiecher, Eber B.     | Universitario en cursado (Ing. en Sistemas / Cs. Computación). | Parsing binario de archivos, especificación .edf/.edf+, Docker, Linux, Nginx, Ley 25.326.  | Experiencia en administración de servidores Linux, contenedores y manipulación de archivos. | Pensamiento estructurado, enfoque en rendimiento e infraestructura, rigurosidad en seguridad. |
| **Dev Frontend**                  | Pereyra, Rocío        | Universitario en cursado (Ing. en Sistemas / Cs. Computación). | HTML5 Canvas, WebGL, CSS adaptativo (Responsive), optimización LCP/FPS, UI/UX.             | Experiencia en desarrollo de interfaces web interactivas y gráficos de alto rendimiento.    | Creatividad visual, orientación a la usabilidad UI/UX, trabajo colaborativo.                  |

---

### 5.4. Matriz de Niveles de Competencia y Polivalencia (Escala 0 a 3)

Inspirada en el modelo de polivalencia analizado en clase, se establece la matriz de autonomía y suplencia del equipo. Esta herramienta permite verificar quién lidera cada área y quién posee la capacidad de asumir un rol de respaldo (_backup_) ante eventuales ausencias o contingencias:

#### Convención de Escala

- **Nivel 3 (Líder / Responsable Principal):** Domina la competencia, lidera la ejecución y supervisa a otros.
- **Nivel 2 (Autónomo / Suplente de Respaldo):** Ejecuta la tarea con autonomía completa; puede tomar el lugar del responsable principal (_backup_).
- **Nivel 1 (Ejecutor Inicial / En Desarrollo):** Realiza tareas básicas bajo supervisión o apoyo técnico.
- **Nivel 0 (No Aplica / Sin Competencia):** No posee la competencia ni le corresponde la ejecución.

| Áreas de Competencia del Proyecto                 | Mateo Astudillo (PM) | Ignacio Ávila (Asistente) | Germán Herrera (Backend/QA) | Martín Mosainer (Full-Stack) | Eber Chiecher (Infra/EDF) | Rocío Pereyra (Frontend) |
| :------------------------------------------------ | :------------------: | :-----------------------: | :-------------------------: | :--------------------------: | :-----------------------: | :----------------------: |
| **Gestión de Proyectos, Riesgos y Compras**       |    **3 (Líder)**     |       2 (Suplente)        |              1              |              1               |             1             |            1             |
| **Documentación y Comunicaciones**                |          2           |       **3 (Líder)**       |              1              |              2               |             1             |            1             |
| **Desarrollo Backend y APIs REST**                |          1           |             1             |        **3 (Líder)**        |         2 (Suplente)         |             2             |            0             |
| **Aseguramiento de Calidad (QA) y Pruebas**       |          1           |             1             |        **3 (Líder)**        |              2               |             1             |            1             |
| **Parsing Binario EDF y Sanitización Ley 25.326** |          0           |             0             |              2              |              1               |       **3 (Líder)**       |            0             |
| **Infraestructura, Docker y Nginx**               |          1           |             0             |              1              |              2               |       **3 (Líder)**       |            0             |
| **Desarrollo Frontend, Canvas y WebGL**           |          0           |             0             |              0              |         2 (Suplente)         |             0             |      **3 (Líder)**       |

---

## 6. Plan de Mejoras, Capacitación y Evaluación de Eficacia

### 6.1. Análisis de Brechas (_Gap Analysis_)

Al comparar el perfil ideal requerido por el proyecto contra el estado real del equipo al inicio del desarrollo, se diagnosticaron las siguientes 3 brechas críticas (_gaps_):

1. **Brecha 1 — Parsing Binario y Manipulación Estructural de Archivos .EDF/.EDF+ (Backend):**
   - _Diagnóstico:_ El desarrollador de infraestructura posee excelente dominio de Linux/Docker, pero carecía de experiencia previa en la lectura por bytes de la cabecera estándar European Data Format (.edf) y en la técnica de sanitización irreversible de datos sensibles.
2. **Brecha 2 — Renderizado Acelerado de Alto Rendimiento en HTML5 Canvas/WebGL (Frontend):**
   - _Diagnóstico:_ La desarrolladora frontend domina maquetación responsiva en CSS/React, pero requería profundizar técnicas avanzadas de renderizado por fragmentos (_chunking_) para sostener ≥ 30 FPS con señales de 1.000.000 de muestras.
3. **Brecha 3 — Ejecución de Pruebas de Estrés y Concurrencia Masiva (QA):**
   - _Diagnóstico:_ El desarrollador de QA domina pruebas unitarias con Jest, pero requería capacitarse en la configuración de scripts k6/JMeter para simular 100 usuarios simultáneos midiendo LCP.

---

### 6.2. Plan de Mejoras y Capacitación (Formato SMART)

Para cerrar las brechas identificadas de forma eficaz y eficiente, se diseñó el siguiente Plan de Capacitación estructurado bajo objetivos **SMART** (_Specific, Measurable, Achievable, Relevant, Time-bound_):

```
  [Brecha Diagnosticada] ──► [Plan de Capacitación SMART] ──► [Evaluación de Eficacia Práctica]
```

#### Programa de Capacitación 1: Taller Intensivo de Parsing Binario EDF y Sanitización

- **Objetivo SMART:** Lograr que el 100% del equipo Backend (Eber Chiecher y Germán Herrera) desarrolle un parser binario en Node.js/Python capaz de validar y anonimizar las cabeceras de 10 archivos EDF en menos de 30 segundos, antes del **20 de Octubre de 2026**.
- **Metodología y Duración:** Taller teórico-práctico interno de 12 horas con análisis de la especificación técnica EDF/EDF+ y revisión de código (_peer review_).
- **Presupuesto y Recursos:** $0 USD (Dictado por mentoría interna y documentación oficial del estándar EDF).

#### Programa de Capacitación 2: Curso de Renderizado de Alto Rendimiento con Canvas y WebGL

- **Objetivo SMART:** Capacitar a la desarrolladora Frontend (Rocío Pereyra) y al desarrollador Full-Stack (Martín Mosainer) en técnicas de renderizado por bloques (_chunking_) para sostener una tasa de refresco ≥ 30 FPS en el visor web ante registros de 32 canales, finalizando antes del **25 de Octubre de 2026**.
- **Metodología y Duración:** Curso de capacitación técnica en línea de 16 horas enfocado en optimización de contexto 2D Canvas y buffers WebGL.
- **Presupuesto y Recursos:** $0 USD (Financiado con licencias educativas de la plataforma de desarrollo).

#### Programa de Capacitación 3: Seminario de Pruebas de Carga y Simulación de Concurrencia

- **Objetivo SMART:** Capacitar al responsable de QA (Germán Herrera) en el diseño de escenarios de estrés masivo con k6 para simular 100 usuarios concurrentes sin caídas de servidor, completándolo antes del **30 de Octubre de 2026**.
- **Metodología y Duración:** Workshop práctico de 8 horas sobre telemetría de rendimiento y Core Web Vitals.
- **Presupuesto y Recursos:** $0 USD (Uso de versión comunitaria de herramienta de telemetría).

---

### 6.3. Procedimiento de Validación y Evaluación de Eficacia

En estricta concordancia con la advertencia del profesor Walter Lucero (_"El hecho de tomar una decisión de capacitación no garantiza que haya sido eficaz; hay que evaluarla mediante pruebas reales"_), se establece que **ninguna capacitación se dará por aprobada hasta superar la evaluación de eficacia práctica**:

| Capacitación Ejecutada         | Método de Evaluación de Eficacia Práctica                                                                                       | Criterio de Éxito para Dar por Cerrada la Brecha (Pasa / No Pasa)                           |   Estado de Cierre    |
| :----------------------------- | :------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------ | :-------------------: |
| **Parsing y Sanitización EDF** | **Prueba de Concepto (_Spike_) + Auditoría Forense:** Inspección binaria con script automatizado sobre 20 archivos sanitizados. | **0% de datos personales residuales** en la cabecera y procesamiento binario ≤ 30 segundos. | **APROBADO (Eficaz)** |
| **Renderizado Canvas/WebGL**   | **Perfilado de Rendimiento en DevTools:** Medición de tasa de refresco durante paneo y zoom continuo de 32 canales.             | Tasa sostenida de **≥ 30 FPS** sin congelamiento de la interfaz del navegador.              | **APROBADO (Eficaz)** |
| **Pruebas de Estrés y Carga**  | **Prueba de Carga Realizada (_Benchmark_):** Ejecución de script de simulación masiva sobre el entorno de staging.              | Resistencia operativa ante **100 usuarios simultáneos** con LCP ≤ 2,5 segundos.             | **APROBADO (Eficaz)** |

---

## 7. Resumen Ejecutivo y Trazabilidad de Entregables

El presente documento consolida la gestión operativa de compras y recursos para el proyecto BioSignal, garantizando el cumplimiento de los 5 entregables de la cátedra:

1. **Lista de Insumos (Sección 1):** 8 ítems definidos con especificaciones abiertas y alineados a la EDT.
2. **Proceso de Compras (Sección 2):** Circuito formal de 7 etapas con RFP/RFQ (plazo 3-5 días), adjudicación ponderada y feedback a oferentes.
3. **Evaluación de Proveedores (Sección 3):** Clasificación _ex post_ con termómetro de estrellas (Verde, Amarillo, Rojo) e historial de precios testigo.
4. **SLA Institucional (Sección 4):** Garantía de prestaciones de infraestructura UNViMe (uptime 99.9%, 100 GB SSD, respuesta < 2h).
5. **Matriz de Competencias y Plan de Mejoras (Secciones 5 y 6):** Evaluación en 4 pilares, matriz de suplencia 0-3, plan de capacitación SMART y validación obligatoria de eficacia práctica.

---
