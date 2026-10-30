# Listas de Verificación de Calidad — Proyecto BioSignal

| Campo     | Valor                                                                               |
| --------- | ----------------------------------------------------------------------------------- |
| Documento | LV-BIOSIG-03                                                                        |
| Versión   | v0.1 (borrador)                                                                     |
| Normas    | ISO/IEC 20000 (servicio), ISO/IEC 25010 (producto), ISO/IEC 12207 nivel 1 (proceso) |

**Uso:** cada lista se completa por el responsable indicado y se adjunta como evidencia al Informe de Calidad del hito. Marcar `[x]` (cumple), `[ ]` (no cumple / pendiente) o `N/A` con justificación. Un ítem **crítico (★)** en "no cumple" bloquea la aprobación del entregable.

Encabezado a completar en cada uso:

| Lista | Versión evaluada | Fecha | Responsable | Resultado (Aprobado / Rechazado) |
| ----- | ---------------- | ----- | ----------- | -------------------------------- |
|       |                  |       |             |                                  |

---

## LV-01 — Definition of Done de código (PR a `develop`)

_Responsable: autor + revisor (Herrera / Mosainer)_

- [ ] ★ La rama es `feature/*` o `bugfix/*` y la PR apunta a `develop`
- [ ] ★ El revisor es distinto del autor y dejó aprobación escrita
- [ ] ★ Pipeline CI en verde (build, lint, tests)
- [ ] ★ Sin secretos ni claves hardcodeadas (gitleaks)
- [ ] Pruebas unitarias nuevas/actualizadas; cobertura de lo modificado > 80 %
- [ ] Sin vulnerabilidades críticas/altas en dependencias (pip-audit / npm audit)
- [ ] Linter y tipado sin errores (ruff/mypy, ESLint/tsc)
- [ ] La PR referencia el ID de tarea/historia (p. ej. BIOSIG-45) y el requisito (RF/RNF)
- [ ] Documentación inline/README actualizada si cambió una interfaz
- [ ] Si afecta una línea base: RFC creado en el Change Log

## LV-02 — Ingesta, validación y anonimización EDF/EDF+

_Responsable: Backend + QA. Req.: RF-04, RF-05, RF-06, RNF-04, RNF-05_

**Validación estructural**

- [ ] ★ Solo se aceptan `.edf` / `.edf+`; se rechazan otras extensiones y archivos con extensión falsa (verificación por contenido, no por nombre)
- [ ] ★ La cabecera se valida antes de confirmar la carga: número de señales (ns), duración del registro de datos, nº de registros, tamaño de cabecera coherente (256 + ns×256 bytes)
- [ ] Se validan los campos de transductor y prefiltrado por señal
- [ ] Archivo truncado o corrupto → error claro, sin persistencia parcial
- [ ] Carga atómica: ante falla no quedan metadatos huérfanos ni binario sin registro

**Sanitización (Ley 25.326)**

- [ ] ★ Campo _Local Patient Identification_ (80 bytes) sobrescrito (p. ej. `X X X X`) — sin nombre, documento, sexo ni fecha de nacimiento
- [ ] ★ Campo _Local Recording Identification_ (80 bytes) sobrescrito: sin fecha exacta de inicio, ID de investigador ni ID de equipo con datos personales
- [ ] ★ Fecha/hora de inicio (cabecera) generalizada o neutralizada según política definida
- [ ] ★ Canal de anotaciones EDF+ (`EDF Annotations`) revisado: sin nombres, fechas de nacimiento ni IDs en el texto de anotaciones
- [ ] ★ Nombre de archivo original descartado o reemplazado por identificador interno
- [ ] Datos personales ausentes en logs, mensajes de error, URLs y metadatos de la BD
- [ ] Sanitización **antes** de persistir; el archivo original con PII no se conserva en disco ni en temporales
- [ ] ★ Auditoría binaria automatizada ejecutada sobre el 100 % de los archivos persistidos con 0 hallazgos
- [ ] Prueba con archivo "sentinela" (PII sintética en todos los campos) aprobada
- [ ] Integridad de datos de señal tras sanitizar: muestras idénticas al original (comparación)

**Rendimiento**

- [ ] Ingesta de EDF < 50 MB ≤ 30 s (n ≥ 10 corridas; registrar media y máximo)
- [ ] Lectura por bloques (sin cargar el archivo completo en memoria)

## LV-03 — Metadatos, baja lógica y exportación

_Responsable: Backend + QA. Req.: RF-07, RF-08, RF-14_

- [ ] Ficha con tipo de señal (ECG/EEG/EMG), patología, grupo etario, equipamiento y notas; campos obligatorios validados
- [ ] Catálogos cerrados aplicados (sin texto libre en campos normalizados)
- [ ] ★ Edición de metadatos no modifica el binario (hash antes = después)
- [ ] Cada edición registra autor, fecha y campo modificado
- [ ] ★ Baja lógica solo disponible para Administrador (Consultor recibe 403)
- [ ] ★ Doble confirmación en pantalla; baja registrada en log de auditoría con motivo
- [ ] El registro dado de baja desaparece de búsquedas y permanece íntegro en BD
- [ ] ★ La descarga entrega el EDF **sanitizado** (nunca un original); validado con MNE-Python/pyedflib
- [ ] Cada descarga queda registrada en auditoría

## LV-04 — Autenticación, sesiones y RBAC

_Responsable: Backend + QA. Req.: RF-01, RF-02, RNF-05, RNF-06_

- [ ] ★ Dos perfiles operativos: Administrador y Consultor, con matriz de permisos documentada
- [ ] ★ Toda acción no permitida devuelve HTTP 403; rutas protegidas también en backend (no solo en frontend)
- [ ] ★ Sesión Administrador expira a los 30 min sin interacción (token invalidado y redirección a login)
- [ ] Contraseñas con Argon2/bcrypt; nunca en logs
- [ ] Bloqueo temporal tras 5 intentos fallidos
- [ ] Tokens solo por HTTPS; cookies con `HttpOnly`, `Secure`, `SameSite`
- [ ] Mensajes de recuperación/registro sin revelar si un correo existe
- [ ] Enlace de recuperación ≤ 15 min y de un solo uso; token de activación ≤ 30 min
- [ ] Prueba de elevación de privilegios (Consultor → acciones de Administrador) superada
- [ ] Sección pública sin credenciales **no** expone catálogo ni descargas privadas

## LV-05 — Visualizador interactivo

_Responsable: Frontend + QA. Req.: RF-09…RF-13, RNF-02, RNF-03, RNF-08_

- [ ] ★ Canales múltiples sincronizados con la misma escala temporal
- [ ] ★ Primer segmento visible ≤ 2,5 s en red de 10 Mbps (LCP; carga por fragmentos)
- [ ] ★ ≥ 30 FPS sostenidos en paneo y zoom continuos con 32 canales
- [ ] Paneo hacia adelante y atrás en toda la duración sin congelamiento
- [ ] Zoom temporal (X) y de amplitud (Y), global y por canal
- [ ] Escalas clínicas 25 mm/s y 10 mm/mV calibradas (verificación contra regla/papel milimetrado en pantalla)
- [ ] Encender/apagar y reordenar canales (drag-and-drop)
- [ ] Desktop ≥ 1024 px: hasta 32 canales; móvil < 768 px: 1–2 canales por defecto
- [ ] Sin fuga de memoria tras 5 min de uso intenso
- [ ] Contraste y legibilidad (WCAG 2.1 AA); controles operables por teclado
- [ ] Señal demo y banner de admisiones UNViMe funcionales en la portada pública
- [ ] Estados vacíos, carga y error comprensibles

## LV-06 — Compatibilidad cross-browser

_Responsable: QA. Req.: RNF-07_

| Navegador                           | Versión N | Versión N-1 | Login | Visualizador | Paneo/Zoom | Carga EDF | Descarga |
| ----------------------------------- | --------- | ----------- | ----- | ------------ | ---------- | --------- | -------- |
| Chrome (Chromium)                   | [ ]       | [ ]         | [ ]   | [ ]          | [ ]        | [ ]       | [ ]      |
| Edge (Chromium)                     | [ ]       | [ ]         | [ ]   | [ ]          | [ ]        | [ ]       | [ ]      |
| Firefox (Gecko)                     | [ ]       | [ ]         | [ ]   | [ ]          | [ ]        | [ ]       | [ ]      |
| Safari (WebKit)                     | [ ]       | [ ]         | [ ]   | [ ]          | [ ]        | [ ]       | [ ]      |
| Safari iOS / Chrome Android (móvil) | [ ]       | —           | [ ]   | [ ]          | [ ]        | N/A       | [ ]      |

- [ ] ★ 100 % de la matriz superada, sin plugins ni extensiones

## LV-07 — Base de datos y migraciones

_Responsable: Chiecher (BD/Infra) + Herrera. Ref.: Plan SCM §4_

- [ ] ★ Migración con script `up` y `down` (`YYYYMMDDHHMMSS_desc.up/down.sql`)
- [ ] ★ `up` y `down` probados localmente y en staging
- [ ] Evaluación de impacto sobre datos existentes (¿destruye o transforma?)
- [ ] ★ Backup/dump preventivo ejecutado antes de migrar producción
- [ ] Sin cambios manuales por consola SQL en staging/producción
- [ ] Índices para búsquedas por tipo de señal, patología, grupo etario
- [ ] Permisos mínimos por rol de BD; credenciales fuera del repositorio
- [ ] Cifrado en reposo y conexiones cifradas
- [ ] Latencia de conexión < 50 ms; consulta de catálogo < 500 ms

## LV-08 — Seguridad web y transporte

_Responsable: QA + DevOps. Req.: RNF-06, OC-02_

- [ ] ★ TLS 1.3 activo; TLS ≤ 1.2 y suites débiles deshabilitados; calificación A
- [ ] Redirección HTTP→HTTPS y HSTS
- [ ] Encabezados: CSP, X-Content-Type-Options, X-Frame-Options/frame-ancestors, Referrer-Policy
- [ ] ★ Escaneo OWASP Top 10 (ZAP) sin hallazgos críticos/altos
- [ ] Protección contra inyección SQL, XSS, CSRF, subida maliciosa de archivos (tamaño y tipo limitados)
- [ ] Rate limiting en login, registro y recuperación
- [ ] Captcha en registro
- [ ] Dependencias sin vulnerabilidades críticas/altas
- [ ] Firewall: solo puertos necesarios abiertos

## LV-09 — Revisión de calidad de documentos (ERS, planes, actas)

_Responsable: Process Owner (Ávila Gelbes) + autor_

- [ ] Encabezado con versión, fecha, autor, aprobador e historial de cambios
- [ ] Nomenclatura de versión correcta (v0.x borrador, v1.0 aprobado, v1.1 corrección menor)
- [ ] Requisitos: únicos, atómicos, no ambiguos, verificables, con criterio Pasa/No Pasa (ISO 29148)
- [ ] Trazabilidad completa (RN → RI → RF/RNF → EDT → prueba)
- [ ] Coherencia entre documentos (umbrales, fechas, alcance y exclusiones)
- [ ] ★ Revisión legal si el documento trata datos personales (Ley 25.326)
- [ ] Revisión por pares realizada y observaciones cerradas
- [ ] ★ Aprobación y firma del Director del Proyecto
- [ ] Publicado en el repositorio central (única versión vigente)

## LV-10 — Pre-despliegue y puesta en servicio (ISO/IEC 20000)

_Responsable: Chiecher (DevOps) + Herrera (QA) + PM. Req.: RT-02, RP-01, Pkg 1.5_

**Gestión de la configuración y de cambios / releases**

- [ ] ★ Release candidate etiquetado (SemVer) = versión aprobada en Change Log
- [ ] ★ Cambios en backend/infraestructura documentados (RFC) y probados en staging
- [ ] ★ Cero defectos críticos/bloqueantes abiertos; recomendación escrita de QA
- [ ] Plan de rollback (versión previa + script `down`) documentado y probado
- [ ] Ventana de mantenimiento acordada con Dirección TIC

**Infraestructura (RP-01)**

- [ ] Credenciales de despliegue, subdominio `*.unvime.edu.ar` y ≥ 100 GB de almacenamiento persistente provistos y verificados
- [ ] Certificado TLS instalado y válido
- [ ] Backups automáticos programados y restauración probada
- [ ] Variables de entorno y secretos gestionados fuera del código

**Verificación en producción**

- [ ] ★ Prueba de humo al 100 %: login, carga, búsqueda, visualización y descarga
- [ ] ★ Dataset semilla: ≥ 30 EDF (≥ 15 ECG y ≥ 15 EEG) catalogados
- [ ] ★ Auditoría binaria del dataset: 0 PII
- [ ] Sin errores en logs tras la prueba de humo

## LV-11 — Calidad del servicio para operar (ISO/IEC 20000)

_Responsable: DevOps + PM. Entrega a Dirección TIC en el cierre_

**Gestión de incidencias**

- [ ] ★ Existe un canal documentado para reportar fallas del servicio (correo/formulario/gestor)
- [ ] Categorías y prioridades de incidencia definidas
- [ ] Contacto y responsable de recepción indicado en la transferencia

**Gestión de disponibilidad**

- [ ] ★ Monitoreo de uptime activo (objetivo 99,9 %) con alertas
- [ ] Monitoreo de CPU, memoria, disco y logs de errores
- [ ] Alerta de espacio de almacenamiento (umbral antes de agotar los 100 GB)

**Gestión de cambios**

- [ ] ★ Procedimiento de cambio documentado: solicitud → evaluación → aprobación → staging → producción
- [ ] Registro de cambios y versiones desplegadas accesible

**Continuidad**

- [ ] Política de respaldo (frecuencia, retención) y procedimiento de restauración entregados

> Recordatorio: el soporte posterior al Acta de Cierre está fuera de alcance; esta lista deja el servicio **transferible** a la Dirección TIC.

## LV-12 — Compuerta de salida de la fase de QA (Go / No-Go)

_Responsable: QA recomienda; PM decide_

- [ ] ★ 0 defectos críticos/bloqueantes abiertos
- [ ] ★ 100 % de pruebas unitarias en verde; cobertura > 80 % en lógica crítica
- [ ] ★ RNF-01…RNF-09 en umbral (ver Métricas)
- [ ] ★ Auditoría binaria EDF al 100 % limpia
- [ ] Defectos mayores con plan de corrección o aceptación documentada
- [ ] UAT aprobado por el 100 % de evaluadores designados (acta)
- [ ] Reporte Consolidado de QA (EJ-04) emitido
- [ ] Auditoría de configuración del hito sin desvíos

**Decisión:** ☐ GO ☐ NO-GO ☐ GO condicionado (detallar): ______________________

## LV-13 — Cierre del proyecto (verificación de entregables)

_Responsable: PM + APM. Req.: RN-02, EJ-05, EJ-06_

- [ ] Acta de homologación y despliegue firmada **≤ 15/02/2027**
- [ ] Sistema operativo en `*.unvime.edu.ar`
- [ ] Repositorios de código (frontend y backend) entregados con scripts de build/ejecución
- [ ] Reporte QA entregado; evidencias archivadas
- [ ] Lecciones aprendidas documentadas
- [ ] Demostración en al menos una jornada institucional (RN-04) y adopción en ≥ 2 programas de cátedra (RN-03) — registrar estado (puede ser posterior al cierre)
- [ ] Convenios y avales éticos archivados (RP-03)
