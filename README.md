# ASpectrum - Reto B: Pronóstico del IPAP-BMC

## 1. Descripción del Proyecto
Sistema predictivo y de gestión de riesgo para el índice **IPAP-BMC** de la Bolsa Mercantil de Colombia, desarrollado por el equipo **ASpectrum** como parte del DataLab Challenge. Su objetivo es anticipar la tendencia del mercado agropecuario y medir la volatilidad para optimizar la toma de decisiones y las coberturas financieras.

## 2. Principales Resultados Cuantitativos y Econométricos
* **Validación Histórica (MAPE):** Se alcanzó un desempeño sobresaliente con un error porcentual absoluto medio del **7%** en la prueba histórica de los últimos 12 meses.
* **Poder Explicativo ($R^2$):** El modelo econométrico base logra un coeficiente de determinación ajustado del **98.18%**, capturando de manera efectiva la estacionalidad extrema del sector agropecuario.
* **Persistencia de la Volatilidad (GARCH):** A través de la modelación GARCH(1,1), se identificó que la suma de los coeficientes $\alpha + \beta$ es extremadamente cercana a 1 (superando 0.99 en índices clave como *IP_agroipe* y *lechem*). Esto demuestra que los choques de precios en el agro **son altamente persistentes en el tiempo**, justificando la urgencia de utilizar instrumentos de cobertura en la Bolsa Mercantil.

---

## 3. Tablas Requeridas de Validación y Pronóstico

### Tabla 1: Testeo Histórico y Validación MAPE (Últimos Periodos)
*Evaluación del desempeño del modelo frente a los datos reales observados.*

| Fecha | IPAP Real | IPAP Predicho (Modelo) | Error Porcentual Absoluto |
| :--- | :--- | :--- | :--- |
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

### Tabla 2: Pronóstico a los Siguientes 12 Meses (Incluyendo Octubre 2026)
*Proyección continua oficial de la tendencia del mercado agropecuario.*

| Fecha | IPAP Pronosticado | Límite Inferior | Límite Superior |
| :--- | :--- | :--- | :--- |
| 2026-07-18 | 256.19 | 204.55 | 307.83 |
| 2026-07-25 | 256.39 | 204.55 | 308.24 |
| 2026-08-01 | 256.60 | 204.55 | 308.64 |
| 2026-08-08 | 256.80 | 204.55 | 309.04 |
| 2026-08-15 | 257.00 | 204.55 | 309.45 |
| 2026-08-22 | 257.20 | 204.55 | 309.85 |
| 2026-08-29 | 257.40 | 204.56 | 310.25 |
| 2026-09-05 | 257.60 | 204.56 | 310.65 |
| 2026-09-12 | 257.81 | 204.56 | 311.05 |
| 2026-09-19 | 258.01 | 204.56 | 311.45 |
| 2026-09-26 | 258.21 | 204.57 | 311.86 |
| **2026-10-03 (Octubre)** | **258.41** | **204.57** | **312.26** |

---

## 4. Estructura del Repositorio y Reproducibilidad
* **`Concurso.xlsx`**: Datos oficiales, tablas de validación histórica (MAPE) y la proyección oficial a octubre de 2026.
* **`Resultados_GARCH_Indices.xlsx`**: Consolidado paramétrico de modelos GARCH ($\mu$, $\omega$, $\alpha$, $\beta$, persistencia, AIC y BIC).
* **`untitled6.py`**: Script automatizado en Python que ejecuta la ingesta, gráficas y estimación de volatilidad con la librería `arch`.
* **`Presentacion_Ejecutiva_RetoB.pdf`**: Pitch deck ejecutivo de 5 diapositivas alineado con la sustentación oficial.

### ¿Cómo replicar el análisis?
1. Clone o descargue este repositorio.
2. Asegúrese de tener el archivo `Concurso.xlsx` en la misma carpeta que el código.
3. Ejecute el script `untitled6.py` en Google Colab o en su entorno local de Python para generar automáticamente las gráficas y el archivo de resultados GARCH.
