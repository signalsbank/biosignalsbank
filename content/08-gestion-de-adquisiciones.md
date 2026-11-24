---
project: BioSignal
version: 1.2
title: 8. Gestión de Adquisiciones
aliases:
  - "Gestión de Adquisiciones"
  - "Adquisiciones"
---

## 1. Lista de Insumos y Productos a Comprar (Análisis de Hacer o Comprar)

### 1.1. Contexto Metodológico y Restricción Financiera

Aunque el proyecto **BioSignal** opera bajo una restricción formal de **$0 USD de costo directo recurrente** en infraestructura comercial por sustentarse en los servidores institucionales de la **Universidad Nacional de Villa Mercedes ([[XX-abreviaciones#UNViMe|UNViMe]])**, se detallan los insumos, licencias, servicios profesionales, equipamiento y conjuntos de datos requeridos para la ejecución, aseguramiento de la calidad y contingencia del sistema.

### 1.2. Análisis Hacer, Comprar o Recibir como Aporte

| Componente                                                                                   | Decisión                                                                                | Justificación                                                                                                                                 |
| -------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Plataforma BioSignal (frontend, backend, parser [[XX-abreviaciones#EDF\|EDF]], visualizador) | **Hacer**                                                                               | Es el núcleo del alcance y no existe una solución lista que cumpla [[XX-abreviaciones#RBAC\|RBAC]], anonimización y visualización requeridas. |
| Servidor, subdominio y almacenamiento                                                        | **Recibir aporte de UNViMe**                                                            | [[03-especificacion-de-requisitos#6. Requisitos y Restricciones del Proyecto\|RP-01]]; no hay erogación de caja.                              |
| Dominio web de respaldo                                                                      | **Comprar / aporte en especie**                                                         | Contingencia si se demora la delegación del subdominio; costo referencial.                                                                    |
| Pruebas de carga                                                                             | **Hacer con k6/JMeter**; comprar [[XX-abreviaciones#SaaS\|SaaS]] solo como contingencia | La prueba es estándar y no justifica una licencia recurrente; el SaaS se simula para comparar alternativas.                                   |
| Auditoría de seguridad y anonimización                                                       | **Contratar / aporte en especie**                                                       | Requiere dictamen independiente y experiencia forense que el equipo no tiene.                                                                 |
| Servicio de [[XX-abreviaciones#IA\|IA]] para metadatos                                       | **Comprar por consumo** (créditos, simulado)                                            | Acelera el etiquetado; es opcional y con costo referencial.                                                                                   |
| Dataset semilla                                                                              | **Recibir de [[XX-abreviaciones#GAB\|GAB]] / PhysioNet / sintéticos**                   | [[03-especificacion-de-requisitos#6. Requisitos y Restricciones del Proyecto\|RP-03]]; no se compra.                                          |
| Diseño [[XX-abreviaciones#UI/UX\|UI/UX]]                                                     | **Hacer**                                                                               | Está dentro de las competencias del equipo.                                                                                                   |

> Los insumos **INS-04, INS-06 e INS-07** se evaluaron y no se adquieren: se cubren con herramientas open source o aportes en especie. Por eso se conservan los identificadores originales de los insumos que sí requieren análisis de compra.

### 1.3. Matriz Consolidada de Insumos y Productos

| Ítem       | Nombre del Insumo / Producto                                                        | Categoría                              | Especificaciones Técnicas y Criterios de Calidad Requeridos                                                                                                                                                    | Paquete de Trabajo [[XX-abreviaciones#EDT\|EDT]] / Req. Asociado                                                                                                                                                                | Justificación Técnica en BioSignal                                                                                      |
| ---------- | ----------------------------------------------------------------------------------- | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **INS-01** | **Servidor [[XX-abreviaciones#VPS\|VPS]] / Cloud de Reserva (Failover)**            | Hardware / Hosting                     | Instancia virtual de cómputo Linux (4 vCPUs, 8 GB RAM, 100 GB SSD NVMe, red ≥ 10 Mbps, soporte Docker, uptime 99.9%).                                                                                          | `1.2.1 Servidores y base de datos configurados`<br>([[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-01]], [[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-02]])                         | Garantizar la alta disponibilidad y contingencia ante mantenimientos o caídas de la infraestructura local de la UNViMe. |
| **INS-02** | **Registro de Nombre de Dominio Web Dedicado**                                      | Dominio / Red                          | Dominio [[XX-abreviaciones#TLD\|TLD]] de segundo/tercer nivel (.org / .com.ar) con soporte [[XX-abreviaciones#DNS\|DNS]] dinámico, registros CNAME/A y privacidad [[XX-abreviaciones#WHOIS\|WHOIS]].           | `1.5 Sistema desplegado en ambiente de producción`<br>([[03-especificacion-de-requisitos#5. Requisitos de Transición y Preparación Operativa\|RT-02]], [[03-especificacion-de-requisitos#4.2. Seguridad y Privacidad\|RNF-06]]) | Asegurar acceso web público de respaldo si se demorase la delegación del subdominio `*.unvime.edu.ar`.                  |
| **INS-03** | **Licencia de Plataforma de Pruebas de Carga y Estrés (SaaS)**                      | Software / [[XX-abreviaciones#QA\|QA]] | Plan SaaS para simulación de concurrencia masiva (≥ 100 [[XX-abreviaciones#VU\|VUs]] - Virtual Users simultáneos) con métricas de latencia [[XX-abreviaciones#LCP\|LCP]] y tasa [[XX-abreviaciones#FPS\|FPS]]. | `1.4.2 Reporte de pruebas de integración y aceptación`<br>([[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-01]], [[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-02]])                  | Certificar objetivamente la capacidad operativa de 100 usuarios simultáneos y LCP ≤ 2,5 s sin degradación.              |
| **INS-05** | **Servicio de Auditoría de Seguridad y Anonimización**                              | Servicios Profesionales                | Servicio de auditoría forense binaria sobre cabeceras .edf/.edf+ con dictamen normativo Ley 25.326.                                                                                                            | `1.3.2.1 Formulario y procesador de carga`<br>([[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros\|RF-06]], [[03-especificacion-de-requisitos#4.2. Seguridad y Privacidad\|RNF-05]])          | Auditar la eliminación 100% irreversible de datos personales de pacientes en cumplimiento legal estricto.               |
| **INS-08** | **Bolsa de Créditos/Tokens de [[XX-abreviaciones#API\|API]] de Procesamiento e IA** | Software / [[XX-abreviaciones#AI\|AI]] | Créditos/tokens para servicio de IA/[[XX-abreviaciones#LLM\|LLM]] enfocado en extracción automática de metadatos clínicos e indexación de patologías.                                                          | `1.3.2.2 Interfaz de edición de metadatos`<br>([[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros\|RF-07]])                                                                                   | Asistir al administrador en la sugerencia y etiquetado automático de patologías durante la ingesta.                     |

### 1.4. Matriz de Adquisiciones

Los importes son **referencias de mercado para el ejercicio**: no representan erogación de caja. La compra real solo se activa si la UNViMe o un aporte en especie no cubre la necesidad.

| Ítem       | EDT / requisito                                                                                                                                                                                                                       | Tipo de contrato / modalidad                  | Proveedores candidatos                             | Responsable                               | Costo estimado                       | Fecha requerida                                                                    | Planificación                                                                                                                                                                                                  | Cierre                                           |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------- | ----------------------------------------- | ------------------------------------ | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| **INS-01** | `1.2.1` / [[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-01]], [[03-especificacion-de-requisitos#4.5. Disponibilidad, Respaldo, Accesibilidad, Auditoría, Mantenibilidad y Seguridad (RNF adicionales)\|RNF-10]] | Servicio cloud (simulado) o aporte en especie | UNViMe/TIC; proveedor cloud A/B                    | Chiecher                                  | USD 0 (referencia USD 60/mes)        | 05/02/2027 ([[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H6]]) | Solicitud al confirmar [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H5]]; cotización 3–5 días; adjudicación antes de [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H6]] | Recepción conforme y prueba de _failover_        |
| **INS-02** | `1.5` / [[03-especificacion-de-requisitos#5. Requisitos de Transición y Preparación Operativa\|RT-02]], [[03-especificacion-de-requisitos#4.2. Seguridad y Privacidad\|RNF-06]]                                                       | Registro de dominio (compra simulada)         | NIC.ar; registrador .org A/B                       | Astudillo / [[XX-abreviaciones#APM\|APM]] | USD 0 (referencia USD 15/año)        | 12/02/2027 ([[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H7]]) | Solicitar en [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H5]]; verificar DNS y [[XX-abreviaciones#TLS\|TLS]]                                                                              | DNS resuelve y certificado válido                |
| **INS-03** | `1.4.2` / [[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-01]], [[03-especificacion-de-requisitos#4.1. Eficiencia de Desempeño\|RNF-02]]                                                                          | SaaS (simulado) o herramienta open source     | LoadMaster Cloud; StressTester Pro; QA-Metric SaaS | Herrera                                   | USD 0 (referencia USD 120/trimestre) | 05/02/2027 ([[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H6]]) | Evaluar en [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H5]]; usar k6 si cubre; si no, contratar SaaS                                                                                      | Informe de carga aceptado                        |
| **INS-05** | `1.3.2.1` / [[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros\|RF-06]], [[03-especificacion-de-requisitos#4.2. Seguridad y Privacidad\|RNF-05]]                                                    | Servicios profesionales (simulado / aporte)   | Consultora A/B; asesoría UNViMe                    | Astudillo / Chiecher                      | USD 0 (referencia USD 800)           | 15/01/2027 ([[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H4]]) | Solicitud en [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H3]]; dictamen antes de [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H4]]                                    | Dictamen legal y 0 [[XX-abreviaciones#PII\|PII]] |
| **INS-08** | `1.3.2.2` / [[03-especificacion-de-requisitos#3.2. Ingesta, Anonimización y Gestión de Registros\|RF-07]]                                                                                                                             | Consumo de API (simulado)                     | LLM API A/B                                        | Herrera                                   | USD 0 (referencia USD 50)            | 15/01/2027 ([[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H4]]) | Prueba en [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación\|H3]]; límite de consumo                                                                                                             | Integración aprobada                             |

> En todos los casos, el cierre de la compra incluye la **evaluación post-compra registrada** (etapa 8 del circuito, sección 3.4).

### 1.5. Fichas de Solicitud de Compra para Insumos Clave

#### Ficha de Solicitud INS-01: Servidor VPS de Contingencia (Failover)

- **Categoría:** Hosting / Infraestructura Cloud.
- **Especificación Técnica:** Servidor virtual con sistema operativo Linux (Ubuntu Server 24.04 LTS), 4 vCPUs, 8 GB RAM, 100 GB de almacenamiento SSD NVMe, tasa de transferencia mensual de al menos 1 TB, soporte nativo para Docker/Docker-Compose, dirección [[XX-abreviaciones#IP|IP]] pública dedicada y protocolo TLS 1.3 preconfigurado.
- **Cantidad:** 1 Instancia (contratación por 6 meses).
- **Criterio de Aceptación:** Uptime comprobado ≥ 99.9% e instalación exitosa del contenedor Docker de BioSignal en menos de 15 minutos.
- **Justificación EDT:** Paquete `1.2.1 Servidores`.

#### Ficha de Solicitud INS-03: Licencia SaaS para Pruebas de Carga y Concurrencia

- **Categoría:** Software de QA / Monitoreo.
- **Especificación Técnica:** Plataforma en la nube capaz de ejecutar scripts de pruebas de estrés mediante simulación distribuida de 100 usuarios virtuales concurrentes navegando el visualizador gráfico Canvas/WebGL, midiendo métricas de LCP (Largest Contentful Paint), [[XX-abreviaciones#TTFB|TTFB]] y tasa de refresco en FPS.
- **Cantidad:** 1 Licencia corporativa (período de pruebas de 3 meses).
- **Criterio de Aceptación:** Generación automática de informe telemétrico auditable en [[XX-abreviaciones#PDF|PDF]].
- **Justificación EDT:** Paquete `1.4.2 Reporte de pruebas de integración`.

## 2. Procedimiento y Circuito Operativo del Proceso de Compras (Efectuar las Adquisiciones)

### 2.1. Circuito del Flujo de Compras Paso a Paso

El proceso de adquisición en el proyecto **BioSignal** se rige por un procedimiento administrativo y técnico estructurado en **8 etapas secuenciales**, garantizando transparencia, trazabilidad y libre concurrencia de proveedores. Las etapas 1 a 7 corresponden a la **selección y ejecución de la compra** (_ex-ante_); la etapa 8 corresponde a la **evaluación de desempeño del proveedor** (_ex-post_) y devuelve su resultado a la etapa 4 de las compras futuras a través del Historial de Proveedores (sección 3.3).

```
 [1. Solicitud de Compra]
               │
               ▼
 [2. Emisión de Pliegos de Licitación]
   (Con plazo estricto de cotización: 3-5 días hábiles)
               │
               ▼
 [3. Difusión a Registro/Padrón de Proveedores]
   (Solo proveedores habilitados: no bloqueados y con documentación vigente)
               │
               ▼
 [4. Recepción, Apertura y Evaluación de Ofertas]  ◄──────────────┐
   (Matriz de Ponderación: criterios técnicos, económicos         │
    e HISTORIAL del proveedor como insumo obligatorio)            │
               │                                                  │
               ▼                                                  │
 [5. Adjudicación y Notificación] ──► [Feedback a Oferentes No    │
               │                       Seleccionados]             │
               ▼                                                  │
 [6. Orden de Compra y Entrega del Insumo/Servicio]               │
               │                                                  │
               ▼                                                  │
 [7. Inspección Técnica y Recepción Conformada]                   │
               │                                                  │
               ▼                                                  │
 [8. Evaluación de Desempeño del Proveedor (Ficha Post-Compra)]   │
               │                                                  │
               ▼                                                  │
 [HISTORIAL DE PROVEEDORES (acumulativo)] ────────────────────────┘
   (Insumo de las próximas licitaciones)
```

### 2.2. Detalle Operativo de las Etapas del Circuito

1. **Identificación de Necesidades y Solicitud de Compra (Requisitoria Interna):** El responsable de un paquete de la EDT (ej. Backend, Frontend, QA) completa el formulario interno de Solicitud de Compra adjuntando el **Enunciado del Trabajo Relativo a las Adquisiciones** o Términos de Referencia, detallando las especificaciones de calidad requeridas sin indicar marcas exclusivas. Se marcan además los **requisitos excluyentes** (los que descalifican la oferta si no se cumplen).
2. **Elaboración y Emisión de Documentos de Licitación:** Se redactan los pliegos de bases y condiciones: **Solicitud de Cotización** para productos estandarizados (dominios, VPS) o **Solicitud de Propuesta** para servicios complejos (auditoría Ley 25.326, UI/UX). Los pliegos **declaran los criterios, pesos y escalas objetivas** de evaluación (sección 2.5), los requisitos excluyentes y el uso del historial. Como requisito de dinamismo procesal, se fija un **plazo estricto de presentación de ofertas de 3 a 5 días hábiles**.
3. **Convocatoria al Registro de Proveedores:** El pedido se notifica a las empresas inscriptas en el **Registro/Padrón de Proveedores** de la organización según el rubro correspondiente (Hardware, Software, Consultoría). **Antes de invitar, el APM consulta el Historial de Proveedores:** se excluyen los proveedores en **zona roja** con suspensión vigente y los que tengan documentación impositiva o legal vencida (sección 3.7).
4. **Recepción, Apertura y Evaluación Ponderada de Ofertas:** Cumplido el plazo, se realiza la apertura formal de propuestas. El equipo evaluador encabezado por el [[XX-abreviaciones#PM|PM]] aplica una **Matriz de Selección Multi-criterio**, con escalas cuantitativas (sección 2.5), considerando:
   - _Capacidad Técnica y Adherencia al Enunciado del Trabajo Relativo a las Adquisiciones:_ 35%
   - _Propuesta Económica / Precio:_ 25%
   - _Tiempo de Entrega / Despliegue:_ 15%
   - _Soporte Técnico y Garantía:_ 10%
   - **_Historial de Desempeño del Proveedor_ (insumo obligatorio):** 15%

   Además de la ponderación, se aplica la **regla de demora** (sección 3.3): un proveedor con demora promedio superior a 10 días hábiles en sus últimas 3 entregas queda excluido, aunque su precio sea el menor. Si la oferta supera en más del 20% el precio testigo del insumo (sección 3.3), el proveedor debe justificarlo antes de la adjudicación.

5. **Adjudicación y Retroalimentación:** Se emite el Dictamen de Adjudicación al proveedor ganador. Como pilar de mejora continua remarcado en la materia, se envía, **dentro de los 3 días hábiles posteriores a la adjudicación**, una **notificación formal con feedback técnico a cada proveedor no seleccionado** (modelo en la sección 2.6), indicando su puntaje por criterio y los motivos (ej. precio fuera de rango, tiempos extendidos, soporte insuficiente) para impulsar la competitividad futura.
6. **Emisión de Orden de Compra ([[XX-abreviaciones#OC|OC]]) y Entrega:** Se formaliza la Orden de Compra (simulada en este ejercicio) y el proveedor adjudicado procede a la provisión o habilitación del servicio. La OC fija la **fecha de entrega pactada**, el **precio acordado** y los **criterios de aceptación**, que serán la base de la evaluación posterior.
7. **Inspección Técnica, Recepción Conformada y Cierre Operativo:** El área técnica del proyecto (QA / Infraestructura) realiza las pruebas de homologación. Si el insumo satisface los criterios de aceptación, se firma la **Constancia de Recepción Conformada**, autorizando el pago. La constancia registra la fecha real de entrega y el resultado de cada criterio de aceptación.
8. **Evaluación de Desempeño del Proveedor y Actualización del Historial:** Dentro de los **5 días hábiles posteriores a la recepción conformada**, el dueño del paquete completa la **Ficha de Evaluación Post-Compra** (sección 3.5) con las rúbricas de la sección 3.2. El APM la valida y registra en el **Historial de Proveedores** dentro de los **2 días hábiles siguientes**; ese historial es insumo obligatorio de la etapa 4 de las próximas licitaciones. **El circuito se cierra con la evaluación registrada.**

### 2.3. Tabla de Etapas, Responsables y Registros

El proceso se inicia cuando el paquete de la EDT está aprobado y existe una necesidad con fecha objetivo. Depende de la decisión de alcance y del hito al que pertenece el insumo; no puede cerrarse sin la aceptación técnica de QA ni sin la evaluación post-compra registrada.

| Etapa                             | ¿Qué se hace?                                                                                                 | Responsable                                                | Documento o registro resultante                                           |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------- |
| 1. Identificación de la necesidad | Se completa la requisitoria interna con especificaciones, justificación EDT y requisitos excluyentes.         | Dueño del paquete EDT                                      | Solicitud de compra                                                       |
| 2. Elaboración del pliego         | Se redactan bases, condiciones, criterios, pesos y escalas objetivas.                                         | PM / APM                                                   | Pliego o solicitud de cotización ([[XX-abreviaciones#RFQ\|RFQ]])          |
| 3. Convocatoria                   | Se consulta el historial, se notifica a los proveedores habilitados del rubro y se fija plazo de oferta.      | APM                                                        | Registro de invitaciones y de proveedores excluidos                       |
| 4. Evaluación de ofertas          | Se abre la propuesta y se aplica la matriz de selección, con el historial como criterio y la regla de demora. | PM + revisor técnico                                       | Acta de evaluación                                                        |
| 5. Adjudicación                   | Se emite el dictamen y se envía feedback a los no seleccionados.                                              | PM                                                         | Dictamen de adjudicación y notificaciones de feedback                     |
| 6. Entrega                        | El proveedor entrega o habilita el producto o servicio.                                                       | Proveedor                                                  | Remito o acta de entrega                                                  |
| 7. Recepción y cierre técnico     | Se prueba el insumo y se firma la conformidad.                                                                | QA / Infraestructura                                       | Constancia de recepción conformada                                        |
| 8. Evaluación post-compra         | Se califica el desempeño real del proveedor y se actualiza el historial.                                      | Dueño del paquete EDT (califica) + APM (valida y registra) | Ficha de Evaluación Post-Compra y registro en el Historial de Proveedores |

### 2.4. Simulación Práctica de una Compra

Se simula el proceso de selección competitiva para el insumo **INS-03 (Licencia de Plataforma de Pruebas de Carga y Estrés SaaS)**. La compra es **simulada**: el costo se usa para comparar alternativas, no para ejecutar un pago. Los datos de **historial** de los proveedores son **supuestos del ejercicio**.

#### Datos de la Compra Simulada

- **Objeto:** Licencia SaaS para simulación de 100 usuarios concurrentes en visualizador WebGL.
- **Presupuesto Máximo de Referencia:** $150 USD / trimestre.
- **Plazo de Cotización:** 3 días hábiles.
- **Plazo requerido:** operativo para el hito [[02-acta-de-constitucion#10. Cronograma de Hitos de Aceptación|H6]] (05/02/2027).

#### Cuadro Comparativo de Ofertas Recibidas

Los puntajes se asignan con las escalas objetivas de la sección 2.5.

| Criterio Evaluado                                               | Peso (%) | Proveedor A (LoadMaster Cloud)                 | Proveedor B (StressTester Pro)                    | Proveedor C (QA-Metric SaaS)                |
| --------------------------------------------------------------- | -------- | ---------------------------------------------- | ------------------------------------------------- | ------------------------------------------- |
| **Capacidad Técnica (100 VUs + WebGL + FPS)**                   | 35%      | 5 (cumple 100% de los requisitos)              | 4 (cumple los excluyentes; ≥ 90% de los demás)    | **Descalificado** (no soporta métricas FPS) |
| **Precio Propuesto**                                            | 25%      | $120 USD (80% del presupuesto → 4)             | $90 USD (60% del presupuesto → 5)                 | —                                           |
| **Tiempo de Despliegue / Activación**                           | 15%      | 24 horas (→ 4)                                 | 24 horas (→ 4)                                    | —                                           |
| **Soporte Técnico y [[XX-abreviaciones#SLA\|SLA]] de Atención** | 10%      | 24/7 en español (→ 5)                          | Horario hábil (→ 3)                               | —                                           |
| **Historial de Desempeño**                                      | 15%      | 4.7 (zona verde; 2 compras previas: 4.8 y 4.6) | 3.2 (zona amarilla; demoras de ≈ 20 días hábiles) | —                                           |
| **PUNTAJE PONDERADO TOTAL**                                     | **100%** | **4.56 (GANADOR)**                             | **4.03**                                          | **Descalificado**                           |

Cálculo del Proveedor A: 0,35 × 5 + 0,25 × 4 + 0,15 × 4 + 0,10 × 5 + 0,15 × 4,7 = **4,56**.

**Proveedor C descalificado:** no soporta métricas FPS, requisito excluyente de INS-03 (sección 2.5); no se pondera.

**Regla de demora aplicada:** el Proveedor B ofrece el **precio más bajo**, pero acumula demoras de ≈ 20 días hábiles por entrega (más de 10 hábiles de promedio). Por la regla de la sección 3.3, **queda excluido de la adjudicación** aunque su precio sea el menor. Su puntaje (4.03) ya era inferior al de A: la regla refuerza el resultado y, sobre todo, impide que B quede como alternativa de reemplazo.

**Dictamen de Adjudicación:** Se selecciona al **Proveedor A (LoadMaster Cloud)** con una puntuación de **4.56/5.00** por ofrecer la mejor combinación de capacidad técnica, precio, soporte e historial verificado para gráficos WebGL/Canvas.

#### Condiciones, Riesgo y Seguimiento del Proveedor Seleccionado

| Aspecto        | Condición acordada                                                        |
| -------------- | ------------------------------------------------------------------------- |
| **Precio**     | USD 120 por trimestre, **referencial y simulado**; sin erogación de caja. |
| **Plazo**      | Activación dentro de 24 h desde la orden de compra.                       |
| **Pago**       | Contra aceptación del informe de pruebas; en el ejercicio, pago simulado. |
| **Soporte**    | Canal 24/7 en español y SLA de respuesta < 4 h.                           |
| **Aceptación** | Informe PDF con 100 VUs, métricas de LCP/TTFB/FPS y cero errores 5xx.     |

**Riesgo asociado:** el proveedor no soporta correctamente WebGL o demora la activación. **Prevención:** exigir una demo técnica antes de adjudicar y dejar la cláusula de aceptación por escrito. **Respuesta:** ejecutar las pruebas con k6/JMeter (alternativa open source, sin proveedor externo).

**Seguimiento:** reunión semanal durante la ventana de pruebas y verificación del informe de aceptación. Dentro de los 5 días hábiles posteriores a la recepción conformada se completa la **Ficha de Evaluación Post-Compra** (sección 3.5) y en los 2 días hábiles siguientes se registra en el **Historial de Proveedores**. El ejemplo resuelto de esa evaluación está en la sección 3.6.

### 2.5. Escalas Objetivas de Puntaje para la Selección de Ofertas

Para evitar interpretaciones subjetivas y discusiones con los proveedores, cada criterio de la matriz se califica con un **valor entero de 1 a 5** según escalas cuantitativas publicadas en el pliego. Las escalas reproducen los puntajes de la simulación de la sección 2.4.

| Puntaje | Capacidad técnica (% de requisitos ponderables) | Precio (% del presupuesto máximo) | Plazo de activación / entrega | Soporte y garantía                                |
| ------- | ----------------------------------------------- | --------------------------------- | ----------------------------- | ------------------------------------------------- |
| **5**   | 100%                                            | ≤ 60%                             | ≤ 4 h                         | 24/7 por chat o teléfono, en el idioma del equipo |
| **4**   | ≥ 90% y < 100%                                  | > 60% y ≤ 80%                     | > 4 h y ≤ 24 h                | 24/7 solo por ticket o e-mail                     |
| **3**   | ≥ 75% y < 90%                                   | > 80% y ≤ 90%                     | > 24 h y ≤ 36 h               | Horario hábil con más de un canal                 |
| **2**   | ≥ 50% y < 75%                                   | > 90% y ≤ 100%                    | > 36 h y ≤ 48 h               | Solo e-mail en horario hábil                      |
| **1**   | < 50%                                           | > 100%                            | > 48 h                        | Sin soporte                                       |

Notas de aplicación:

- **Historial:** se usa directamente el promedio de las **últimas 3 evaluaciones post-compra** (escala 1 a 5, o las que tenga si son menos). Un proveedor **sin historial** recibe **3.0** neutro.
- **Requisitos excluyentes:** el pliego declara los que descalifican la oferta si no se cumplen (para INS-03: 100 VUs, WebGL y métricas FPS). Una oferta que incumpla un requisito excluyente queda **descalificada** y no se pondera. Superar el presupuesto máximo no descalifica: recibe el puntaje mínimo de precio.

### 2.6. Modelo de Notificación de Feedback a Oferentes No Seleccionados

Se envía a cada oferente no adjudicado dentro de los 3 días hábiles posteriores al dictamen. **No se divulgan datos comerciales del ganador** (precio ni propuesta); solo el puntaje propio, por criterio, y los motivos. La comunicación se registra en el [[02b-gestion-de-las-comunicaciones|plan de comunicaciones]].

> **Asunto:** Resultado de la convocatoria INS-03 – Licencia SaaS de pruebas de carga
>
> Estimados [Proveedor]:
>
> Agradecemos su participación. Les informamos que su oferta **no resultó adjudicada**. Su puntaje ponderado fue de **[X] / 5,00**.
>
> **Detalle por criterio:**
>
> - Capacidad técnica (35%): [puntaje] — [motivo, ej. cobertura del 90% de los requisitos].
> - Precio (25%): [puntaje] — [motivo].
> - Plazo de activación (15%): [puntaje] — [motivo, ej. activación en 24 h].
> - Soporte (10%): [puntaje] — [motivo, ej. cobertura en horario hábil, sin atención 24/7].
> - Historial (15%): [puntaje] — [motivo, ej. demoras registradas en entregas anteriores].
>
> **Oportunidades de mejora para futuras convocatorias:** [lista breve].
>
> Quedamos a disposición para ampliar esta devolución.
>
> Equipo de Adquisiciones – BioSignal

## 3. Sistema de Evaluación de Desempeño de Proveedores

### 3.1. Distinción Metodológica Clave

- **Selección de Ofertas (_ex-ante_):** Proceso de comparación de presupuestos y propuestas _antes de comprar_ para elegir al proveedor adjudicado.
- **Evaluación de Desempeño (_ex-post_):** Auditoría de calidad _posterior a la entrega_ que califica el comportamiento real del proveedor durante la ejecución del contrato.

|                           | Selección de ofertas (_ex-ante_)                   | Evaluación de desempeño (_ex-post_)                                    |
| ------------------------- | -------------------------------------------------- | ---------------------------------------------------------------------- |
| **Momento**               | Antes de comprar (etapa 4)                         | Después de la entrega (etapa 8)                                        |
| **Pregunta que responde** | ¿Qué oferta conviene?                              | ¿El proveedor cumplió lo pactado?                                      |
| **Base de comparación**   | Ofertas frente al enunciado y entre sí             | Entrega real frente a la Orden de Compra y los criterios de aceptación |
| **Resultado**             | Dictamen de adjudicación                           | Ficha de evaluación y actualización del historial                      |
| **Relación entre ambas**  | **Consume** el historial como criterio obligatorio | **Produce** el historial                                               |

```
   SELECCIÓN (ex-ante) ──► COMPRA Y ENTREGA ──► EVALUACIÓN (ex-post)
          ▲                                              │
          │                                              ▼
          └───────────── HISTORIAL DE PROVEEDORES ◄──────┘
```

### 3.2. Criterios de Calificación Post-Compra y Termómetro de Desempeño

Finalizada la entrega del producto o servicio, el responsable del paquete de trabajo completa la Ficha de Evaluación Post-Compra ponderando 4 dimensiones en una escala de 1 a 5 estrellas. Cada dimensión se califica con **datos medibles** obtenidos de documentos del proceso, no por impresión:

1. **Puntualidad en la Entrega (30%):** Cumplimiento del plazo estipulado en la Orden de Compra. _Fuente:_ OC y acta de entrega.
2. **Calidad Técnica y Ajuste (40%):** Cumplimiento de los criterios de aceptación definidos en la OC. _Fuente:_ Constancia de recepción conformada y checklist de QA.
3. **Atención y Soporte Post-Venta (15%):** Respuestas dentro del SLA acordado. _Fuente:_ sistema de tickets con marcas de tiempo.
4. **Cumplimiento Presupuestario (15%):** Diferencia entre el precio pactado y el facturado. _Fuente:_ OC y factura.

#### Rúbrica cuantitativa

| Estrellas | Puntualidad (30%)                | Calidad técnica (40%)               | Soporte post-venta (15%)              | Cumplimiento presupuestario (15%) |
| --------- | -------------------------------- | ----------------------------------- | ------------------------------------- | --------------------------------- |
| **5**     | Entrega en fecha o antes         | 100% de los criterios de aceptación | 100% de las respuestas dentro del SLA | 0% de sobrecosto                  |
| **4**     | 1 a 2 días hábiles de demora     | ≥ 90% y < 100%                      | ≥ 90% y < 100%                        | > 0% y ≤ 2%                       |
| **3**     | 3 a 5 días hábiles de demora     | ≥ 75% y < 90%                       | ≥ 75% y < 90%                         | > 2% y ≤ 5%                       |
| **2**     | 6 a 10 días hábiles de demora    | ≥ 50% y < 75%                       | ≥ 50% y < 75%                         | > 5% y ≤ 10%                      |
| **1**     | Más de 10 días hábiles de demora | < 50%                               | < 50%                                 | > 10%                             |

#### Fórmula

**Puntaje final = 0,30 × Puntualidad + 0,40 × Calidad + 0,15 × Soporte + 0,15 × Presupuesto**

#### Clasificación por Termómetro de Desempeño

La **zona de un proveedor** se determina por el **promedio de sus últimas 3 evaluaciones** (historial acumulado). Cada evaluación individual también se clasifica, a modo informativo.

- **Rango Verde (≥ 4.5 y ≤ 5.0 estrellas) — Proveedor Preferente / Aliado Estratégico:** prioridad en nuevas licitaciones y seguimiento estándar.
- **Rango Amarillo (≥ 3.0 y < 4.5 estrellas) — Proveedor Aceptable en Observación:** Mantiene su inscripción activa y participa de las convocatorias, pero su historial incide en la selección y requiere seguimiento estricto (por ejemplo, cláusulas de plazo por escrito).
- **Rango Rojo (< 3.0 estrellas) — Proveedor Sancionado / Bloqueado:** Penalización con suspensión del padrón según las reglas de la sección 3.7.

Un proveedor sin evaluaciones no tiene zona hasta su primera evaluación post-compra.

```
 [1.0 ────────────── < 3.0) ─────── [3.0 ────────────── < 4.5) ─────── [4.5 ────────────── 5.0]
     ZONA ROJA (Bloqueado)            ZONA AMARILLA (Observación)         ZONA VERDE (Preferente)
```

### 3.3. Historial de Proveedores y Precios Testigo

Las calificaciones _ex post_ se alimentan en una **base de datos centralizada de adquisiciones** (Historial de Proveedores). Por cada compra evaluada se registra:

| Campo              | Contenido                                                     |
| ------------------ | ------------------------------------------------------------- |
| Proveedor e insumo | Identificación del proveedor, ítem (INS-xx) y número de OC    |
| Fechas             | Fecha de entrega pactada y fecha real; demora en días hábiles |
| Puntajes           | Estrellas por dimensión, puntaje final y zona del termómetro  |
| Desvíos            | Sobrecosto (%) y observaciones de calidad o soporte           |
| Precio pagado      | Monto abonado (precio testigo)                                |
| Documentación      | Vencimientos de certificados fiscales y comerciales           |

#### Uso del historial como insumo obligatorio de la selección

El historial **interviene en cada licitación** mediante tres reglas:

1. **Regla de habilitación (etapa 3):** solo se invita a proveedores no bloqueados y con documentación vigente.
2. **Regla de ponderación (etapa 4):** el promedio de las últimas 3 evaluaciones del proveedor se incorpora a la matriz como criterio con **peso del 15%**. Un proveedor sin historial recibe 3.0 (neutro).
3. **Regla de demora (etapa 4):** si el proveedor acumula una **demora promedio superior a 10 días hábiles** en sus últimas 3 entregas, **queda excluido de la adjudicación**, aunque presente el precio más bajo. Como todos los insumos de la matriz tienen fecha atada a un hito, la regla se aplica a todas las compras.

_Ejemplo:_ un proveedor ofrece el menor precio, pero acumula demoras de 20 días hábiles por entrega; la regla 3 lo descarta y la regla 2 ya lo había penalizado en el puntaje.

#### Otros beneficios operativos del historial

- **Precios testigo:** guarda el monto abonado por insumo; una oferta que supere en más del 20% ese precio testigo exige justificación del proveedor antes de la adjudicación.
- **Control de Documentación Impositiva y Legal:** Alerta automáticamente sobre vencimientos de certificados fiscales o comerciales del proveedor, bloqueando su participación si no mantiene la documentación al día.

### 3.4. Procedimiento de Evaluación Post-Compra

| Paso                        | Qué se hace                                                                                                                                                                                                                  | Responsable                | Plazo                               |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- | ----------------------------------- |
| 1. Disparador               | La firma de la Constancia de Recepción Conformada (etapa 7) inicia la evaluación.                                                                                                                                            | Dueño del paquete EDT      | Al recibir                          |
| 2. Recolección de evidencia | Se reúnen la OC, el acta de entrega, el checklist de QA, los tickets de soporte y la factura.                                                                                                                                | Dueño del paquete EDT + QA | ≤ 3 días hábiles                    |
| 3. Calificación             | Se completa la Ficha de Evaluación Post-Compra aplicando la rúbrica y la fórmula de la sección 3.2.                                                                                                                          | Dueño del paquete EDT      | ≤ 5 días hábiles desde la recepción |
| 4. Validación               | El APM revisa que cada puntaje esté respaldado por evidencia y que el cálculo sea correcto.                                                                                                                                  | APM                        | ≤ 2 días hábiles                    |
| 5. Registro                 | Se carga la evaluación en el Historial de Proveedores y se recalcula el promedio de las últimas 3 evaluaciones y la zona.                                                                                                    | APM                        | Inmediato                           |
| 6. Comunicación             | Se informa al proveedor su puntaje por dimensión. Dispone de **5 días hábiles** para presentar descargo.                                                                                                                     | PM / APM                   | ≤ 3 días hábiles                    |
| 7. Acciones                 | Si hay desvíos, se registra el reclamo o la corrección solicitada. Si la zona resultante es roja, el PM aplica la sección 3.7 **vencido el plazo de descargo**; si el descargo prospera, se corrige la ficha y el historial. | PM                         | Según corresponda                   |

La evaluación califica la **ejecución real del contrato** (entrega frente a lo pactado en la OC), no la oferta presentada.

### 3.5. Ficha de Evaluación Post-Compra (Modelo)

| Campo                         | Valor  |
| ----------------------------- | ------ |
| Proveedor                     |        |
| Insumo / Ítem                 | INS-xx |
| Nº de Orden de Compra         |        |
| Responsable de la evaluación  |        |
| Fecha de recepción conformada |        |

| Dimensión                   | Peso | Dato medido                       | Pactado / esperado | Estrellas (1-5) | Aporte ponderado |
| --------------------------- | ---- | --------------------------------- | ------------------ | --------------- | ---------------- |
| Puntualidad                 | 30%  | Fecha real de entrega             | Fecha de la OC     |                 |                  |
| Calidad técnica             | 40%  | Criterios de aceptación cumplidos | Total de criterios |                 |                  |
| Soporte post-venta          | 15%  | Respuestas dentro del SLA         | Total de consultas |                 |                  |
| Cumplimiento presupuestario | 15%  | Monto facturado                   | Monto de la OC     |                 |                  |
| **Puntaje final**           | 100% |                                   |                    |                 | **/ 5,00**       |

| Resultado                                           | Valor                   |
| --------------------------------------------------- | ----------------------- |
| Zona de la evaluación (informativa)                 | Verde / Amarillo / Rojo |
| Promedio acumulado (últimas 3) y zona del proveedor |                         |
| Desvíos detectados y acción tomada                  |                         |
| Descargo del proveedor y resolución (si hubo)       |                         |
| Validación del APM (fecha y firma)                  |                         |

### 3.6. Ejemplo Resuelto: Evaluación Post-Compra de LoadMaster Cloud (INS-03)

_Datos simulados del ejercicio, a continuación de la compra de la sección 2.4._

| Dimensión                   | Peso | Dato medido                                                                                              | Pactado            | Estrellas | Aporte ponderado |
| --------------------------- | ---- | -------------------------------------------------------------------------------------------------------- | ------------------ | --------- | ---------------- |
| Puntualidad                 | 30%  | Activación en 3 días hábiles (2 días de demora)                                                          | 1 día hábil (24 h) | 4         | 1,20             |
| Calidad técnica             | 40%  | 4 de 4 criterios de aceptación cumplidos (informe PDF, 100 VUs, métricas LCP/TTFB/FPS, cero errores 5xx) | 4 criterios        | 5         | 2,00             |
| Soporte post-venta          | 15%  | 4 de 5 consultas respondidas en menos de 4 h (80%)                                                       | SLA < 4 h          | 3         | 0,45             |
| Cumplimiento presupuestario | 15%  | USD 120 facturados (0% de sobrecosto)                                                                    | USD 120            | 5         | 0,75             |
| **Puntaje final**           | 100% |                                                                                                          |                    |           | **4,40 / 5,00**  |

**Lectura del resultado:**

- La evaluación individual es **4,40**, en zona **amarilla**, cerca del límite superior. Los descuentos provienen de 2 días de demora en la activación y de una consulta respondida fuera del SLA.
- **Actualización del historial:** el proveedor tenía dos evaluaciones previas (4,8 y 4,6). Su nuevo promedio de las últimas 3 es (4,8 + 4,6 + 4,4) ÷ 3 = **4,60**, lo que lo mantiene en **zona verde**.
- **Acción registrada:** se comunica el resultado al proveedor y se solicita refuerzo del soporte para una eventual renovación. Este promedio de 4,60 será su puntaje de historial en la próxima licitación.

### 3.7. Sanción y Bloqueo de Proveedores

La sanción se basa en el **promedio acumulado de las últimas 3 evaluaciones**, para que un solo resultado aislado no decida la suspensión, salvo incumplimiento grave.

| Situación                                                                                         | Consecuencia                               |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| Promedio acumulado **< 3,0** (zona roja) por primera vez                                          | Suspensión del padrón por **3 meses**      |
| **Reincidencia:** el proveedor vuelve a zona roja tras reingresar                                 | Suspensión por **12 meses**                |
| **Incumplimiento grave:** entrega no realizada, evaluación individual < 2,0 o falsedad documental | **Baja definitiva** del registro           |
| Documentación impositiva o legal vencida                                                          | Bloqueo automático hasta su regularización |

- **Descargo:** el proveedor puede presentarlo dentro de los 5 días hábiles de comunicada la evaluación; el PM resuelve y registra la decisión dentro de los 5 días hábiles siguientes.
- **Reingreso:** al vencer la suspensión, el proveedor vuelve al padrón con **3.0 neutro** y su primera compra queda bajo seguimiento reforzado. Las evaluaciones anteriores se conservan como antecedente, pero **no entran en el promedio**: este se reinicia con la primera evaluación posterior al reingreso.

## 4. Acuerdo de Nivel de Servicio

### 4.1. Propósito y Aplicabilidad en BioSignal

En proyectos como BioSignal, donde la infraestructura principal de servidores y conectividad no se adquiere en el mercado abierto sino que es provista por un **sponsor institucional (UNViMe)** a costo directo $0 USD, resulta indispensable formalizar un **Acuerdo de Nivel de Servicio (SLA)** para garantizar los estándares técnicos requeridos por el alcance del software.

### 4.2. Matriz de Especificaciones y Métricas del SLA con UNViMe

| Dimensión Técnica                          | Parámetro / Métrica Garantizada                                                                                                   | Método de Medición / Verificación                                         | Penalidad o Plan de Contingencia ante Incumplimiento                                      |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Disponibilidad del Servidor (_Uptime_)** | **≥ 99.9% mensual** (máximo 60 minutos de parada no programada al mes).                                                           | Monitoreo continuo mediante ping/HTTP health-check cada 20 minutos.       | Reubicación inmediata del servicio al Servidor VPS de Reserva Failover (INS-01).          |
| **Capacidad de Cómputo Asignada**          | 4 vCPUs dedicados, 8 GB RAM DDR4, 100 GB almacenamiento SSD NVMe.                                                                 | Telemetría de consumo de recursos en panel de control del servidor.       | Escalado vertical provisional.                                                            |
| **Ancho de Banda y Conectividad**          | Conexión simétrica de **≥ 10 Mbps sostenidos** con latencia < 50 ms.                                                              | Benchmark periódico de velocidad de red y tiempo TTFB.                    | Redirección de tráfico mediante [[XX-abreviaciones#CDN\|CDN]] / proxy inverso externo.    |
| **Rendimiento de Ingesta (.EDF)**          | Procesamiento y validación binaria de cabecera **≤ 30 segundos** para archivos < 50 MB.                                           | Logs de auditoría de tiempo de ejecución en backend.                      | Optimización de hilos de ejecución y procesamiento asincrónico.                           |
| **Tiempo de Respuesta a Incidentes**       | Respuesta técnica inicial **< 2 horas** ante caídas críticas de servidor (24/7).                                                  | Sistema de tickets con marcas de tiempo automáticas.                      | Escalado directo de soporte a la Dirección de [[XX-abreviaciones#TIC\|TIC]] de la UNViMe. |
| **Respaldos de Seguridad (_Backups_)**     | Copia de seguridad **diaria automatizada** de base de datos y archivos .edf con retención de 30 días; **RTO ≤ 4 h y RPO ≤ 24 h**. | Script de verificación de integridad y restauración semanal automatizada. | Generación manual inmediata de snapshot de base de datos.                                 |

## 5. Registro de Cambios

| Versión | Fecha      | Cambio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Responsable | Estado    |
| ------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | --------- |
| v1.0    | —          | Versión inicial: análisis hacer/comprar, matriz de insumos, fichas de compra, circuito de adquisiciones, evaluación de proveedores y SLA con UNViMe                                                                                                                                                                                                                                                                                                                                    | PM          | Histórico |
| v1.1    | 12/11/2026 | Matriz de insumos y fichas conciliadas con ERS y EDT; referencias y abreviaciones normalizadas; registro de cambios incorporado. Tramitado como **RFC-015** en el [[09-gestion-y-control-de-cambios\|Change Log]]                                                                                                                                                                                                                                                                      | PM + APM    | Aprobado  |
| v1.2    | 23/11/2026 | Corrección tras la devolución del TP 8: se completa la **evaluación de desempeño** como etapa 8 (ex-post) y se separa de la selección (ex-ante); el **historial de proveedores** pasa a ser insumo obligatorio (15% + regla de demora); escalas enteras de 1 a 5 con requisitos excluyentes, ficha y ejemplo de evaluación, termómetro con rangos continuos, sanciones y feedback a no seleccionados. Tramitado como **RFC-017** en el [[09-gestion-y-control-de-cambios\|Change Log]] | PM + APM    | Propuesto |
