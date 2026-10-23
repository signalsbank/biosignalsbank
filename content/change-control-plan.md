---
project: Banco de Señales Biomédicas ("BioSignalsBank")
version: 1
title: 11. Plan de Gestión de la Configuración y Control de Cambios
aliases: Plan de Gestión de la Configuración y Control de Cambios
---

## 1. Marco General del Plan de Gestión de la Configuración (SCM)

### 1.1. Propósito y Objetivos del Plan

El presente documento define la gobernanza, procedimientos y herramientas para identificar, versionar, rastrear y controlar todas las modificaciones sobre los artefactos del proyecto **BioSignal**.

Los objetivos principales de este plan son:

1. **Garantizar la Integridad y Consistencia:** Evitar alteraciones no autorizadas en la documentación, código fuente, base de datos e interfaz gráfica.
2. **Prevenir la Corrupción del Alcance:** Asegurar que todo cambio introducido responda a una necesidad justificada, evaluada y aprobada formalmente.
3. **Asegurar la Trazabilidad Bidireccional:** Vincular cada cambio de código, esquema o diseño visual con su correspondiente requerimiento, historia de usuario o solicitud formal.
4. **Disponer de Mecanismos de Reversión (_Rollback_):** Garantizar la capacidad operativa de desestimar un cambio o restaurar una versión estable previa ante contingencias técnicas.

### 1.2. Alcance y Elementos de Configuración (_Configuration Items - CIs_)

El Plan de Gestión de la Configuración abarca la totalidad del ciclo de vida del proyecto BioSignal e identifica cuatro grandes categorías de Elementos de Configuración (CIs):

- **CI-DOC (Documentación Procesal y de Proyecto):** Actas, pliegos, especificaciones en formato `.md`, manuales, EDT y matriz de trazabilidad.
- **CI-CODE (Código Fuente y Scripts):** Repositorios de Frontend (React/TypeScript), Backend (Node.js/Python), pipelines de CI/CD y scripts de despliegue.
- **CI-DATA (Estructura de Base de Datos):** Modelo relacional PostgreSQL, archivos DDL, funciones almacenadas, vistas y scripts de migración/rollback.
- **CI-UI (Interfaz de Usuario y UX):** Prototipos gráficos, maquetas en Figma, kits de componentes visuales y hojas de estilo.

### 1.3. Matriz de Roles y Niveles de Autorización

El control de cambios se organiza mediante niveles de responsabilidad para evitar decisiones unilaterales:

| Rol SCM                                            | Integrante(s) Asignado(s)                                       | Función y Dominio de Autoridad                                                                                                   |
| :------------------------------------------------- | :-------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| **Comité de Control de Cambios (CCB) / PM**        | Astudillo, Mateo T. (PM) / Ávila Gelbes, Ignacio (Asistente PM) | Evaluación de impacto global, aprobación/rechazo de cambios en líneas base de costo, tiempo o alcance, y firma de publicaciones. |
| **Dueño del Proceso Documental (_Process Owner_)** | Ávila Gelbes, Ignacio N.                                        | Revisión de coherencia metodológica, formato y custodia de la documentación publicada.                                           |
| **Revisor Legal / Normativo**                      | Equipo PM / Asesoría UNViMe                                     | Verificación de cumplimiento normativo (Ley 25.326 de Protección de Datos Personales y reglamentos UNViMe).                      |
| **Líder de Código y QA**                           | Herrera, Germán E.                                              | Revisión cruzada de Pull Requests (PRs), aprobación de merge a ramas de desarrollo y certificación de pruebas.                   |
| **Líder de Infraestructura y Base de Datos**       | Chiecher, Eber B.                                               | Aprobación y ejecución de migraciones DDL, scripts de rollback y gestión de ambientes de servidor.                               |
| **Líder de Frontend y UI/UX**                      | Pereyra, Rocío / Mosainer, Martín D.                            | Versionado de prototipos Figma, revisión de maquetado adaptativo y cumplimiento de guías de estilo visual.                       |

### 1.4. Flujo Operativo del Control Integrado de Cambios

Todo cambio en el proyecto debe seguir el siguiente circuito secuencial:

```
[1. Identificación y Solicitud de Cambio]
       │
       ▼
[2. Evaluación de Impacto Técnico, Costo y Tiempo]
       │
       ▼
[3. Revisión por el Dueño del Proceso / Experto Técnico]
       │
       ▼
[4. Dictamen del Comité (Aprobado / Rechazado / Aplazado)]
       │
       ▼
[5. Implementación en Entorno de Pruebas]
       │
       ▼
[6. Verificación de QA / Inspección Cruzada]
       │
       ▼
[7. Publicación en Producción y Actualización del Change Log]
```

---

## 2. Control de Cambios Documental y Procesal

### 2.1. Alcance de la Documentación

Esto comprende todos los documentos vivos del proyecto y para los documentos estáticos (como el acta de constitución) se requiere una reunión directa con el patrocinador del proyecto y una aprobación con los integrantes del proyecto.
### 2.2. Roles y Flujo de Aprobación Documental

1. **Elaboración:** El integrante responsable redacta la modificación propuesta sobre el archivo `.md`.
2. **Revisión Técnica por el Dueño del Proceso (_Process Owner_):** El integrante con mayor conocimiento del área (ej. el responsable de arquitectura para el documento de infraestructura, o el Asistente del PM para comunicaciones) revisa la pertinencia del contenido.
3. **Revisión Legal / Normativa:** Si el documento involucra el tratamiento de información, se audita que no incumpla la Ley 25.326 de Protección de Datos Personales ni resoluciones de la UNViMe.
4. **Aprobación y Firma:** El Director del Proyecto (Mateo Astudillo) da el visto bueno formal.

### 2.3. Criterio de Publicación y Vigencia

- **Regla de Oro Documental:** La única versión válida y vigente de un documento o instructivo es aquella que se encuentra oficialmente publicada en el repositorio central del proyecto (`/workspace/knowledge/` o la rama `main` del repositorio de documentación).
- Al publicarse una versión nueva (ej. `v2.0`), las versiones anteriores quedan automáticamente derogadas pero se conservan archivadas en el historial de Git a fines de auditoría.

### 2.4. Nomenclatura y Regla de Versionado Documental

Los documentos utilizan versionado numérico explícito en el encabezado y en el historial de cambios:

- **Versiones Borrador / En Revisión:** `v0.1`, `v0.2`, `v0.9` (cambios internos de redacción).
- **Versiones Oficiales / Aprobadas:** `v1.0`, `v2.0` (versión formalmente aprobada por el PM).
- **Versiones de Corrección Menor:** `v1.1`, `v1.2` (ajustes tipográficos, ortográficos o aclaraciones menores sin cambio de alcance).

---

## 3. Seguimiento, Control y Versionado de Código Fuente

### 3.1. Arquitectura de Repositorios (Git / GitHub)

El código fuente de BioSignal se gestiona en repositorios Git centralizados bajo la organización del proyecto en GitHub, divididos en dos módulos independientes: `biosignal-backend` y `biosignal-frontend`.

### 3.2. Estrategia de Ramas

Se adopta una adaptación de _GitFlow_ simplificado para garantizar la estabilidad de los entornos:

```
[main]      ───●─────────────────────────●───────────── (Producción estable)
               │                         ▲
[develop]   ───┼───────●─────────●───────┤             (Integración / Staging)
               │       ▲         ▲       │
[feature/*] ───┴───●───┘         │       │             (Desarrollo funcional)
                                 │       │
[bugfix/*]  ─────────────────────┴───●───┘             (Corrección de errores)
```

- **`main`:** Rama protegida de código productivo. Refleja exclusivamente versiones probadas y desplegadas en el servidor institucional.
- **`develop`:** Rama de integración continua donde se consolidan las funcionalidades probadas.
- **`feature/<nombre-tarea>`:** Ramas temporales creadas para desarrollar una historia de usuario o paquete de trabajo de la EDT (ej. `feature/parser-edf-header`).
- **`bugfix/<nombre-error>`:** Ramas temporales para resolver incidencias de QA (ej. `bugfix/fix-jwt-expiration`).

### 3.3. Regla del Control Cruzado Obligatorio (_Code Review_ / PRs)

- **Prohibición de Merge Directo:** Queda estrictamente prohibido realizar _push_ o _merge_ directo sobre las ramas `main` y `develop`.
- **Mecanismo de Pull Request (PR):** Todo desarrollador debe abrir una PR desde su rama `feature/*` hacia `develop`.
- **Revisión por Tercero:** Ningún integrante puede aprobar su propio código. Toda PR requiere obligatoriamente la revisión y aprobación escrita de al menos un revisor asignado (**Germán Herrera** en Backend/QA o **Martín Mosainer** en Full-Stack).
- **Criterios de Aceptación de la PR:** Cobertura de pruebas unitarias aprobadas, ausencia de secretos/claves hardcodeadas y paso limpio del pipeline de CI/CD.

### 3.4. Versionado Semántico y Promoción de Releases

El código fuente aplica **Semantic Versioning (SemVer - `MAJOR.MINOR.PATCH`)**:

- **`MAJOR` (Ej. 1.0.0):** Cambios estructurales incompatibles con la API anterior.
- **`MINOR` (Ej. 1.1.0):** Incorporación de nueva funcionalidad compatible hacia atrás (ej. nuevo módulo de catálogo).
- **`PATCH` (Ej. 1.1.1):** Corrección de errores o parches de seguridad.

---

## 4. Control de Cambios en la Base de Datos

### 4.1. Alcance del Control en la Capa de Datos

Abarca el modelo relacional implementado en PostgreSQL (tablas, columnas, claves foráneas, índices, restricciones de integridad y procedimientos almacenados).

### 4.2. Herramientas de Migración de Esquemas

No se permiten modificaciones manuales ejecutas directamente por consola SQL en la base de datos de producción o pruebas. Todo cambio debe gestionarse mediante **Scripts de Migración Versionados** integrados con el ORM/herramienta de persistencia.

### 4.3. Regla Obligatoria de Pares: Migración + Rollback

Todo archivo de cambio de estructura DDL debe ir acompañado de manera indivisible por su script de reversión:

1. **Script Up (`YYYYMMDDHHMMSS_descripcion.up.sql`):** Modificación a aplicar (ej. `ALTER TABLE usuarios ADD COLUMN ultimo_acceso TIMESTAMP;`).
2. **Script Down / Rollback (`YYYYMMDDHHMMSS_descripcion.down.sql`):** Sentencia de reversión exacta (ej. `ALTER TABLE usuarios DROP COLUMN ultimo_acceso;`).

### 4.4. Flujo de Aprobación y Despliegue de Datos

1. **Generación Local:** El desarrollador de backend (**Eber Chiecher**) crea el script de migración y ejecuta localmente la prueba de _Up_ y _Down_.
2. **Verificación de Impacto:** Se evalúa si el cambio destruye datos existentes o requiere un script intermedio de transformación/migración de datos.
3. **Ejecución en Staging:** Se aplica la migración en el entorno de pruebas antes de autorizar el pase a producción.
4. **Respaldo Pre-Despliegue:** Antes de ejecutar una migración en producción, la Dirección de TIC o el líder de infraestructura ejecuta un _dump/backup_ preventivo de la base de datos.

---

## 5. Control de Cambios en la Interfaz de Usuario (UI/UX)

### 5.1. Alcance de la Capa de Interfaz

Comprende los prototipos gráficos, maquetas interactivas en Figma, componentes de React y estilos CSS/Tailwind del visualizador multicanal.

### 5.2. Versionado de Maquetas en Figma

Se mantiene un archivo oficial de diseño en Figma con versionado explícito de componentes:

- **Figma v1.0 (Línea Base Inicial):** Prototipo de baja/media fidelidad.
- **Figma v2.0 (Diseño Adaptativo Refinado):** Maqueta de alta fidelidad con controles de paneo, zoom temporal, selector de canales y modo táctil mobile.
- **Figma v2.1+:** Ajustes puntuales de contraste y componentes de accesibilidad.

### 5.3. Criterios de Evaluación y Aprobación UI/UX

Antes de que una modificación de diseño sea enviada a desarrollo frontend (**Rocío Pereyra**), debe cumplir con:

1. **Pruebas de Usabilidad:** Navegación intuitiva permitiendo operar el visor en menos de 5 minutos.
2. **Accesibilidad y Legibilidad:** Contraste de color adecuado para trazado de señales fisiológicas (ECG/EEG) bajo pautas WCAG 2.1.
3. **Optimización para Renderizado Canvas/WebGL:** Verificación de que los controles no sobrecarguen la DOM para garantizar la fluidez a ≥ 30 FPS.

### 5.4. Trazabilidad con el Backlog (ver herramienta)

Todo cambio visual en la interfaz debe estar vinculado al ID de la historia de usuario correspondiente en (alguna herramienta) (ej. `BIOSIG-45: Ajuste de escala de amplitud en Canvas`), impidiendo rediseños estéticos que no estén presupuestados en el Sprint.

---

## 6. Registro de Cambios (_Change Log_) y Auditoría

### 6.1. Plantilla del Registro de Cambios del Proyecto (_Change Log_)

Toda solicitud de cambio aprobada o rechazada se asienta en la **Matriz Consolidada de Control de Cambios**:

|  ID Cambio  | Fecha Solicitud | Elemento Afectado (CI)                  | Descripción del Cambio Solicitado                        | Solicitante   | Revisor Técnico / Legal    |           Dictamen CCB           | Versión Resultante |    Estado    |
| :---------: | :-------------: | :-------------------------------------- | :------------------------------------------------------- | :------------ | :------------------------- | :------------------------------: | :----------------: | :----------: |
| **RFC-001** |   05/10/2026    | `CI-DOC-02` (Especificación Requisitos) | Ajuste en RNF-02 de latencia LCP de 10s a ≤ 2,5s.        | Astudillo, M. | Ávila Gelbes, I.           |           **Aprobado**           |       `v2.0`       | Implementado |
| **RFC-002** |   12/10/2026    | `CI-CODE` (Backend Ingesta)             | Incorporación de parser secundario para formato .MAT.    | Colaborador   | Herrera, G. / Chiecher, E. | **Rechazado** (Fuera de alcance) |        N/A         |   Cerrado    |
| **RFC-003** |   18/10/2026    | `CI-DATA` (PostgreSQL)                  | Agregado de tabla `auditoria_descargas` para Ley 25.326. | Chiecher, E.  | Equipo PM / Legal          |           **Aprobado**           |      `v1.2.0`      |    En QA     |

### 6.2. Auditorías de Configuración

Al finalizar cada hito del proyecto, el Asistente del PM y el equipo de QA realizarán una **Auditoría de Configuración** para verificar que:

- Todos los entregables desplegados coinciden exactamente con la versión aprobada en el Change Log.
- Ningún componente de software o tabla de base de datos fue modificado al margen del proceso formal.

---
