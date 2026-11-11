# AGENTS.md — BioSignal / biosignalsbank

Instrucciones para agentes de IA (y personas) que trabajen en este repositorio.

## 1. Qué es este repo

Repositorio **documental** del trabajo práctico académico **BioSignal — Banco de Señales Biomédicas de la UNViMe**. Los artefactos de gestión de proyectos se escriben en Markdown dentro de `content/` y se publican como sitio estático con **Quartz**.

- El proyecto es **ficticio**: no hay clientes, contratos, pacientes ni sistema en producción reales. No presentarlo como real ni contactar a terceros invocándolo.
- Este repo **no contiene el código del producto**. El stack canónico (Next.js/React + TypeScript, FastAPI/Python, PostgreSQL, Docker, CI/CD) es una decisión de arquitectura del escenario; el código, si existiera, va en otro repositorio (EJ-03).
- Punto de entrada obligatorio antes de escribir: **`content/00-contexto-del-proyecto.md`**.

## 2. Jerarquía de verdad

1. **Documentos fuente aprobados** (Acta 02, ERS 03, Alcance 04, EDT 05, Diccionario 06, RTM 07, Riesgos XX, Adquisiciones 08, Cambios 09, Conocimiento 10, Competencias 11, Calidad 12, Evaluaciones 13).
2. `content/00-contexto-del-proyecto.md`: mapa, resumen y registro de decisiones de _tailoring_. Explica el “por qué”, no reemplaza a las fuentes.
3. `content/borradores/` y `content/consignas/`: material de trabajo y enunciados. **No son fuente de verdad y no se publican.**
4. Acuerdos verbales o de chat: solo valen si quedan registrados en un documento, acta, RFC o Change Log.

Si dos documentos se contradicen, gana el documento fuente y se abre un **RFC** para corregir. No “arreglar” una contradicción editando el documento equivocado.

## 3. Estructura

```
content/                          # raíz publicada (solo acá va lo vigente)
├── index.md                      # índice del sitio
├── 00-contexto-del-proyecto.md   # contexto; excluido del sitio por ignorePatterns
├── 02-…, 03-…, …, 13-…, XX-…     # documentos principales
├── 02b-…                         # comunicaciones y partes interesadas
├── diccionario-del-edt/          # desglose del EDT (una carpeta por rama + index.md)
├── evaluaciones-de-desempeno/    # instrumentos 360° + index.md
├── imagenes/                     # imágenes referenciadas por los documentos
├── borradores/                   # NO se publica
└── consignas/                    # NO se publica
quartz.config.default.yaml        # configuración del sitio (título, plugin, ignorePatterns)
quartz.ts                         # carga la config y el layout
quartz/                           # motor Quartz v5 (no editar salvo tarea explícita)
public/                           # salida de build (ignorada por git)
```

## 4. Comandos

Requiere **Node ≥ 22** (`.node-version`: v22.16.0) y **npm ≥ 10.9.2**.

```bash
npm install                 # dependencias
npm run install-plugins     # instala plugins de Quartz (necesario tras clonar o cambiar versión)
npx quartz build --serve --watch   # preview local en http://localhost:8080
npx quartz build            # build de producción en public/
npx quartz build --bundleInfo      # build con detalle de bundle
npm run check               # tsc --noEmit + prettier --check
npm run format              # prettier --write
npm test                    # tests de Quartz (tsx --test)
```

Notas:

- No hay script `npm run build`; el build se invoca con `npx quartz build` (o `npm run quartz -- build`).
- Los workflows de `.github/workflows/` son heredados de la plantilla de Quartz y están condicionados a `github.repository == 'jackyzha0/quartz'`: **no validan este repo**. La verificación local es `npm run check` + `npx quartz build`.
- El despliegue del sitio es externo (Render, `https://biosignalsbank.onrender.com/`); no hay pipeline de deploy en este repo.

## 5. Convenciones de los documentos

- **Markdown + frontmatter YAML**. Campos habituales: `project`, `version`, `title`, `aliases`, `authors`, `date`. Mantener el estilo del archivo que se edita; no todos los documentos tienen `authors`/`date`.
- **Nombre de archivo**: prefijo numérico (`02-`, `03-`, …, `02b-`, `XX-`) en kebab-case (`05-estructura-de-desglose-detrabajo.md`).
- **Enlaces internos**: estilo Obsidian `[[documento|texto]]` o rutas relativas a `.md` con ancla. Para subcarpetas, `[[evaluaciones-de-desempeno/archivo|texto]]`. La resolución de enlaces es por ruta más corta.
- **Fechas**: `dd/mm/aaaa`. **Moneda**: `USD` para caja, `ARS` para esfuerzo interno; nunca mezclar.
- **Versionado**: `v0.x` en revisión, `v1.0` aprobado, `v1.x` corrección menor. Los archivos usan tanto enteros (`version: 2`) como cadenas (`version: 1.1`); respetar el formato existente y subir versión al cambiar contenido sustantivo.
- **IDs estables**: `O-`, `EP-`, `EJ-`, `H1…H7`, `RF-`, `RNF-`, `RN-`, `RT-`, `RP-`, `R-`, `RFC-`, `T-`. No renumerar ni reutilizar.
- **Tablas** para fichas, matrices y umbrales; **callouts** (`>`) para advertencias y decisiones. Diagramas con bloques `mermaid`.
- Tono: formal, en español rioplatense neutro, sin marketing ni emojis decorativos.

## 6. Reglas de publicación

- Solo se publica lo que está en `content/` (config: `quartz.config.default.yaml`).
- `borradores`, `consignas`, `00-contexto-del-proyecto.md`, `private`, `templates` y `.obsidian` están excluidos por `ignorePatterns`. **No agregar documentos vigentes a `borradores/`.**
- Al crear un documento nuevo, agregarlo a `content/index.md` con su enlace y actualizar los índices de subcarpeta si corresponde.
- Los assets van en `content/imagenes/` con rutas relativas.
- No editar `public/`, `.quartz-cache/` ni `node_modules/` (ignorados por git).

## 7. Coherencia y control de cambios

1. No inventar métricas, fechas, costos, proveedores ni stakeholders que no estén en los documentos fuente.
2. Si se agrega o cambia un requisito: actualizar **ERS (03)**, **RTM (07)** y, si impacta, **EDT (05)** y **Alcance (04)**.
3. Si se cambia un umbral (TTIS, FPS, PII, cobertura, etc.): revisar **todas** sus menciones (Acta, ERS, Alcance, Calidad, RTM, Contexto).
4. Todo cambio de alcance, plazo, costo o beneficio requiere **RFC** y registro en el **Change Log** de `09-gestion-y-control-de-cambios.md`.
5. Distinguir siempre entre **dato del escenario**, **supuesto** y **decisión de tailoring**. Las decisiones de tailoring se registran en la sección 13 del contexto (T-01…T-12).
6. No usar datos personales reales; todo EDF debe ser sintético o anonimizado (Ley 25.326).
7. Si queda una brecha abierta, registrarla en la sección 15 del contexto.

## 8. Datos clave que no deben contradecirse

| Dato               | Valor                                                             |
| :----------------- | :---------------------------------------------------------------- |
| Proyecto           | BioSignal — Banco de Señales Biomédicas de la UNViMe              |
| Duración           | 15 semanas: 02/11/2026 → 15/02/2027                               |
| Producción         | 12/02/2027 (cierre 15/02/2027)                                    |
| Caja               | $0 USD de desembolso directo                                      |
| Esfuerzo           | 260–360 h; referencia ARS 10.000/h (no erogable)                  |
| Dataset semilla    | 30 EDF: 15 ECG + 15 EEG                                           |
| Roles del producto | Administrador y Consultor (RBAC)                                  |
| Equipo             | PM Mateo Astudillo; APM Ignacio Ávila; 4 integrantes              |
| Sponsor            | EICA / UNViMe, Ing. Alejandro Rosas (rol del escenario)           |
| Stack              | Next.js/React + TypeScript · FastAPI/Python · PostgreSQL · Docker |

Umbrales críticos: TTIS ≤ 2,5 s · ≥ 30 FPS · 100 usuarios concurrentes · ≤ 30 s por EDF < 50 MB · 0 % PII residual · TLS 1.3 · cobertura > 80 % · WCAG 2.1 AA · disponibilidad ≥ 99,9 %.

## 9. Qué está fuera de alcance (no proponerlo ni documentarlo como incluido)

Anotaciones clínicas, calibradores o medición sobre la señal; registro público de usuarios y recuperación autónoma de credenciales; roles distintos de Admin/Consultor; exportación a CSV/JSON/MATLAB; captura en tiempo real o hardware; diagnóstico automático o IA clínica; certificación ANMAT; apps nativas; migración desde LightWAVE; manuales de usuario, capacitaciones y soporte post-cierre.

## 10. Deudas documentales conocidas (sección 15 del contexto)

- Plan integrador sin archivo propio.
- Matriz RACI referenciada pero inexistente (la matriz de competencias **no** es una RACI).
- Registro completo de riesgos `R-01…R-12` no publicado.
- Evidencia Jira de la consigna 06b no versionada en este repo.
- Caso de negocio y registro de beneficios referenciados, no autónomos.
- Inconsistencia de estado del Acta v2.0 vs. RFC-004 (“Pendiente Sponsor”).
- Varios documentos en “Propuesto (pendiente CCB)”; el Change Log debe ser la referencia única de estado.

No cerrar estas brechas inventando contenido: usar los documentos existentes o abrir RFC.

## 11. Checklist antes de entregar un cambio

- [ ] Leí `content/00-contexto-del-proyecto.md` y el documento fuente afectado.
- [ ] El cambio no contradice alcance, exclusiones ni umbrales aprobados.
- [ ] Mantuve tono, formato, IDs y convenciones de fecha/moneda.
- [ ] Diferencié dato del escenario, supuesto y decisión de tailoring.
- [ ] Si cambié requisitos o umbrales, actualicé RTM, Change Log y documentos impactados.
- [ ] Si agregué un documento, lo enlacé desde `content/index.md`.
- [ ] `npm run check` y `npx quartz build` pasan sin errores nuevos.
- [ ] No publiqué borradores ni consignas como documentación vigente.
- [ ] No expuse credenciales (p. ej. `mcp.json`) en documentos, commits ni logs.

## 12. Seguridad del repositorio

`mcp.json` contiene una API key en texto plano. No copiarla a documentación, issues, logs ni respuestas; si se rota o elimina, tratarlo como tarea aparte y avisar al equipo.
