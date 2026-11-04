# ASpectrum - Reto B: Pronóstico del IPAP-BMC

## 1. Descripción del Proyecto
Sistema predictivo y de gestión de riesgo para el índice **IPAP-BMC** de la Bolsa Mercantil de Colombia, desarrollado por el equipo **ASpectrum** como parte del DataLab Challenge. Su objetivo es anticipar la tendencia del mercado agropecuario y medir la volatilidad para optimizar la toma de decisiones y las coberturas financieras.

## 2. Principales Resultados Cuantitativos y Econométricos
* **Validación Histórica (MAPE):** Se alcanzó un desempeño sobresaliente con un error porcentual absoluto medio del **7%** en la prueba histórica de los últimos 12 meses.
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
| **Promedio Final** | | | **MAPE = 7.0%** |

---

### Tabla 2: Pronóstico Oficial a 12 Meses (52 Observaciones Semanales hasta Octubre de 2026)
*Proyección continua completa del modelo econométrico con periodicidad semanal*

| Fecha (Semanal) | IPAP Pronosticado | Límite Inferior | Límite Superior |
| :--- | :--- | :--- | :--- |
| 2025-10-18 | 227.93 | 219.01 | 236.85 |
| 2025-10-25 | 228.14 | 218.42 | 237.85 |
| 2025-11-01 | 228.34 | 217.91 | 238.77 |
| 2025-11-08 | 228.55 | 217.47 | 239.62 |
| 2025-11-15 | 228.75 | 217.08 | 240.42 |
| 2025-11-22 | 228.95 | 216.73 | 241.17 |
| 2025-11-29 | 229.16 | 216.41 | 241.90 |
| 2025-12-06 | 229.36 | 216.12 | 242.60 |
| 2025-12-13 | 229.56 | 215.86 | 243.27 |
| 2025-12-20 | 229.77 | 215.61 | 243.92 |
| 2025-12-27 | 229.97 | 215.39 | 244.55 |
| 2026-01-03 | 230.17 | 215.18 | 245.16 |
| 2026-01-10 | 230.38 | 214.99 | 245.76 |
| 2026-01-17 | 230.58 | 214.81 | 246.34 |
| 2026-01-24 | 230.79 | 214.65 | 246.92 |
| 2026-01-31 | 230.99 | 214.50 | 247.48 |
| 2026-02-07 | 231.19 | 214.36 | 248.03 |
| 2026-02-14 | 231.40 | 214.23 | 248.56 |
| 2026-02-21 | 231.60 | 214.11 | 249.09 |
| 2026-02-28 | 231.80 | 214.00 | 249.60 |
| 2026-03-07 | 232.01 | 213.90 | 250.11 |
| 2026-03-14 | 232.21 | 213.81 | 250.61 |
| 2026-03-21 | 232.41 | 213.72 | 251.10 |
| 2026-03-28 | 232.62 | 213.64 | 251.59 |
| 2026-04-04 | 232.82 | 213.57 | 252.07 |
| 2026-04-11 | 233.02 | 213.50 | 252.54 |
| 2026-04-18 | 233.23 | 213.43 | 253.02 |
| 2026-04-25 | 233.43 | 213.38 | 253.48 |
| 2026-05-02 | 233.64 | 213.32 | 253.95 |
| 2026-05-09 | 233.84 | 213.27 | 254.40 |
| 2026-05-16 | 234.04 | 213.23 | 254.85 |
| 2026-05-23 | 234.25 | 213.19 | 255.30 |
| 2026-05-30 | 234.45 | 213.15 | 255.75 |
| 2026-06-06 | 234.65 | 213.12 | 256.19 |
| 2026-06-13 | 234.86 | 213.10 | 256.62 |
| 2026-06-20 | 235.06 | 213.08 | 257.05 |
| 2026-06-27 | 235.26 | 213.06 | 257.47 |
| 2026-07-04 | 235.47 | 213.04 | 257.90 |
| 2026-07-11 | 235.67 | 213.03 | 258.31 |
| 2026-07-18 | 235.87 | 213.02 | 258.73 |
| 2026-07-25 | 236.08 | 213.01 | 259.14 |
| 2026-08-01 | 236.28 | 213.01 | 259.55 |
| 2026-08-08 | 236.48 | 213.01 | 259.95 |
| 2026-08-15 | 236.69 | 213.01 | 260.36 |
| 2026-08-22 | 236.89 | 213.01 | 260.76 |
| 2026-08-29 | 237.10 | 213.01 | 261.18 |
| 2026-09-05 | 237.30 | 213.02 | 261.58 |
| 2026-09-12 | 237.50 | 213.03 | 261.98 |
| 2026-09-19 | 237.71 | 213.04 | 262.38 |
| 2026-09-26 | 237.91 | 213.05 | 262.77 |
| 2026-10-03 | 238.11 | 213.07 | 263.16 |
| **2026-10-07 (Cierre)** | **238.28** | **213.08** | **263.48** |

---

## 4. Estructura y Reproducibilidad del Repositorio
* **`Concurso.xlsx`**: Datos oficiales, tablas de validación histórica (MAPE) y la proyección oficial a octubre de 2026.
* **`Resultados_GARCH_Indices.xlsx`**: Consolidado paramétrico de los modelos GARCH ($\mu$, $\omega$, $\alpha$, $\beta$, persistencia, AIC y BIC) para cada subsector.
* **`untitled6.py`**: Script automatizado en Python que ejecuta la ingesta, las gráficas de series temporales, la estimación de volatilidad con la librería `arch` y la exportación de resultados.
* **`Presentacion_Ejecutiva_RetoB.pdf`**: Pitch deck ejecutivo de 5 diapositivas alineado con la sustentación oficial.

### ¿Cómo replicar el análisis?
1. Clone o descargue este repositorio.
2. Asegúrese de tener el archivo `Concurso.xlsx` en la misma carpeta que el código.
3. Ejecute el script `untitled6.py` en Google Colab o en su entorno local de Python para generar automáticamente las gráficas y el archivo de resultados GARCH.
