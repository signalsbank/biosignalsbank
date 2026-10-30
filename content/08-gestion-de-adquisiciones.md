---
aliases:
  - Gestión de Adquisiciones
title: 8. Gestión de Asquisiciones
project: Banco de Señales Biomédicas ("BioSignalsBank")
version: 1
---

## 1. Lista de Insumos y Productos a Comprar (Análisis de Hacer o Comprar)

### 1.1. Contexto Metodológico y Restricción Financiera

Aunque el proyecto **BioSignal** opera bajo una restricción formal de **$0 USD de costo directo recurrente** en infraestructura comercial por sustentarse en los servidores institucionales de la **Universidad Nacional de Villa Mercedes (UNViMe)**, se detallan los insumos, licencias, servicios profesionales, equipamiento y conjuntos de datos requeridos para la ejecución, aseguramiento de la calidad y contingencia del sistema.

### 1.2. Matriz Consolidada de Insumos y Productos

|    Ítem    | Nombre del Insumo / Producto                                   | Categoría               | Especificaciones Técnicas y Criterios de Calidad Requeridos                                                                       |                     Paquete de Trabajo EDT / Req. Asociado                     | Justificación Técnica en BioSignal                                                                                      |
| :--------: | :------------------------------------------------------------- | :---------------------- | :-------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------- |
| **INS-01** | **Servidor VPS / Cloud de Reserva (Failover)**                 | Hardware / Hosting      | Instancia virtual de cómputo Linux (4 vCPUs, 8 GB RAM, 100 GB SSD NVMe, red ≥ 10 Mbps, soporte Docker, uptime 99.9%).             |    `1.2.1 Servidores y base de datos configurados`<br>([RNF-01], [RNF-02])     | Garantizar la alta disponibilidad y contingencia ante mantenimientos o caídas de la infraestructura local de la UNViMe. |
| **INS-02** | **Registro de Nombre de Dominio Web Dedicado**                 | Dominio / Red           | Dominio TLD de segundo/tercer nivel (.org / .com.ar) con soporte DNS dinámico, registros CNAME/A y privacidad WHOIS.              |   `1.5 Sistema desplegado en ambiente de producción`<br>([RT-02], [RNF-06])    | Asegurar acceso web público de respaldo si se demorase la delegación del subdominio `*.unvime.edu.ar`.                  |
| **INS-03** | **Licencia de Plataforma de Pruebas de Carga y Estrés (SaaS)** | Software / QA           | Plan SaaS para simulación de concurrencia masiva (≥ 100 VUs - Virtual Users simultáneos) con métricas de latencia LCP y tasa FPS. | `1.4.2 Reporte de pruebas de integración y aceptación`<br>([RNF-01], [RNF-02]) | Certificar objetivamente la capacidad operativa de 100 usuarios simultáneos y LCP ≤ 2,5 s sin degradación.              |
| **INS-05** | **Servicio de Auditoría de Seguridad y Anonimización**         | Servicios Profesionales | Servicio de auditoría forense binaria sobre cabeceras .edf/.edf+ con dictamen normativo Ley 25.326.                               |       `1.3.2.1 Formulario y procesador de carga`<br>([RF-06], [RNF-05])        | Auditar la eliminación 100% irreversible de datos personales de pacientes en cumplimiento legal estricto.               |
| **INS-08** | **Bolsa de Créditos/Tokens de API de Procesamiento e IA**      | Software / AI           | Créditos/tokens para servicio de IA/LLM enfocado en extracción automática de metadatos clínicos e indexación de patologías.       |            `1.3.2.2 Interfaz de edición de metadatos`<br>([RF-07])             | Asistir al administrador en la sugerencia y etiquetado automático de patologías durante la ingesta.                     |

### 1.3. Fichas de Solicitud de Compra para Insumos Clave

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

## 2. Procedimiento y Circuito Operativo del Proceso de Compras (Efectuar las Adquisiciones)

### 2.1. Circuito Flujo de Compras Paso a Paso

El proceso de adquisición en el proyecto **BioSignal** se rige por un procedimiento administrativo y técnico estructurado en 7 etapas secuenciales, garantizando transparencia, trazabilidad y libre concurrencia de proveedores:

```
 [1. Solicitud de Compra]
               │
               ▼
 [2. Emisión de Pliegos de Licitación]
   (Con plazo estricto de cotización: 3-5 días hábiles)
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
 [6. Orden de Compra y Entrega del Insumo/Servicio]
               │
               ▼
 [7. Inspección Técnica y Recepción Conformada]
```

### 2.2. Detalle Operativo de las Etapas del Circuito

1. **Identificación de Necesidades y Solicitud de Compra (Requisitoria Interna):**
   El responsable de un paquete de la EDT (ej. Backend, Frontend, QA) completa el formulario interno de Solicitud de Compra adjuntando el **Enunciado del Trabajo Relativo a las Adquisiciones** o Términos de Referencia, detallando las especificaciones de calidad requeridas sin indicar marcas exclusivas.
2. **Elaboración y Emisión de Documentos de Licitación:**
   Se redactan los pliegos de bases y condiciones: **Solicitud de Cotización** para productos estandarizados (dominios, VPS) o **Solicitud de Propuesta** para servicios complejos (auditoría Ley 25.326, UI/UX). Como requisito de dinamismo procesal, se fija un **plazo estricto de presentación de ofertas de 3 a 5 días hábiles**.
3. **Convocatoria al Registro de Proveedores:**
   El pedido se notifica a las empresas inscriptas en el **Registro/Padrón de Proveedores** de la organización según el rubro correspondiente (Hardware, Software, Consultoría).
4. **Recepción, Apertura y Evaluación Ponderada de Ofertas:**
   Cumplido el plazo, se realiza la apertura formal de propuestas. El equipo evaluador encabezado por el PM aplica una **Matriz de Selección Multi-criterio** considerando:
   - _Capacidad Técnica y Adherencia al Enunciado del Trabajo Relativo a las Adquisiciones:_ 40%
   - _Propuesta Económica / Precio:_ 30%
   - _Tiempo de Entrega / Despliegue:_ 20%
   - _Soporte Técnico y Garantía:_ 10%
5. **Adjudicación, Firma de Contrato y Retroalimentación:**
   Se emite el Dictamen de Adjudicación al proveedor ganador. Como pilar de mejora continua remarcado en la materia, se envía una **notificación formal con feedback técnico a los proveedores no seleccionados**, indicando los motivos (ej. precio fuera de rango, tiempos extendidos) para impulsar la competitividad futura.
6. **Emisión de Orden de Compra (OC) y Entrega:**
   Se formaliza la Orden de Compra de compromiso financiero y el proveedor adjudicado procede a la provisión o habilitación del servicio.
7. **Inspección Técnica, Recepción Conformada y Cierre Operativo:**
   El área técnica del proyecto (QA / Infraestructura) realiza las pruebas de homologación. Si el insumo satisface los criterios de aceptación, se firma la **Constancia de Recepción Conformada**, autorizando el pago y cerrando el circuito de compra.

### 2.3. Simulación Práctica de una Compra Real

Se simula el proceso de selección competitiva para el insumo **INS-03 (Licencia de Plataforma de Pruebas de Carga y Estrés SaaS)**:

#### Datos de la Compra Simula

- **Objeto:** Licencia SaaS para simulación de 100 usuarios concurrentes en visualizador WebGL.
- **Presupuesto Máximo de Referencia:** $150 USD / trimestre.
- **Plazo de Cotización:** 3 días hábiles.

#### Cuadro Comparativo de Ofertas Recibidas

| Criterio Evaluado                       | Peso (%) | Proveedor A (LoadMaster Cloud) |    Proveedor B (StressTester Pro)    | Proveedor C (QA-Metric SaaS)  |
| :-------------------------------------- | :------: | :----------------------------: | :----------------------------------: | :---------------------------: |
| **Capacidad Técnica (100 VUs + WebGL)** |   40%    |       5.0 (Cumple 100%)        | 4.0 (Soporta Canvas, WebGL limitado) | 2.0 (No soporta métricas FPS) |
| **Precio Propuesto**                    |   30%    |     $120 USD (Score: 4.5)      |         $90 USD (Score: 5.0)         |     $140 USD (Score: 3.0)     |
| **Tiempo de Despliegue / Activación**   |   20%    |     Inmediata (Score: 5.0)     |        24 horas (Score: 4.0)         |     48 horas (Score: 2.0)     |
| **Soporte Técnico y SLA de Atención**   |   10%    |  24/7 en español (Score: 5.0)  |      Horario hábil (Score: 3.0)      |   Solo e-mail (Score: 2.0)    |
| **PUNTAJE PONDERADO TOTAL**             | **100%** |       **4.85 (GANADOR)**       |               **4.20**               |           **2.30**            |

**Dictamen de Adjudicación:** Se selecciona al **Proveedor A (LoadMaster Cloud)** con una puntuación de **4.85/5.00** por ofrecer la mejor relación calidad-precio y soporte integral para gráficos WebGL/Canvas.

## 3. Sistema de Evaluación de Desempeño de Proveedores

### 3.1. Distinción Metodológica Clave

- **Selección de Ofertas:** Proceso de comparación de presupuestos y propuestas _antes de comprar_ para elegir al proveedor adjudicado.
- **Evaluación de Desempeño:** Auditoría de calidad _posterior a la entrega_ que califica el comportamiento real del proveedor durante la ejecución del contrato.

### 3.2. Criterios de Calificación Post-Compra y Termómetro de Desempeño

Finalizada la entrega del producto o servicio, el responsable del paquete de trabajo completa la Ficha de Evaluación Post-Compra ponderando 4 dimensiones en una escala de 1 a 5 estrellas:

1. **Puntualidad en la Entrega (30%):** Cumplimiento exacto del plazo estipulado en la Orden de Compra.
2. **Calidad Técnica y Ajuste (40%):** Ausencia de fallas, estabilidad y rendimiento del producto/servicio.
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

## 4. Acuerdo de Nivel de Servicio

### 4.1. Propósito y Aplicabilidad en BioSignal

En proyectos como BioSignal, donde la infraestructura principal de servidores y conectividad no se adquiere en el mercado abierto sino que es provista por un **sponsor institucional (UNViMe)** a costo directo $0 USD, resulta indispensable formalizar un **Acuerdo de Nivel de Servicio (SLA)** para garantizar los estándares técnicos requeridos por el alcance del software.

### 4.2. Matriz de Especificaciones y Métricas del SLA con UNViMe

| Dimensión Técnica                          | Parámetro / Métrica Garantizada                                                                       | Método de Medición / Verificación                                         | Penalidad o Plan de Contingencia ante Incumplimiento                             |
| :----------------------------------------- | :---------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------ | :------------------------------------------------------------------------------- |
| **Disponibilidad del Servidor (_Uptime_)** | **≥ 99.9% mensual** (máximo 60 minutos de parada no programada al mes).                               | Monitoreo continuo mediante ping/HTTP health-check cada 20 minutos.       | Reubicación inmediata del servicio al Servidor VPS de Reserva Failover (INS-01). |
| **Capacidad de Cómputo Asignada**          | 4 vCPUs dedicados, 8 GB RAM DDR4, 100 GB almacenamiento SSD NVMe.                                     | Telemetría de consumo de recursos en panel de control del servidor.       | Escalado vertical provisional.                                                   |
| **Ancho de Banda y Conectividad**          | Conexión simétrica de **≥ 10 Mbps sostenidos** con latencia < 50 ms.                                  | Benchmark periódico de velocidad de red y tiempo TTFB.                    | Redirección de tráfico mediante CDN / proxy inverso externo.                     |
| **Rendimiento de Ingesta (.EDF)**          | Procesamiento y validación binaria de cabecera **≤ 30 segundos** para archivos < 50 MB.               | Logs de auditoría de tiempo de ejecución en backend.                      | Optimización de hilos de ejecución y procesamiento asincrónico.                  |
| **Tiempo de Respuesta a Incidentes**       | Respuesta técnica inicial **< 2 horas** ante caídas críticas de servidor (24/7).                      | Sistema de tickets con marcas de tiempo automáticas.                      | Escalado directo de soporte a la Dirección de TIC de la UNViMe.                  |
| **Respaldos de Seguridad (_Backups_)**     | Copia de seguridad **diaria automatizada** de base de datos y archivos .edf con retención de 30 días. | Script de verificación de integridad y restauración semanal automatizada. | Generación manual inmediata de snapshot de base de datos.                        |
