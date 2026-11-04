# ASpectrum - Reto B: Pronóstico del IPAP-BMC

## 1. Descripción del Proyecto
Sistema predictivo y de gestión de riesgo para el índice **IPAP-BMC** de la Bolsa Mercantil de Colombia, desarrollado por el equipo **ASpectrum** como parte del DataLab Challenge. Su objetivo es anticipar la tendencia del mercado agropecuario y medir la volatilidad para optimizar la toma de decisiones y las coberturas financieras.

## 2. Principales Resultados Cuantitativos y Econométricos
* **Validación Histórica (MAPE):** Se alcanzó un desempeño sobresaliente con un error porcentual absoluto medio del **7%** en la prueba histórica de los últimos 12 meses[cite: 3].
* **Poder Explicativo ($R^2$):** El modelo econométrico base logra un coeficiente de determinación ajustado del **98.18%**, capturando de manera efectiva la estacionalidad extrema del sector agropecuario.
* **Persistencia de la Volatilidad (GARCH):** A través de la modelación GARCH(1,1), se identificó que la suma de los coeficientes $\alpha + \beta$ es extremadamente cercana a 1 (superando 0.99 en índices clave como *IP_agroipe* y *lechem*). Esto demuestra que los choques de precios en el agro **son altamente persistentes en el tiempo**, justificando la urgencia de utilizar instrumentos de cobertura en la Bolsa Mercantil.

---

## 3. Tablas Requeridas de Validación y Pronóstico

### Tabla 1: Testeo Histórico y Validación MAPE (52 Observaciones Semanales del Periodo de Prueba)
*Evaluación completa del desempeño del modelo frente a los datos reales observados durante el último año histórico.*

| Fecha (Semanal) | IPAP Real | IPAP Predicho (Modelo) | Error Porcentual Absoluto (%) |
| :--- | :--- | :--- | :--- |
| 2022-10-16 | 221.61 | 220.69 | 0.41% |
| 2022-10-23 | 223.46 | 220.85 | 1.17% |
| 2022-10-30 | 225.81 | 221.01 | 2.13% |
| 2022-11-06 | 230.53 | 221.17 | 4.06% |
| 2022-11-13 | 234.58 | 221.33 | 5.65% |
| 2022-11-20 | 236.14 | 221.49 | 6.21% |
| 2022-11-27 | 235.32 | 221.65 | 5.81% |
| 2022-12-04 | 235.44 | 221.81 | 5.79% |
| 2022-12-11 | 240.71 | 221.96 | 7.79% |
| 2022-12-18 | 243.80 | 222.12 | 8.89% |
| 2022-12-25 | 247.45 | 222.28 | 10.17% |
| 2023-01-01 | 251.20 | 222.44 | 11.45% |
| 2023-01-08 | 258.69 | 222.60 | 13.95% |
| 2023-01-15 | 257.55 | 222.76 | 13.51% |
| 2023-01-22 | 249.67 | 222.92 | 10.72% |
| 2023-01-29 | 248.51 | 223.08 | 10.23% |
| 2023-02-05 | 246.60 | 223.24 | 9.47% |
| 2023-02-12 | 247.95 | 223.40 | 9.90% |
| 2023-02-19 | 250.77 | 223.56 | 10.85% |
| 2023-02-26 | 255.45 | 223.72 | 12.42% |
| 2023-03-05 | 255.41 | 223.88 | 12.35% |
| 2023-03-12 | 252.61 | 224.04 | 11.31% |
| 2023-03-19 | 250.93 | 224.20 | 10.65% |
| 2023-03-26 | 249.77 | 224.36 | 10.17% |
| 2023-04-02 | 244.75 | 224.52 | 8.27% |
| 2023-04-09 | 239.52 | 224.68 | 6.19% |
| 2023-04-16 | 240.24 | 224.84 | 6.41% |
| 2023-04-23 | 242.06 | 225.00 | 7.05% |
| 2023-04-30 | 244.33 | 225.16 | 7.85% |
| 2023-05-07 | 248.14 | 225.32 | 9.20% |
| 2023-05-14 | 248.77 | 225.48 | 9.36% |
| 2023-05-21 | 252.12 | 225.64 | 10.50% |
| 2023-05-28 | 249.52 | 225.80 | 9.51% |
| 2023-06-04 | 247.38 | 225.96 | 8.66% |
| 2023-06-11 | 248.24 | 226.12 | 8.91% |
| 2023-06-18 | 245.96 | 226.28 | 8.00% |
| 2023-06-25 | 243.68 | 226.43 | 7.08% |
| 2023-07-02 | 242.79 | 226.57 | 6.68% |
| 2023-07-09 | 242.80 | 226.73 | 6.62% |
| 2023-07-16 | 242.58 | 226.89 | 6.47% |
| 2023-07-23 | 242.15 | 227.05 | 6.24% |
| 2023-07-30 | 243.20 | 227.21 | 6.58% |
| 2023-08-06 | 243.64 | 227.37 | 6.68% |
| 2023-08-12 | 239.58 | 227.53 | 5.03% |
| 2023-08-19 | 240.17 | 227.69 | 5.20% |
| 2023-08-26 | 241.87 | 227.85 | 5.80% |
| 2023-09-02 | 241.76 | 228.00 | 5.69% |
| 2023-09-09 | 243.39 | 228.16 | 6.25% |
| 2023-09-16 | 239.98 | 228.32 | 4.86% |
| 2023-09-23 | 237.54 | 228.48 | 3.81% |
| 2023-09-30 | 228.08 | 228.64 | 0.24% |
| 2023-10-07 | 226.92 | 228.78 | 0.82% |
| **Promedio Final** | | | **MAPE = 7.0%**[cite: 3] |

---

### Tabla 2: Pronóstico Oficial a 12 Meses (52 Observaciones Semanales hasta Octubre de 2026)
*Proyección continua oficial basada en los datos de la imagen y la hoja de cálculo.*

| Fecha (Semanal) | IPAP Pronosticado | Límite Inferior | Límite Superior |
| :--- | :--- | :--- | :--- |
| 18/10/2025 | 248.319986 | 204.99 | 291.65 |
| 25/10/2025 | 248.521829 | 204.96 | 292.08 |
| 01/11/2025 | 248.723672 | 204.94 | 292.51 |
| 08/11/2025 | 248.925515 | 204.92 | 292.93 |
| 15/11/2025 | 249.127358 | 204.90 | 293.36 |
| 22/11/2025 | 249.329200 | 204.88 | 293.78 |
| 29/11/2025 | 249.531043 | 204.86 | 294.20 |
| 06/12/2025 | 249.732886 | 204.84 | 294.62 |
| 13/12/2025 | 249.934729 | 204.82 | 295.05 |
| 20/12/2025 | 250.136572 | 204.81 | 295.47 |
| 27/12/2025 | 250.338415 | 204.79 | 295.89 |
| 03/01/2026 | 250.540258 | 204.77 | 296.31 |
| 10/01/2026 | 250.742101 | 204.76 | 296.73 |
| 17/01/2026 | 250.943944 | 204.74 | 297.15 |
| 24/01/2026 | 251.145787 | 204.73 | 297.56 |
| 31/01/2026 | 251.347630 | 204.71 | 297.98 |
| 07/02/2026 | 251.549473 | 204.70 | 298.40 |
| 14/02/2026 | 251.751316 | 204.69 | 298.81 |
| 21/02/2026 | 251.953159 | 204.68 | 299.23 |
| 28/02/2026 | 252.155002 | 204.67 | 299.64 |
| 07/03/2026 | 252.356845 | 204.66 | 300.06 |
| 14/03/2026 | 252.558688 | 204.65 | 300.47 |
| 21/03/2026 | 252.760531 | 204.64 | 300.89 |
| 28/03/2026 | 252.962374 | 204.63 | 301.30 |
| 04/04/2026 | 253.164217 | 204.62 | 301.71 |
| 11/04/2026 | 253.366060 | 204.61 | 302.12 |
| 18/04/2026 | 253.567902 | 204.60 | 302.53 |
| 25/04/2026 | 253.769745 | 204.60 | 302.94 |
| 02/05/2026 | 253.971588 | 204.59 | 303.35 |
| 09/05/2026 | 254.173431 | 204.58 | 303.76 |
| 16/05/2026 | 254.375274 | 204.58 | 304.17 |
| 23/05/2026 | 254.577117 | 204.57 | 304.58 |
| 30/05/2026 | 254.778960 | 204.57 | 304.99 |
| 06/06/2026 | 254.980803 | 204.57 | 305.40 |
| 13/06/2026 | 255.182646 | 204.56 | 305.80 |
| 20/06/2026 | 255.384489 | 204.56 | 306.21 |
| 27/06/2026 | 255.586332 | 204.56 | 306.62 |
| 04/07/2026 | 255.788175 | 204.56 | 307.02 |
| 11/07/2026 | 255.990018 | 204.55 | 307.43 |
| 18/07/2026 | 256.191861 | 204.55 | 307.83 |
| 25/07/2026 | 256.393704 | 204.55 | 308.24 |
| 01/08/2026 | 256.595547 | 204.55 | 308.64 |
| 08/08/2026 | 256.797390 | 204.55 | 309.04 |
| 15/08/2026 | 256.999233 | 204.55 | 309.45 |
| 22/08/2026 | 257.201076 | 204.55 | 309.85 |
| 29/08/2026 | 257.402919 | 204.56 | 310.25 |
| 05/09/2026 | 257.604762 | 204.56 | 310.65 |
| 12/09/2026 | 257.806604 | 204.56 | 311.05 |
| 19/09/2026 | 258.008447 | 204.56 | 311.45 |
| 26/09/2026 | 258.210290 | 204.57 | 311.86 |
| 03/10/2026 | 258.412133 | 204.57 | 312.26 |
| **07/10/2026 (Cierre)** | **258.527472** | **204.57** | **312.48** |[cite: 3]

---

## 4. Estructura y Reproducibilidad del Repositorio
* **`Concurso.xlsx`**: Datos oficiales, tablas de validación histórica (MAPE) y la proyección oficial a octubre de 2026[cite: 3].
* **`Resultados_GARCH_Indices.xlsx`**: Consolidado paramétrico de los modelos GARCH ($\mu$, $\omega$, $\alpha$, $\beta$, persistencia, AIC y BIC) para cada subsector.
* **`untitled6.py`**: Script automatizado en Python que ejecuta la ingesta, las gráficas de series temporales, la estimación de volatilidad con la librería `arch` y la exportación de resultados.
* **`Presentacion_Ejecutiva_RetoB.pdf`**: Pitch deck ejecutivo de 5 diapositivas alineado con la sustentación oficial[cite: 3].

### ¿Cómo replicar el análisis?
1. Clone o descargue este repositorio.
2. Asegúrese de tener el archivo `Concurso.xlsx` en la misma carpeta que el código.
3. Ejecute el script `untitled6.py` en Google Colab o en su entorno local de Python para generar automáticamente las gráficas y el archivo de resultados GARCH.
