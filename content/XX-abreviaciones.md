---
project: BioSignal
version: 1.0
title: Abreviaciones y siglas
aliases:
  - "Abreviaciones"
  - "Abreviaturas"
  - "Siglas"
  - "Glosario de siglas"
authors: Mateo Astudillo, Ignacio Ávila
date: 2026-11-12
---

# Abreviaciones y siglas

Este documento reúne las **siglas y acrónimos** que se usan en los documentos de gestión de BioSignal. Su objetivo es que cualquier lector pueda resolver una abreviatura sin salir del sitio y sin tener que reconstruir el significado por contexto.

> **Cómo se usa:** cada entrada tiene un encabezado con la sigla exacta. Los documentos enlazan la **primera aparición** de cada sigla a la entrada correspondiente; por eso los enlaces apuntan a este archivo y no a una definición duplicada en cada documento.

Complementa el glosario del contexto del proyecto y el glosario de la wiki organizacional descrito en [[10-gestion-de-conocimiento|Gestión del Conocimiento]].

## Organización, roles y gobernanza

#### UNViMe

Universidad Nacional de Villa Mercedes. Institución patrocinadora del proyecto (proyecto académico ficticio).

#### EICA

Escuela de Ingeniería y Ciencias Ambientales de la UNViMe. A través de su director, Ing. Alejandro Rosas, ejerce el rol de patrocinador (sponsor) del escenario.

#### GAB

Grupo de Administradores de Bioingeniería. Interesados clave que aporta los registros EDF del dataset semilla y valida los casos de uso clínicos del escenario.

#### TIC

Dirección de Tecnologías de la Información y la Comunicación de la UNViMe. Provee servidor, subdominio `*.unvime.edu.ar`, TLS y respaldos, y recibe el servicio en la transición.

#### PM

_Project Manager_ o Director del Proyecto. En BioSignal, Mateo Tomás Astudillo. Preside el CCB y responde por la planificación, el equipo y el cierre.

#### APM

Asistente del _Project Manager_ (Assistant Project Manager). En BioSignal, Ignacio Nicolás Ávila Gelbes. Mantiene la documentación, el seguimiento y el registro de cambios.

#### PMO

_Project Management Office_ u Oficina de Gestión de Proyectos. En este proyecto se usa como referencia organizacional; no existe una PMO formal (ver decisión de tailoring T-07).

#### RDS

Responsable del Servicio. Rol que evalúa el desempeño del equipo de desarrollo en la evaluación 360°; en BioSignal lo ejerce el APM.

#### CCB

_Change Control Board_ o Comité de Control de Cambios. Evalúa y dictamina las solicitudes de cambio: aprobado, rechazado, aplazado o aprobado con condiciones.

#### RFC

_Request for Change_ o Solicitud de Cambio. Documento con el que se registra, justifica y somete a decisión cualquier cambio de alcance, plazo, costo o línea base.

#### RACI

_Responsible, Accountable, Consulted, Informed_. Matriz de asignación de responsabilidades: quién ejecuta, quién aprueba, quién es consultado y quién es informado.

#### SLA

_Service Level Agreement_ o Acuerdo de Nivel de Servicio. Fija disponibilidad, tiempos de respuesta, respaldos y penalidades del servicio prestado.

#### OC

Orden de Compra. Documento que formaliza la adquisición adjudicada (en este proyecto, simulada).

#### RFQ

_Request for Quotation_ o Solicitud de Cotización. Pliego simplificado que se usa para productos estandarizados, como dominios o VPS.

#### INS

Identificador de insumo del plan de adquisiciones (`INS-01` a `INS-08`). No es una sigla literal: se conserva como prefijo estable del inventario de compras.

#### BIOSIG

Prefijo de los _issues_ y tickets del proyecto en GitHub Projects (por ejemplo, `BIOSIG-45`). Se usa para vincular cambios, PR y trazabilidad.

#### ID

Identificador. En los documentos designa un código estable que no se renumera ni se reutiliza.

#### N/A

No aplica. Se usa en las evaluaciones de desempeño cuando un instrumento no corresponde al rol evaluado; se excluye del promedio.

## Requisitos, entregables y planificación

#### ERS

Especificación de Requisitos de Software (documento [[03-especificacion-de-requisitos|03]]). Define requisitos funcionales, no funcionales, de transición y restricciones.

#### RTM

_Requirements Traceability Matrix_ o Matriz de Trazabilidad de Requisitos (documento [[07-matriz-de-trazabilidad-de-requisitos|07]]). Vincula necesidad, requisito, paquete del EDT y prueba.

#### EDT

Estructura de Desglose del Trabajo. Descomposición jerárquica del alcance en paquetes y actividades (documentos [[05-estructura-de-desglose-detrabajo|05]] y [[06-diccionario-del-edt|06]]).

#### WBS

_Work Breakdown Structure_. Equivalente en inglés de EDT.

#### RF

Requisito Funcional (`RF-01` a `RF-14`). Describe una capacidad que el producto debe ofrecer.

#### RNF

Requisito No Funcional (`RNF-01` a `RNF-15`). Define umbrales de desempeño, seguridad, usabilidad, disponibilidad y mantenibilidad.

#### RN

Requisito de Negocio (`RN-01` a `RN-04`). Expresa la necesidad institucional que justifica el proyecto.

#### RT

Requisito de Transición (`RT-01`, `RT-02`). Condición necesaria para poner el producto en operación.

#### RP

Restricción del Proyecto (`RP-01` a `RP-03`). Límite impuesto al proyecto, por ejemplo infraestructura institucional, fecha límite o marco ético.

#### EP

Entregable de Producto (`EP-01` a `EP-06`). Resultado tangible del software o del servicio.

#### EJ

Entregable de Proyecto (`EJ-01` a `EJ-06`). Artefacto de gestión o evidencia del proceso del proyecto.

#### O-01

Objetivo del proyecto (`O-01` a `O-07`). Cada objetivo tiene métrica y fecha de cumplimiento asociadas.

#### MVP

_Minimum Viable Product_ o Producto Mínimo Viable. Alcance reducido que conserva el valor central: ingesta, anonimización, visualización y exportación EDF.

## Calidad, pruebas y métricas

#### QA

_Quality Assurance_ o Aseguramiento de Calidad. Diseña y ejecuta las pruebas, verifica criterios de aceptación y puede recomendar o negar la liberación a producción.

#### UAT

_User Acceptance Testing_ o Pruebas de Aceptación del Usuario. Validación con docentes y GAB antes de la aceptación formal del patrocinador.

#### E2E

_End-to-End_ o pruebas de extremo a extremo. Recorren el flujo completo del usuario sobre la aplicación desplegada (por ejemplo, con Playwright).

#### PII

_Personally Identifiable Information_ o Información Personal Identificable. Datos que permiten identificar a una persona; el objetivo es **0 % de PII residual** tras la anonimización.

#### TTIS

_Time to Interactive Segment_. Tiempo hasta que el primer segmento de la señal queda visible e interactivo. Umbral: **≤ 2,5 s**.

#### LCP

_Largest Contentful Paint_. Métrica de rendimiento web que mide cuándo se pinta el elemento visual más grande; en BioSignal se usa como referencia de latencia percibida.

#### TTFB

_Time To First Byte_. Tiempo entre la solicitud y el primer byte de respuesta del servidor.

#### FPS

_Frames Per Second_ o cuadros por segundo. Medida de fluidez del visualizador durante paneo y zoom. Umbral: **≥ 30 FPS**.

#### WCAG

_Web Content Accessibility Guidelines_. Pautas de accesibilidad web del W3C. BioSignal adopta el nivel **WCAG 2.1 AA**.

#### RTO

_Recovery Time Objective_. Tiempo máximo aceptable para restablecer el servicio tras una caída. Umbral: **≤ 4 h**.

#### RPO

_Recovery Point Objective_. Cantidad máxima de datos que se acepta perder tras una falla. Umbral: **≤ 24 h**.

#### PDCA

_Plan-Do-Check-Act_ o Planificar-Hacer-Verificar-Actuar. Ciclo de mejora continua que se aplica a los indicadores de calidad.

#### EVM

_Earned Value Management_ o Gestión del Valor Ganado. Método de control de cronograma y costo mediante SPI = EV/PV y CPI = EV/AC.

#### PERT

_Program Evaluation and Review Technique_. Técnica de estimación de duraciones: `E = (TO + 4·TM + TP) / 6`.

## Configuración, desarrollo y arquitectura

#### SCM

_Software Configuration Management_ o Gestión de la Configuración del Software. Identifica, versiona y controla los artefactos del proyecto (documentos, código, datos y UI).

#### CI

_Configuration Item_ o Elemento de Configuración (`CI-DOC`, `CI-CODE`, `CI-DATA`, `CI-UI`). Unidad versionada y controlada por el plan de configuración.

> No confundir con **CI/CD**, que designa la integración y entrega continuas.

#### CI/CD

_Continuous Integration / Continuous Delivery_ o Integración Continua / Entrega Continua. Automatización de compilación, pruebas y despliegue.

#### PR

_Pull Request_. Solicitud de integración de cambios que exige revisión de una persona distinta del autor y paso limpio del pipeline.

#### ADR

_Architecture Decision Record_ o Registro de Decisión de Arquitectura. Documento breve que conserva el contexto, las alternativas, la decisión y sus consecuencias.

#### DDL

_Data Definition Language_. Sentencias SQL que definen o modifican la estructura de la base de datos (`CREATE`, `ALTER`, `DROP`).

#### DBA

_Database Administrator_ o Administrador de Base de Datos. Rol responsable del modelo de datos, los índices, los respaldos y los permisos de acceso.

#### ORM

_Object-Relational Mapping_ o Mapeo Objeto-Relacional. Capa que traduce objetos del código a tablas relacionales y gestiona migraciones.

#### SQL

_Structured Query Language_. Lenguaje de consulta y definición de datos usado en PostgreSQL.

#### SemVer

_Semantic Versioning_ o Versionado Semántico (`MAJOR.MINOR.PATCH`). Regla de numeración de releases del código.

#### RBAC

_Role-Based Access Control_ o Control de Acceso Basado en Roles. Modelo de permisos que asigna capacidades según el rol; BioSignal define los roles **Administrador** y **Consultor**.

#### JWT

_JSON Web Token_. Estándar de token firmado que se usa para autenticación y sesión.

#### API

_Application Programming Interface_ o Interfaz de Programación de Aplicaciones. Contrato de comunicación entre el frontend y el backend.

#### REST

_Representational State Transfer_. Estilo arquitectónico de las APIs HTTP del backend.

#### LLM

_Large Language Model_ o Modelo Grande de Lenguaje. Servicio de IA usado para sugerir metadatos clínicos durante la ingesta.

#### IA

Inteligencia Artificial. En este proyecto se usa solo como apoyo a la carga de metadatos, nunca para diagnóstico clínico.

#### AI

_Artificial Intelligence_. Equivalente en inglés de IA; aparece en las categorías del plan de adquisiciones.

#### DOM

_Document Object Model_. Representación en memoria del documento HTML; se evita sobrecargarlo para sostener la fluidez del visualizador.

#### HTML5

_HyperText Markup Language_ 5. Lenguaje de marcado de la interfaz web.

#### CSS

_Cascading Style Sheets_ u Hojas de Estilo en Cascada. Lenguaje de presentación visual de la interfaz.

#### UI/UX

_User Interface / User Experience_ o Interfaz de Usuario / Experiencia de Usuario. Disciplina que cubre el diseño visual y la interacción.

#### UX/UI

Variante de escritura de **UI/UX**; ambas designan el mismo par de disciplinas.

#### UI

_User Interface_ o Interfaz de Usuario.

#### UX

_User Experience_ o Experiencia de Usuario.

#### CDN

_Content Delivery Network_ o Red de Distribución de Contenidos. Caché geográfica que puede usarse como contingencia de ancho de banda.

#### DNS

_Domain Name System_ o Sistema de Nombres de Dominio. Traduce nombres como `*.unvime.edu.ar` a direcciones IP mediante registros `A` y `CNAME`.

#### TLS

_Transport Layer Security_. Protocolo de cifrado de las comunicaciones; BioSignal exige **TLS 1.3**.

#### HTTPS

_HyperText Transfer Protocol Secure_. HTTP cifrado mediante TLS.

#### HTTP

_HyperText Transfer Protocol_. Protocolo de transporte de la web.

#### IP

_Internet Protocol_. Dirección lógica de un servidor o dispositivo en la red.

#### VPS

_Virtual Private Server_ o Servidor Privado Virtual. Instancia de cómputo en la nube usada como contingencia (_failover_) del servidor institucional.

#### SaaS

_Software as a Service_ o Software como Servicio. Licencia de software consumida por suscripción; en el proyecto se usa de forma simulada.

#### VU

_Virtual User_ o Usuario Virtual. Unidad de carga que simula un usuario concurrente en las pruebas de estrés. Umbral: **100 VU**.

#### TLD

_Top-Level Domain_ o Dominio de Nivel Superior (por ejemplo, `.org` o `.com.ar`).

#### WHOIS

Servicio de consulta pública de los datos de registro de un dominio.

## Estándares, formatos y normativas

#### ISO

_International Organization for Standardization_. Organización de normalización; sus normas conjuntas se citan como **ISO/IEC** (con IEC, la Comisión Electrotécnica Internacional) o **ISO/IEC/IEEE** (con IEEE, el Instituto de Ingeniería Eléctrica y Electrónica).

#### PMBOK

_Project Management Body of Knowledge_. Guía de fundamentos de dirección de proyectos del PMI. BioSignal usa **PMBOK 7** como marco principal y conserva técnicas de PMBOK 6.

#### OWASP

_Open Worldwide Application Security Project_. Comunidad y estándares de seguridad de aplicaciones; se usa su lista de verificación y herramientas en las pruebas.

#### ZAP

_Zed Attack Proxy_. Herramienta de análisis de seguridad web de OWASP usada en las pruebas de seguridad.

#### C4

Modelo C4 de arquitectura: _Context, Containers, Components, Code_. Se usa para documentar la arquitectura del sistema en cuatro niveles.

#### EDF

_European Data Format_. Estándar binario para registrar señales biomédicas; es el único formato de ingesta y exportación del alcance. **EDF+** es su extensión con anotaciones con marca de tiempo y metadatos estructurados.

#### ECG

Electrocardiograma. Señal eléctrica del corazón; el dataset semilla incluye **15 ECG**.

#### EEG

Electroencefalograma. Señal eléctrica de la actividad cerebral; el dataset semilla incluye **15 EEG**.

#### CSV

_Comma-Separated Values_ o Valores Separados por Comas. Formato tabular de exportación **fuera del alcance**.

#### JSON

_JavaScript Object Notation_. Formato de intercambio de datos estructurados; su exportación está **fuera del alcance**.

#### MAT

Archivo de datos de MATLAB (MathWorks). Su exportación está **fuera del alcance**.

#### PDF

_Portable Document Format_. Formato de los informes y evidencias de pruebas.
