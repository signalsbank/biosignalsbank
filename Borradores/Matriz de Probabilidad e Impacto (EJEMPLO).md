| Probabilidad \ Consecuencia | Leve / Bajo |                                  Moderado / Medio                                   |                       Grave / Alto                        |                 Catastrófico / Crítico                 |
| :-------------------------- | :---------: | :---------------------------------------------------------------------------------: | :-------------------------------------------------------: | :----------------------------------------------------: |
| **Alta**                    | _Zona Baja_ |               **R3** (Disponibilidad por exámenes)<br>_(Nivel Medio)_               |   **R2** (Rendimiento del visor web)<br>_(Nivel Alto)_    |                     _Zona Crítica_                     |
| **Media**                   | _Zona Baja_ | **R1** (Demora en datos EDF)<br>**R6** (Baja adopción académica)<br>_(Nivel Medio)_ | **R5** (Límites infraestructura $0 USD)<br>_(Nivel Alto)_ |                     _Zona Crítica_                     |
| **Baja** 1                  | _Zona Baja_ |                                     _Zona Baja_                                     |                       _Zona Media_                        | **R4** (Filtración datos Ley 25.326)<br>_(Nivel Alto)_ |
Probabilidad = 2, Imapcato = 3 Total = P x I (para determinar un valor, más valor más riesgo)
## Clasificación de Severidad y Niveles de Acción

| Nivel de Riesgo       |  Rango   | Criterio de Acción                                                                       | Riesgos Identificados  |
| :-------------------- | :------: | :--------------------------------------------------------------------------------------- | :--------------------- |
| **Crítico / Extremo** |   Rojo   | Medidas de contingencia inmediatas; escalamiento directo a las autoridades de la UNViMe. | —                      |
| **Alto**              | Naranja  | Mitigación proactiva y seguimiento semanal obligatorio por el equipo de desarrollo.      | **R2**, **R4**, **R5** |
| **Medio**             | Amarillo | Monitoreo periódico en retrospectivas de hito y aplicación de medidas preventivas.       | **R1**, **R3**, **R6** |
| **Bajo**              |  Verde   | Aceptación informada; monitoreo pasivo sin asignación de recursos extra.                 | —                      |

## Detalle de Riesgos Mapeados

- **R1 — Demora en entrega de datos EDF reales:** Probabilidad Media × Consecuencia Media $\rightarrow$ **Nivel Medio**.
- **R2 — Sobrecarga o latencia del visor en el navegador:** Probabilidad Alta × Consecuencia Alta $\rightarrow$ **Nivel Alto**.
- **R3 — Disminución de horas de desarrollo por exámenes:** Probabilidad Alta × Consecuencia Media $\rightarrow$ **Nivel Medio**.
- **R4 — Exposición de datos personales de pacientes (Ley 25.326):** Probabilidad Baja × Consecuencia Crítica $\rightarrow$ **Nivel Alto**.
- **R5 — Agotamiento de cuotas gratuitas ($0 USD) / retraso de servidores UNViMe:** Probabilidad Media × Consecuencia Alta $\rightarrow$ **Nivel Alto**.
- **R6 — Baja adopción curricular en cátedras de Medicina y Salud:** Probabilidad Media × Consecuencia Media $\rightarrow$ **Nivel Medio**.
