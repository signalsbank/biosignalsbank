---
title: "Inicio - Biosignals Bank"
---

# BioSignal: Banco de Señales Biomédicas

Plataforma web centralizada para el almacenamiento, gestión, visualización interactiva y análisis académico de registros fisiológicos en formato estándar EDF (.edf).

Proyecto institucional desarrollado en el marco de la Universidad Nacional de Villa Mercedes (UNViMe), concebido como una herramienta de articulación pedagógica entre la carrera de Bioingeniería, la Escuela de Ciencias de la Salud y la Escuela de Medicina.

## Propósito del Proyecto

BioSignal surge para cubrir la necesidad de contar con un repositorio institucional propio que permita a las cátedras trabajar con registros biomédicos reales directamente desde el navegador web.

El sistema resuelve dos necesidades operativas concretas:

- **Gestión y carga (Bioingeniería):** Provee un canal unificado para catalogar, validar y almacenar registros fisiológicos locales, verificando automáticamente la integridad de los archivos EDF y extrayendo sus metadatos (frecuencia de muestreo, canales y unidades).
- **Consumo didáctico (Medicina y Ciencias de la Salud):** Proporciona un entorno de visualización ágil sin necesidad de instalar software especializado ni controladores en equipos personales, facilitando la ejercitación clínica y el análisis de señales.

## Funcionalidades del Sistema

- **Visualizador web de alto rendimiento:** Renderizado gráfico interactivo basado en Canvas/WebGL, con herramientas de desplazamiento temporal (paneo), zoom dinámico y ajuste de amplitud.
- **Procesamiento de formato estándar:** Motor de ingesta compatible con archivos `.edf` con lectura de cabeceras, extracción paramétrica y segmentación de datos (_chunking_) para streaming web.
- **Control de acceso basado en roles:** Perfiles diferenciados para la administración y carga de registros (Bioingeniería) y para la consulta y estudio (Medicina/Salud).
- **Anonimización estricta:** Eliminación irreversible de información identificatoria de pacientes previa a la persistencia de datos en el servidor, garantizando el cumplimiento de normativas de privacidad médica.

## Límites del Alcance

Para garantizar el cumplimiento de los requerimientos técnicos y legales, el sistema define con precisión sus fronteras operativas:

**Incluido en el Alcance**

Ingesta, validación y catálogo de registros en formato EDF.
Streaming y renderizado web interactivo.
Descarga de archivos en formato estandarizado.

**Excluido del Alcance**

Adquisición o captura de señales en tiempo real desde hardware.
Algoritmos de diagnóstico automatizado o soporte a la decisión clínica.
Uso hospitalario, terapéutico o sustitución de software médico certificado.
Soporte para formatos propietarios ajenos al estándar acordado.


## Equipo de Trabajo

- **Director del Proyecto (PM):** Mateo Tomás Astudillo
- **Asistente de Dirección:** Ignacio Nicolás Ávila Gelbes
- **Backend y Aseguramiento de Calidad (QA):** Germán Ezequiel Herrera
- **Desarrollo Full-Stack y Soporte:** Martín David Mosainer
- **Backend e Infraestructura:** Eber Blas Chiecher
- **Desarrollo Frontend:** Rocío Pereyra
