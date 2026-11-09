---
project: BioSignal
version: 1.0
title: 0. Contexto del Proyecto
aliases:
  - Contexto del Proyecto
  - Contexto BioSignal
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-11-09
---

# Contexto del Proyecto — BioSignal

> **Este documento no es una consigna ni un entregable evaluable.** Es el punto de entrada al proyecto: resume qué se está haciendo, con qué reglas, qué decisiones se tomaron y cómo se usa la guía PMBOK 7. Ante cualquier contradicción, **prevalece el documento fuente** (Acta, ERS, Enunciado del Alcance, EDT, etc.) y, si la contradicción es real, debe resolverse por el circuito de cambios (RFC/CCB).

## 1. Para qué sirve este documento

Sirve para que cualquier integrante —o un asistente de IA— pueda entender el proyecto en pocos minutos sin reconstruirlo leyendo toda la documentación. También deja por escrito algo que suele quedar implícito: **qué partes de PMBOK 7 se aplican, cuáles se adaptan y cuáles se dejan fuera, y por qué**.

### 1.1. Regla de oro

| Nivel                              | Qué es                                                                                                                        | Cómo se usa                                                                           |
| :--------------------------------- | :---------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------ |
| **1. Documentos fuente aprobados** | Acta, ERS, Alcance, EDT, Diccionario, RTM, Riesgos, Adquisiciones, Cambios, Conocimiento, Competencias, Calidad, Evaluaciones | Son la verdad operativa. Se citan y se actualizan por el circuito formal.             |
| **2. Este documento de contexto**  | Mapa, resumen y registro de decisiones de adaptación                                                                          | Explica el “por qué”. No reemplaza ni modifica los documentos fuente.                 |
| **3. Borradores y consignas**      | `content/borradores/` y `content/consignas/`                                                                                  | Material de trabajo y enunciados. No son fuente de verdad ni se publican en el sitio. |
| **4. Acuerdos verbales o de chat** | Reuniones, Discord, mensajes                                                                                                  | Solo valen cuando quedan registrados en un documento, acta, RFC o Change Log.         |

### 1.2. Advertencia: el proyecto es ficticio

BioSignal es un **trabajo práctico académico**. No existe un cliente real, un contrato real, un sistema en producción ni pacientes reales. La Universidad Nacional de Villa Mercedes (UNViMe), la EICA, el GAB, la Dirección TIC y los proveedores mencionados se usan como **escenario verosímil** para practicar la dirección de proyectos.

Consecuencias prácticas:

- Los roles, métricas, costos, proveedores, fechas y resultados son **simulados** o definidos por el equipo para cumplir las consignas.
- No hay datos personales de pacientes: cualquier EDF del escenario debe considerarse sintético o anonimizado.
- No deben contactarse autoridades, docentes ni proveedores reales invocando el proyecto.
- Las cifras no son estados contables ni auditorías reales; son **supuestos de planificación**.
- Lo que sí es real es el ejercicio de aplicar PMBOK 7, ISO y técnicas de gestión sobre un caso concreto.

### 1.3. Quién decide

El equipo del proyecto es el que toma las decisiones. PMBOK 7 se usa como **guía**, no como ley: sus principios y dominios orientan el criterio, pero la profundidad, los artefactos y el nivel de formalidad se ajustan al alcance académico, al tiempo disponible y a lo que piden las consignas. Esas decisiones se registran en la sección 13.

## 2. Resumen ejecutivo

**BioSignal** es una plataforma web para **cargar, catalogar, anonimizar, visualizar y exportar señales biomédicas** en formato EDF/EDF+. Apunta a que estudiantes y docentes de carreras de salud de la UNViMe puedan trabajar con casos clínicos del escenario desde el navegador, sin instalar software de escritorio ni depender de licencias comerciales.

El proyecto nace de una limitación concreta del escenario: herramientas como LightWAVE permiten visualizar señales públicas, pero no que la institución cargue y gobierne sus propios registros. BioSignal cubre ese hueco con un repositorio institucional, control de acceso por roles, anonimización irreversible y un visualizador interactivo multicanal.

**Propuesta de valor:** soberanía de datos, uso académico, divulgación institucional y una experiencia de visualización fluida en el navegador. **Restricción central:** hacerlo con desembolso de caja de **$0 USD**, en **15 semanas** (02/11/2026 a 15/02/2027) y con un esfuerzo interno de **260 a 360 horas**.

## 3. Ficha del proyecto

| Campo                          | Dato                                                                                                                                 |
| :----------------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| **Nombre**                     | BioSignal — Banco de Señales Biomédicas de la UNViMe                                                                                 |
| **Tipo**                       | Trabajo práctico integrador académico, proyecto ficticio                                                                             |
| **Sponsor**                    | EICA / UNViMe, representada por Ing. Alejandro Rosas (rol del escenario)                                                             |
| **Director del Proyecto (PM)** | Mateo Tomás Astudillo                                                                                                                |
| **Asistente del PM (APM)**     | Ignacio Nicolás Ávila Gelbes                                                                                                         |
| **Equipo**                     | Germán Herrera (Backend/QA), Martín Mosainer (Full-Stack/Soporte), Eber Chiecher (Backend/Infraestructura), Rocío Pereyra (Frontend) |
| **Inicio**                     | 02/11/2026 (Hito H1)                                                                                                                 |
| **Cierre**                     | 15/02/2027 (Hito H7), con puesta en producción el 12/02/2027                                                                         |
| **Duración**                   | 15 semanas                                                                                                                           |
| **Esfuerzo**                   | 260–360 horas (límite de la línea base)                                                                                              |
| **Caja**                       | $0 USD de desembolso directo                                                                                                         |
| **Costo interno de esfuerzo**  | ARS 10.000/h como valor de referencia (no erogable)                                                                                  |
| **Stack canónico**             | Frontend Next.js/React + TypeScript; Backend FastAPI/Python; PostgreSQL; Docker; CI/CD                                               |
| **Repositorio documental**     | `content/` publicado con Quartz                                                                                                      |
| **Sitio**                      | https://biosignalsbank.onrender.com/                                                                                                 |

> El “stack canónico” es una decisión de arquitectura del escenario. No implica que el código del producto esté en este repositorio: acá viven los artefactos de gestión. El código, si se materializa, corresponde a los entregables EJ-03 y a un repositorio aparte.

## 4. Problema, solución y alcance

### 4.1. Problema

- Los registros biomédicos están dispersos y no existe un repositorio institucional propio.
- Las herramientas disponibles no permiten cargar registros personalizados con metadatos académicos.
- La privacidad de datos de salud exige anonimización irreversible (Ley 25.326).
- Los estudiantes necesitan practicar con señales sin instalar software ni depender de licencias.

### 4.2. Solución

Una plataforma web con seis capacidades:

1. **RBAC** con dos roles: Administrador y Consultor.
2. **Ingesta EDF/EDF+** con validación de cabecera.
3. **Sanitización irreversible** de datos personales en cabecera, TALs y metadatos.
4. **Visualizador interactivo** multicanal con paneo, zoom y escalas clínicas.
5. **Exportación** del EDF sanitizado e íntegro, con trazabilidad.
6. **Acceso público demostrativo** con señal de prueba y enlace a admisiones.

### 4.3. Alcance del producto (resumen)

| Bloque            | Incluye                                                                            |
| :---------------- | :--------------------------------------------------------------------------------- |
| **Acceso**        | Login, sesión Admin de 30 min, RBAC Admin/Consultor, bloqueo tras 5 intentos       |
| **Ingesta**       | Carga EDF/EDF+, validación binaria, anonimización, metadatos académicos            |
| **Gestión**       | Edición de metadatos, baja lógica con doble confirmación, restauración por Admin   |
| **Visualización** | Hasta 32 canales, paneo, zoom X/Y, escalas 25 mm/s y 10 mm/mV, selector de canales |
| **Exportación**   | Descarga EDF sanitizado, íntegro y trazable (hash + auditoría)                     |
| **Público**       | Señal demo sintética o anonimizada + banner a admisiones                           |
| **Dataset**       | 30 EDF catalogados: 15 ECG + 15 EEG                                                |

### 4.4. Exclusiones principales

Quedan **fuera** del alcance:

- Anotaciones clínicas, etiquetado de eventos, calibradores o herramientas de medición sobre la señal.
- Registro público de usuarios y recuperación autónoma de credenciales.
- Roles distintos de Administrador y Consultor.
- Exportación a CSV, JSON, MATLAB u otros formatos.
- Captura en tiempo real o conexión a hardware biomédico.
- Diagnóstico automático, IA clínica o cualquier uso médico.
- Certificación como producto médico (ANMAT u otra).
- Apps nativas de Android/iOS o clientes de escritorio.
- Migración automática desde LightWAVE u otras plataformas.
- Manuales de usuario, capacitaciones y soporte post-cierre.

### 4.5. Restricciones y supuestos clave

| Tipo         | Detalle                                                                     |
| :----------- | :-------------------------------------------------------------------------- |
| **Tiempo**   | Fecha límite inamovible: 15/02/2027                                         |
| **Costo**    | $0 USD de caja; infraestructura institucional o capas gratuitas             |
| **Técnica**  | Solo EDF/EDF+; navegadores modernos sin plugins                             |
| **Legal**    | Ley 25.326; anonimización irreversible; convenios y avales éticos           |
| **Supuesto** | La Dirección TIC provee servidor, subdominio `*.unvime.edu.ar` y 100 GB     |
| **Supuesto** | El GAB entrega EDF anonimizados; si no, se usan PhysioNet o sintéticos (R1) |
| **Supuesto** | Los usuarios tienen internet y navegadores compatibles con Canvas/WebGL     |

## 5. Objetivos y criterios de éxito

| ID       | Objetivo                            | Métrica / criterio                                               | Fecha      |
| :------- | :---------------------------------- | :--------------------------------------------------------------- | :--------- |
| **O-01** | Autenticación y RBAC                | 2 roles; sesión Admin 30 min; 0 hallazgos críticos de elevación  | 18/12/2026 |
| **O-02** | Ingesta, sanitización y baja lógica | 30 EDF; 0 % PII residual; ≤ 30 s por archivo < 50 MB             | 15/01/2027 |
| **O-03** | Visualizador interactivo            | 32 canales; ≥ 30 FPS; TTIS ≤ 2,5 s; 100 usuarios                 | 29/01/2027 |
| **O-04** | Exportación y acceso público        | EDF sanitizado descargable; señal demo; enlace a admisiones      | 29/01/2027 |
| **O-05** | Despliegue productivo               | `*.unvime.edu.ar`; TLS 1.3; backup/restore; smoke test 100 %     | 12/02/2027 |
| **O-06** | Cierre                              | 0 defectos críticos/bloqueantes; acta de cierre firmada          | 15/02/2027 |
| **O-07** | Línea base de gestión               | Variación de esfuerzo/costo ≤ 10 %; 100 % de cambios registrados | 15/02/2027 |

**Beneficios que se miden después del cierre** (no durante la ejecución): adopción curricular en 2 cátedras (B-02), 50 usuarios que completan “buscar–abrir–configurar” (B-03) y tiempo medio < 5 min (B-04).

## 6. Entregables

### 6.1. Entregables de producto (EP)

| ID        | Entregable                                         |
| :-------- | :------------------------------------------------- |
| **EP-01** | Autenticación y control de acceso por roles (RBAC) |
| **EP-02** | Ingesta, sanitización y baja lógica                |
| **EP-03** | Visualizador interactivo de señales                |
| **EP-04** | Acceso público y enlace institucional              |
| **EP-05** | Exportación de registros EDF sanitizados           |
| **EP-06** | Dataset semilla: 30 EDF (15 ECG + 15 EEG)          |

### 6.2. Entregables de proyecto (EJ)

| ID        | Entregable                                 |
| :-------- | :----------------------------------------- |
| **EJ-01** | Acta de Constitución aprobada y versionada |
| **EJ-02** | ERS + Matriz de Trazabilidad               |
| **EJ-03** | Repositorios de código versionados con CI  |
| **EJ-04** | Reporte consolidado de QA                  |
| **EJ-05** | Acta de despliegue en producción           |
| **EJ-06** | Acta de cierre con lecciones aprendidas    |

## 7. Hitos y cronograma

| Hito                                | Fecha objetivo                 | Criterio de salida                                 |
| :---------------------------------- | :----------------------------- | :------------------------------------------------- |
| **H1 — Acta aprobada**              | 02/11/2026                     | Acta firmada; glosario y línea base v1.0           |
| **H2 — Requisitos aprobados**       | 13/11/2026                     | ERS + RTM + criterios de aceptación firmados       |
| **H3 — Autenticación/RBAC**         | 18/12/2026                     | 2 roles; sesión 30 min; 0 hallazgos críticos       |
| **H4 — Ingesta y sanitización**     | 15/01/2027                     | 30 EDF; 0 % PII; ≤ 30 s por archivo < 50 MB        |
| **H5 — Visualizador y exportación** | 29/01/2027                     | 32 canales; ≥ 30 FPS; TTIS ≤ 2,5 s; EDF sanitizado |
| **H6 — QA/UAT cerrado**             | 05/02/2027                     | 0 defectos críticos/bloqueantes; UAT aprobada      |
| **H7 — Despliegue y cierre**        | 12/02/2027 (cierre 15/02/2027) | Producción; TLS 1.3; backup/restore; acta firmada  |

**Fases:** (1) Iniciación y requisitos; (2) Seguridad y acceso; (3) Backend, ingesta y gestión; (4) Frontend y visualizador; (5) QA y despliegue; (6) Homologación y cierre.

## 8. Requisitos clave

### 8.1. Requisitos de negocio

- **RN-01:** Soberanía y gestión local de datos; 100 % alojado bajo control de la UNViMe.
- **RN-02:** Ventana de entrega operativa antes del ciclo lectivo 2027.
- **RN-03:** Soporte y adopción curricular en al menos 2 cátedras.
- **RN-04:** Difusión institucional y vínculo con admisiones.

### 8.2. Requisitos funcionales (agrupados)

| Grupo             | IDs           | Idea central                                                   |
| :---------------- | :------------ | :------------------------------------------------------------- |
| **Acceso**        | RF-01 a RF-03 | RBAC, expiración de sesión Admin, acceso público demo          |
| **Ingesta**       | RF-04 a RF-08 | EDF/EDF+, validación, anonimización, metadatos, baja lógica    |
| **Visualización** | RF-09 a RF-13 | Multicanal, paneo, zoom, escalas clínicas, selector de canales |
| **Exportación**   | RF-14         | Descarga EDF sanitizado, íntegro y trazable                    |

### 8.3. Requisitos no funcionales críticos

| ID         | Requisito                        | Umbral                                          |
| :--------- | :------------------------------- | :---------------------------------------------- |
| **RNF-01** | Concurrencia                     | 100 usuarios sin degradación                    |
| **RNF-02** | Tiempo al primer segmento (TTIS) | ≤ 2,5 s en red ≥ 10 Mbps                        |
| **RNF-03** | Fluidez                          | ≥ 30 FPS en paneo/zoom                          |
| **RNF-04** | Ingesta                          | ≤ 30 s para EDF < 50 MB                         |
| **RNF-05** | Privacidad                       | Ley 25.326; 0 % PII residual                    |
| **RNF-06** | Cifrado                          | HTTPS/TLS 1.3                                   |
| **RNF-07** | Navegadores                      | 2 últimas versiones de Chromium, Gecko y WebKit |
| **RNF-08** | Responsive                       | 32 canales en desktop; 1–2 en móvil             |
| **RNF-09** | Usabilidad                       | “Buscar–abrir–configurar” < 5 min               |
| **RNF-10** | Disponibilidad                   | ≥ 99,9 % mensual                                |
| **RNF-11** | Backup                           | Diario; RTO ≤ 4 h; RPO ≤ 24 h                   |
| **RNF-12** | Accesibilidad                    | WCAG 2.1 AA                                     |
| **RNF-13** | Auditoría                        | 100 % de altas, bajas, ediciones y descargas    |
| **RNF-14** | Mantenibilidad                   | Cobertura > 80 %; complejidad ≤ 10              |
| **RNF-15** | Seguridad de autenticación       | Rate limiting; bloqueo al 5.º intento           |

### 8.4. Transición y restricciones

- **RT-01:** Dataset semilla de 30 EDF antes de H4.
- **RT-02:** Despliegue en servidores UNViMe antes de H7.
- **RP-01:** Infraestructura institucional (`*.unvime.edu.ar`, 100 GB).
- **RP-02:** Fecha límite 15/02/2027.
- **RP-03:** Marco ético y convenios para señales hospitalarias.

La trazabilidad completa (necesidad → requisito → EDT → prueba) está en la **Matriz de Trazabilidad (07)**.

## 9. EDT, estimación y costos

### 9.1. Estructura de primer nivel

```
1.0 Banco de Señales Biomédicas
├── 1.1 Gestión del Proyecto
├── 1.2 Infraestructura y Entorno
├── 1.3 Software: Banco de Señales
│   ├── 1.3.1 Autenticación y seguridad
│   ├── 1.3.2 Gestión de señales
│   └── 1.3.3 Consulta y visualización
├── 1.4 Aseguramiento de Calidad
└── 1.5 Sistema desplegado en producción
```

El detalle de paquetes y actividades está en el **Diccionario del EDT (06)**.

### 9.2. Método de estimación

Se usa **PERT beta**:

```
E = (TO + 4·TM + TP) / 6
σ = (TP – TO) / 6
```

Donde `TO` es optimista, `TM` más probable y `TP` pesimista. Cada actividad publica su esperanza (≈ 50 % de confianza). Cuando el cálculo es simétrico, coincide con la media simple.

### 9.3. Costos

- **Caja:** $0 USD. No hay compras reales de infraestructura comercial.
- **Esfuerzo interno:** ARS 10.000/h como valor de referencia, no erogable.
- **Aportes en especie:** VPS de pruebas, dominio, pentesting, diseño UI/UX, dataset y herramientas de IA se registran en el plan de adquisiciones.
- **Control:** variación de esfuerzo/costo ≤ 10 % (O-07) y seguimiento con EVM (SPI/CPI ≥ 0,9).

> El costo en ARS es una **unidad de control académica**, no una obligación financiera. No debe confundirse con el presupuesto de caja, que es $0 USD.

## 10. Riesgos e incertidumbre

### 10.1. Apetito de riesgo

| Tipo de riesgo                             | Apetito   |
| :----------------------------------------- | :-------- |
| Privacidad, seguridad y cumplimiento legal | **Bajo**  |
| Técnicos y de cronograma                   | **Medio** |
| Oportunidades de innovación académica      | **Alto**  |

Ningún riesgo **crítico (15–25)** puede quedar residual al cierre. Los riesgos **altos (10–14)** requieren dueño, respuesta activa y seguimiento quincenal.

### 10.2. Escala

`Riesgo = Probabilidad × Impacto` (1 a 5 cada uno):

- **Bajo (1–4):** aceptable, monitoreo periódico.
- **Medio (5–9):** tolerable, mitigación estándar.
- **Alto (10–14):** atención prioritaria y respuesta activa.
- **Crítico (15–25):** inaceptable, acción inmediata y escalamiento.

### 10.3. Riesgos principales del escenario

| ID     | Riesgo                                 | Respuesta                                                              |
| :----- | :------------------------------------- | :--------------------------------------------------------------------- |
| **R1** | Demora en la entrega de EDF por el GAB | Obtener señales de otras fuentes desde H1; usar PhysioNet o sintéticos |
| **R2** | Bajo rendimiento del visualizador      | Chunking, Canvas/WebGL, pruebas de carga tempranas                     |
| **R3** | Reducción de disponibilidad del equipo | Margen entre H2 y H3; planificación flexible                           |

La **matriz de riesgos (XX)** define la evaluación. El registro completo con IDs **R-01…R-12** y oportunidades **O-01…O-03** se referencia en el plan integrador; si no está publicado, es una deuda documental a cerrar (ver sección 15).

## 11. Interesados y comunicaciones

### 11.1. Interesados clave

| Interesado                           | Necesidad / expectativa                            | Estrategia                                |
| :----------------------------------- | :------------------------------------------------- | :---------------------------------------- |
| **UNViMe / Sponsor (EICA)**          | Desarrollo propio, impacto académico y divulgación | Informe ejecutivo mensual + por hito      |
| **GAB (Bioingeniería)**              | Persistir y organizar bioseñales                   | Reunión quincenal; dataset y validación   |
| **Dirección TIC**                    | Infraestructura, subdominio, TLS y respaldos       | Acuerdo formal; checklist de transición   |
| **Estudiantes (ECS/EM)**             | Analizar señales sin software instalado            | Pilotos, UAT y comunicación de beneficios |
| **Docentes de cátedra**              | Repositorio ordenado por patología                 | Validación de casos y guías de TP         |
| **Asesoría legal / Comité de ética** | Cumplimiento Ley 25.326                            | Dictamen previo y auditoría               |
| **Equipo de desarrollo**             | Competencias profesionales y precedente académico  | Team charter, weekly y retrospectiva      |

El registro completo, con influencia, interés y nivel actual/deseado, está en **02b — Partes Interesadas**.

### 11.2. Cadencia de comunicación

| Qué                  | A quién            | Frecuencia                      | Canal                       |
| :------------------- | :----------------- | :------------------------------ | :-------------------------- |
| Estado del proyecto  | Sponsor            | Mensual + por hito              | Informe ejecutivo + reunión |
| Requisitos y alcance | GAB, TIC, docentes | Por hito                        | Repositorio + reunión       |
| Infraestructura      | Dirección TIC      | Semanal durante infraestructura | Ticket + checklist          |
| Riesgos              | Equipo y Sponsor   | Quincenal + por hito            | Informe de riesgos          |
| Cambios              | CCB y equipo       | Ante cada cambio                | RFC + reunión               |
| Coordinación interna | Equipo completo    | Semanal                         | Reunión + documento         |

**Escalamiento:** bloqueo técnico 24 h al PM; bloqueo de hito 48 h al Sponsor; cambio de alcance/plazo/costo 5 días hábiles al CCB + Sponsor; incidente de seguridad/privacidad inmediato a PM + Legal + TIC.

## 12. Gobernanza, calidad y conocimiento

### 12.1. Control de cambios

- **Quién solicita:** cualquier integrante o interesado, mediante RFC.
- **Quién analiza:** PM/APM, dueño del proceso y revisor técnico/legal según el elemento afectado.
- **Quién decide:** CCB (PM, APM, QA, Infraestructura; Sponsor cuando afecta alcance, plazo, costo o beneficios).
- **Quórum:** 3 miembros, incluido el PM.
- **Dictámenes:** aprobado, rechazado, aplazado o aprobado con condiciones.
- **SLA:** 48 h hábiles para cambios normales; 24 h para emergencias.
- **Registro:** Change Log con RFC, impacto, versión resultante y estado.

El flujo completo y la matriz de roles están en **09 — Gestión y Control de Cambios**.

### 12.2. Gestión de la configuración

| Elemento          | Herramienta / regla                                              |
| :---------------- | :--------------------------------------------------------------- |
| **Documentación** | Markdown en `content/`, versionado en Git y publicado con Quartz |
| **Código**        | GitHub, GitFlow simplificado, PR con revisor distinto del autor  |
| **Base de datos** | PostgreSQL; migraciones con `up` y `down` probados               |
| **UI/UX**         | Figma versionado; aprobación de maquetas                         |
| **Release**       | Versionado semántico; `main` protegida; CI obligatorio           |

La única versión vigente es la publicada en el repositorio central. Las versiones anteriores se conservan en Git para auditoría.

### 12.3. Calidad

El plan de calidad integra **PMBOK 7** con **ISO 9001/90003, ISO/IEC/IEEE 12207, ISO/IEC 25010, ISO/IEC 20000 e ISO/IEC/IEEE 29148**. Cubre tres dimensiones:

- **Proyecto:** procesos repetibles, trazables y auditables.
- **Producto:** atributos de calidad del software (funcionalidad, desempeño, seguridad, usabilidad, mantenibilidad).
- **Servicio:** puesta en servicio, monitoreo, backup/restore y transferencia a la UNViMe.

Los umbrales concretos (TTIS, FPS, concurrencia, PII, cobertura, accesibilidad, etc.) están en **12 — Gestión de Calidad**.

### 12.4. Conocimiento

Se adopta una estrategia de **wiki organizacional + Docs-as-Code**: una wiki central con estándares, plantillas y activos reutilizables, y una documentación en Markdown versionada con Git en cada proyecto. Los ADR, error logs, runbooks y lecciones son tipos de contenido dentro de esa estrategia, no iniciativas separadas. La documentación se actualiza como parte de la “definición de terminado”. Ver **10 — Gestión del Conocimiento**.

### 12.5. Competencias y desempeño

- **11 — Matriz de Competencias** cataloga 8 roles (UX/UI, Frontend, Backend, DBA, DevOps, PM, APM, QA) mapeados a 6 personas. Incluye educación, formación, habilidades y experiencia.
- **13 — Evaluaciones de Desempeño** aplica una evaluación multidimensional 360°: autoevaluación, pares, cliente, responsable del servicio (RDS) y evaluación ascendente del equipo a la dirección, con fichas integrales por integrante.

> La matriz de competencias **no es una RACI**. La asignación R/A/C/I se gestiona en la matriz RACI del plan integrador. Si esa matriz no está publicada, es una deuda documental.

### 12.6. Aceptación y cierre

- **Aceptación técnica:** QA valida criterios técnicos.
- **Aceptación de gestión:** PM valida entregables de gestión.
- **Cierre:** Sponsor/EICA y PM firman el Acta de Cierre.
- **Cierre anticipado:** imposibilidad técnica no solucionable, suspensión institucional o falta de datos/infraestructura con retraso > 30 % del cronograma.

## 13. PMBOK 7: qué se aplica y qué no

### 13.1. Cómo se usa PMBOK 7

PMBOK 7 no prescribe 49 procesos: propone **12 principios** y **8 dominios de desempeño**. El equipo lo usa así:

1. **PMBOK 7 como marco principal:** orienta el criterio, los principios y los dominios.
2. **PMBOK 6 como fuente de métodos:** se toman técnicas puntuales (PERT, EVM, EDT, diccionario, matriz de riesgos, RACI, gestión de adquisiciones) porque las consignas piden artefactos concretos.
3. **Adaptación explícita:** no se aplica todo con la misma profundidad. El nivel de formalidad se ajusta al alcance académico, al equipo de 6 personas y a las 15 semanas.
4. **Trazabilidad:** cada decisión de adaptación queda registrada en este documento y, cuando corresponde, en el Change Log.

### 13.2. Los 12 principios

| Principio                       | ¿Se aplica?      | Cómo se ve en BioSignal                                                         |
| :------------------------------ | :--------------- | :------------------------------------------------------------------------------ |
| **Diligencia**                  | Sí               | Gobernanza, ética, Ley 25.326, cuidado de datos y actas formales                |
| **Equipo**                      | Sí               | Roles, competencias, evaluaciones 360°, retrospectivas                          |
| **Interesados**                 | Sí               | Registro, matriz de involucramiento, plan de comunicaciones                     |
| **Valor**                       | Sí (parcial)     | Beneficios B-02/B-03/B-04 definidos; se miden post-cierre                       |
| **Pensamiento sistémico**       | Sí               | Integración alcance–tiempo–costo–calidad–riesgo; mirada de servicio             |
| **Liderazgo**                   | Sí               | Autoridad del PM, CCB, Sponsor, QA con veto técnico                             |
| **Adaptación (tailoring)**      | Sí               | MVP Opción A, híbrido predictivo/ágil, artefactos a medida                      |
| **Calidad**                     | Sí               | Plan ISO/PMBOK, métricas, auditorías, UAT                                       |
| **Complejidad**                 | Parcial          | Se identifican dependencias y riesgos; no hay modelo formal de complejidad      |
| **Riesgo**                      | Sí (cualitativo) | Matriz P×I, apetito, respuestas, seguimiento por hito                           |
| **Adaptabilidad y resiliencia** | Parcial          | Contingencia, margen y planes de respuesta; no hay prueba formal de resiliencia |
| **Cambio**                      | Sí               | RFC, CCB, Change Log, control de configuración                                  |

### 13.3. Los 8 dominios de desempeño

| Dominio                                   | ¿Se aborda? | Evidencia                                                         | Profundidad                   |
| :---------------------------------------- | :---------- | :---------------------------------------------------------------- | :---------------------------- |
| **Interesados**                           | Sí          | 02b Partes Interesadas; 02b Comunicaciones                        | Alta                          |
| **Equipo**                                | Sí          | 11 Competencias; 13 Evaluaciones; roles y autoridad               | Alta                          |
| **Enfoque de desarrollo y ciclo de vida** | Sí          | Híbrido: fases e hitos + GitFlow, PR, CI/CD, iteraciones          | Alta                          |
| **Planificación**                         | Sí          | Acta, Alcance, ERS, EDT, Diccionario, RTM, Riesgos, Adquisiciones | Alta                          |
| **Trabajo del proyecto**                  | Sí          | Procesos, adquisiciones simuladas, conocimiento, cambios          | Media (ejecución simulada)    |
| **Entrega**                               | Sí          | EP/EJ, criterios de aceptación, QA, despliegue planificado        | Media (producto no ejecutado) |
| **Medición**                              | Sí          | EVM, SPI/CPI, métricas de calidad, evaluaciones de desempeño      | Media (datos simulados)       |
| **Incertidumbre**                         | Sí          | Matriz de riesgos, apetito, supuestos, dependencias               | Media (cualitativa)           |

**Conclusión:** no se ignora ningún dominio. Lo que cambia es la **profundidad**: los dominios de planificación, interesados, equipo y calidad están muy desarrollados; los de trabajo, entrega y medición están planteados y simulados, porque el proyecto es académico y no hay una operación real.

### 13.4. Técnicas de PMBOK 6 que se conservan

| Técnica / artefacto                                              | Uso en BioSignal  |
| :--------------------------------------------------------------- | :---------------- |
| Acta de Constitución                                             | 02                |
| Recopilar requisitos / definir alcance                           | 03 y 04           |
| EDT y diccionario                                                | 05 y 06           |
| Estimar duraciones con PERT                                      | 06                |
| Estimar costos y presupuesto                                     | 06 y 11 del Acta  |
| Planificar / gestionar / controlar calidad                       | 12                |
| Planificar / identificar / analizar / responder riesgos          | XX                |
| Planificar / efectuar / controlar adquisiciones                  | 08                |
| Planificar / gestionar comunicaciones                            | 02b               |
| Planificar / gestionar interesados                               | 02b               |
| Monitorear y controlar el trabajo / control integrado de cambios | 09                |
| Gestionar el conocimiento                                        | 10                |
| Adquirir / desarrollar / dirigir al equipo                       | 11 y 13           |
| Controlar cronograma y costos con EVM                            | 06, 12 y reportes |
| Cerrar proyecto o fase                                           | 06 (1.1.5)        |

### 13.5. Lo que se deja fuera o se adapta (registro de tailoring)

| ID       | Decisión                       | Qué se aplica                                                         | Qué se deja fuera / se adapta                                                                              | Por qué                                                                              |
| :------- | :----------------------------- | :-------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------- |
| **T-01** | PMBOK 7 como marco principal   | Principios y dominios                                                 | Los 49 procesos de PMBOK 6 no se usan como checklist obligatorio                                           | PMBOK 7 no los exige; el equipo prioriza criterio y valor                            |
| **T-02** | Ciclo de vida híbrido          | Fases, hitos, líneas base + prácticas ágiles (PR, CI/CD, iteraciones) | Ni predictivo puro ni Scrum completo                                                                       | Fecha fija y alcance acotado, pero necesidad de adaptación técnica                   |
| **T-03** | MVP “Opción A”                 | 6 EP y 6 EJ                                                           | Registro público, recuperación de credenciales, roles extra, anotaciones/calibradores, export CSV/JSON/MAT | 15 semanas y 260–360 h; el valor central está en ingesta, visualización y privacidad |
| **T-04** | Compras simuladas              | Análisis hacer/comprar, matriz, pliegos, evaluación, proveedor        | Contratos reales, pagos reales y obligaciones legales                                                      | Presupuesto de caja $0 y proyecto ficticio                                           |
| **T-05** | Costo interno en ARS           | Valor hora de referencia y esfuerzo 260–360 h                         | Presupuesto de caja en USD y erogaciones reales                                                            | La universidad no financia infraestructura comercial                                 |
| **T-06** | Riesgo cualitativo             | Matriz P×I, apetito, respuestas, seguimiento                          | Monte Carlo, árboles de decisión, EMV cuantitativo                                                         | Suficiente para el alcance y el tamaño del equipo                                    |
| **T-07** | Gobernanza de proyecto único   | CCB, RFC, Change Log, actas                                           | PMO formal, gestión de programas y portafolio                                                              | El ejercicio es un proyecto, no una organización completa                            |
| **T-08** | Beneficios post-cierre         | B-02, B-03, B-04 definidos y con dueño                                | Medición real de beneficios durante el proyecto                                                            | Los beneficios dependen del ciclo lectivo 2027                                       |
| **T-09** | Documentación como código      | Markdown, Git, Quartz, Docs-as-Code                                   | Wiki corporativa o herramienta de PMO                                                                      | Equipo pequeño, transparencia y trazabilidad                                         |
| **T-10** | Ejecución simulada             | Planes, métricas, QA y actas                                          | Desarrollo real, despliegue real, usuarios reales y datos reales                                           | El proyecto es ficticio; el entregable es la gestión                                 |
| **T-11** | Sin manuales ni capacitación   | Producto y transferencia técnica                                      | Manuales de usuario, cursos y talleres                                                                     | Excluido explícitamente del alcance                                                  |
| **T-12** | Estándares ISO complementarios | Calidad de producto, proceso y servicio                               | Certificación formal ISO                                                                                   | Se usan como referencia metodológica, no como auditoría certificada                  |

### 13.6. Qué cambiaría en un proyecto real

Si BioSignal fuera un proyecto real, habría que:

- Publicar el **plan integrador**, el **registro de tailoring**, la **RACI** y el **registro completo de riesgos**.
- Reemplazar las compras simuladas por contratos y órdenes de compra reales.
- Medir beneficios post-cierre con un plan formal de realización de beneficios.
- Ejecutar el producto, el despliegue, la UAT y las auditorías con datos reales.
- Hacer análisis cuantitativo de riesgos si el impacto justifica el esfuerzo.
- Formalizar la gestión de incidentes, problemas y capacidad operativa.

## 14. Mapa de consignas, documentos y PMBOK 7

| Consigna                       | Documento principal                          | Dominio / principio PMBOK 7         | Estado                         |
| :----------------------------- | :------------------------------------------- | :---------------------------------- | :----------------------------- |
| 02 — Acta de Constitución      | `02-acta-de-constitucion.md`                 | Interesados, Planificación, Entrega | Publicado                      |
| 02b — Comunicaciones           | `02b-gestion-de-las-comunicaciones.md`       | Interesados                         | Publicado                      |
| 02b — Partes Interesadas       | `02b-gestion-de-las-partes-interesadas.md`   | Interesados                         | Publicado                      |
| 03 — Requisitos                | `03-especificacion-de-requisitos.md`         | Planificación, Entrega              | Publicado                      |
| 04 — Enunciado del Alcance     | `04-enunciado-del-alance-del-proyecto.md`    | Planificación                       | Publicado                      |
| 05 — EDT                       | `05-estructura-de-desglose-detrabajo.md`     | Planificación                       | Publicado                      |
| 06 — Diccionario del EDT       | `06-diccionario-del-edt.md`                  | Planificación, Medición             | Publicado                      |
| 06b — Actividades en Jira      | Evidencia externa / diccionario              | Trabajo del Proyecto, Planificación | **No versionado en este repo** |
| 07 — Matriz de Trazabilidad    | `07-matriz-de-trazabilidad-de-requisitos.md` | Planificación, Medición             | Publicado                      |
| XX — Matriz de Riesgos         | `XX-matriz-de-riesgos.md`                    | Incertidumbre                       | Publicado                      |
| 08 — Adquisiciones             | `08-gestion-de-adquisiciones.md`             | Trabajo del Proyecto                | Publicado                      |
| 09 — Cambios y configuración   | `09-gestion-y-control-de-cambios.md`         | Trabajo del Proyecto, Planificación | Publicado                      |
| 10 — Conocimiento              | `10-gestion-de-conocimiento.md`              | Trabajo del Proyecto, Equipo        | Publicado                      |
| 11 — Competencias              | `11-matriz-de-competencias.md`               | Equipo                              | Publicado                      |
| 12 — Calidad                   | `12-gestion-de-calidad.md`                   | Entrega, Medición                   | Publicado                      |
| 13 — Evaluaciones de desempeño | `13-evaluaciones-de-desempeño.md` + carpeta  | Equipo, Medición                    | Publicado                      |

## 15. Estado de avance y deudas documentales

### 15.1. Publicado y utilizable

- Acta, ERS, Alcance, EDT, Diccionario, RTM, Matriz de Riesgos, Adquisiciones, Cambios, Conocimiento, Competencias, Calidad y Evaluaciones.
- Comunicaciones y Partes Interesadas.
- Índice del sitio.

### 15.2. Referenciado pero no publicado como documento autónomo

| Artefacto                      | Dónde se menciona                             | Situación                                                                                  |
| :----------------------------- | :-------------------------------------------- | :----------------------------------------------------------------------------------------- |
| Plan integrador                | RFC-006; riesgos; calidad                     | Referenciado, sin archivo propio                                                           |
| Registro de tailoring          | RFC-006; borradores de calidad y competencias | Referenciado; este documento cubre parte del contenido                                     |
| Matriz RACI                    | 11 Competencias; 12 Calidad                   | Referenciada; no hay archivo RACI                                                          |
| Registro de riesgos R-01…R-12  | XX Matriz de Riesgos                          | Referenciado; no está el registro completo                                                 |
| Caso de negocio                | RFC-006                                       | Referenciado; la justificación está en el Acta                                             |
| Registro de beneficios         | RFC-006; 04 Alcance                           | Referenciado; la tabla B-02/B-03/B-04 está en el Alcance                                   |
| Evidencia Jira (06b)           | Consigna 06b                                  | No versionada en este repo                                                                 |
| Plan de mejora de competencias | Consigna 11                                   | Publicado como sección del documento 11 (acciones, responsables e indicadores de eficacia) |

### 15.3. Inconsistencias a revisar

- El **Acta v2.0** figura como “Aprobado” en su registro de cambios, pero el **RFC-004** del Change Log está “Pendiente Sponsor”. Definir cuál es el estado formal.
- Varios documentos están en **v1.1/v2.0 “Propuesto (pendiente CCB)”**. El Change Log debe ser la referencia única del estado.
- La **matriz de riesgos** promete un registro R-01…R-12 que no está publicado; sin él, la gestión de riesgos queda incompleta.
- La **matriz de competencias** se declara catálogo y no RACI; si no existe la RACI, la asignación de responsabilidades queda distribuida entre varios documentos.
- La **evaluación 360°** ya cuenta con cobertura documentada y evaluación ascendente; queda pendiente repetirla al cierre de la primera fase formal.

> Estas brechas no invalidan el trabajo: son tareas de cierre para que la documentación quede coherente con lo que ella misma declara.

## 16. Convenciones de trabajo

### 16.1. Documentos

- Formato Markdown con frontmatter YAML: `project`, `version`, `title`, `aliases`, `authors`, `date`.
- Nombres de archivo con prefijo numérico (`02-`, `03-`, …) y guiones.
- Enlaces internos estilo Obsidian (`[[...]]`) o relativos a `.md` con anclas (`#^rf-01`).
- Fechas en formato `dd/mm/aaaa`.
- Moneda: `USD` para caja y `ARS` para esfuerzo interno; no mezclar.
- Versionado: `v0.x` en revisión, `v1.0` aprobado, `v1.x` corrección menor.
- Todo cambio de alcance, plazo, costo o beneficio requiere RFC y registro en el Change Log.

### 16.2. Sitio

- `content/` es la raíz publicada.
- `content/borradores/` y `content/consignas/` están excluidos por `ignorePatterns`.
- El índice (`index.md`) lista los documentos publicados.
- La publicación se genera con Quartz; la versión vigente es la del repositorio.

### 16.3. Reglas de coherencia

1. No inventar métricas, fechas, costos ni stakeholders que no estén en los documentos fuente.
2. Si se agrega un requisito, actualizar ERS, RTM y, si impacta, EDT y Alcance.
3. Si se cambia un umbral, revisar todas las menciones (Acta, ERS, Alcance, Calidad, RTM).
4. Mantener los IDs (`O-`, `EP-`, `EJ-`, `H`, `RF-`, `RNF-`, `RN-`, `RI-`, `RT-`, `RP-`, `R-`, `RFC-`) estables.
5. No usar datos personales reales; todo EDF debe ser sintético o anonimizado.
6. Marcar explícitamente los supuestos y las decisiones de tailoring.
7. Si un documento contradice a otro, gana el documento fuente y se abre RFC para corregir.

## 17. Glosario

| Término             | Significado                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| **EDF / EDF+**      | European Data Format, estándar binario para señales biomédicas           |
| **ECG / EEG / EMG** | Electrocardiograma / Electroencefalograma / Electromiograma              |
| **RBAC**            | Control de acceso basado en roles                                        |
| **PII**             | Información personal identificable                                       |
| **TAL**             | Time-stamped Annotations List (anotaciones de EDF+)                      |
| **TTIS**            | Time to Interactive Segment; tiempo hasta el primer segmento interactivo |
| **FPS**             | Frames por segundo                                                       |
| **EVM**             | Earned Value Management; SPI = EV/PV, CPI = EV/AC                        |
| **EDT / WBS**       | Estructura de Desglose del Trabajo                                       |
| **RTM**             | Requirements Traceability Matrix                                         |
| **RFC**             | Request for Change; solicitud de cambio                                  |
| **CCB**             | Change Control Board; comité de control de cambios                       |
| **RACI**            | Responsible, Accountable, Consulted, Informed                            |
| **UAT**             | User Acceptance Testing                                                  |
| **SLA**             | Service Level Agreement                                                  |
| **RTO / RPO**       | Recovery Time Objective / Recovery Point Objective                       |
| **MVP**             | Minimum Viable Product                                                   |
| **PMBOK 7**         | Guía de los Fundamentos para la Dirección de Proyectos, 7.ª edición      |

## 18. Checklist para futuras ediciones (humanos o IA)

Antes de modificar o generar un documento:

- [ ] Leer este contexto y el documento fuente correspondiente.
- [ ] Verificar que la decisión no contradiga el alcance, las exclusiones ni los umbrales aprobados.
- [ ] Mantener el tono, el formato, los IDs y las convenciones de fecha/moneda.
- [ ] Distinguir claramente entre **dato del escenario**, **supuesto** y **decisión de tailoring**.
- [ ] Si se agrega o cambia un requisito, actualizar la RTM y el Change Log.
- [ ] Si se cambia un hito, revisar Acta, Alcance, EDT, Calidad y Comunicaciones.
- [ ] No presentar el proyecto como real ni usar datos de pacientes reales.
- [ ] Registrar la deuda documental que quede abierta en la sección 15.
- [ ] Publicar solo en `content/`; no mezclar borradores ni consignas con la documentación vigente.

---

**Resumen en una frase:** BioSignal es un proyecto ficticio de la UNViMe para practicar dirección de proyectos; el equipo decide cómo aplicar PMBOK 7, usa sus principios y dominios como guía, conserva técnicas de PMBOK 6 como fuente de métodos y deja fuera todo lo que no aporta valor al alcance académico, al plazo de 15 semanas y al presupuesto de caja de $0 USD.
