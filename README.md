# ASpectrum - Reto B: Pronóstico del IPAP-BMC

## 1. Descripción del Proyecto
Sistema predictivo y de gestión de riesgo para el índice **IPAP-BMC** de la Bolsa Mercantil de Colombia, desarrollado por el equipo **ASpectrum** como parte del DataLab Challenge. Su objetivo es anticipar la tendencia del mercado agropecuario y medir la volatilidad para optimizar la toma de decisiones y las coberturas financieras.

## 2. Principales Resultados Cuantitativos y Econométricos
* **Validación Histórica (MAPE):** Se alcanzó un desempeño sobresaliente con un error porcentual absoluto medio del **7%** en la prueba histórica de los últimos 12 meses.
* **Poder Explicativo ($R^2$):** El modelo econométrico base logra un coeficiente de determinación ajustado del **98.18%**, capturando de manera efectiva la estacionalidad extrema del sector agropecuario.
* **Persistencia de la Volatilidad (GARCH):** A través de la modelación GARCH(1,1), se identificó que la suma de los coeficientes $\alpha + \beta$ es extremadamente cercana a 1 (superando 0.99 en índices clave como *IP_agroipe* y *lechem*). Esto demuestra que los choques de precios en el agro **son altamente persistentes en el tiempo**, justificando la urgencia de utilizar instrumentos de cobertura en la Bolsa Mercantil.

## 3. Estructura del Repositorio
* **`Concurso.xlsx`**: Datos oficiales, tablas de validación histórica (MAPE) y la proyección oficial a octubre de 2026.
* **`Resultados_GARCH_Indices.xlsx`**: Consolidado paramétrico de los modelos GARCH ($\mu$, $\omega$, $\alpha$, $\beta$, persistencia, AIC y BIC) para cada subsector.
* **`untitled6.py`**: Script automatizado en Python que ejecuta la ingesta, las gráficas de series temporales, la estimación de volatilidad con la librería `arch` y la exportación de resultados.
* **`Presentacion_Ejecutiva_RetoB.pdf`**: Pitch deck ejecutivo de 5 diapositivas alineado con la sustentación oficial.

## 4. Enlace del Video Pitch y Reproducibilidad
* **Video de sustentación (Duración: < 3 min):** (https://drive.google.com/file/d/18LqGwvHljl7K2bJVizAL4wxkNkPj1Obw/view?usp=sharing)

### ¿Cómo replicar el análisis?
1. Clone o descargue este repositorio.
2. Asegúrese de tener el archivo `Concurso.xlsx` en la misma carpeta que el código.
3. Ejecute el script `untitled6.py` en Google Colab o en su entorno local de Python para generar automáticamente las gráficas y el archivo de resultados GARCH.
