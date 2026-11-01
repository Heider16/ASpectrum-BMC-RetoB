# ASpectrum-BMC-RetoB
Modelo econométrico y pronóstico del IPAP-BMC para el DataLab Challenge
# ASpectrum - Reto B: Pronóstico del IPAP-BMC

## 1. Descripción del Proyecto
Sistema predictivo y de gestión de riesgo para el índice **IPAP-BMC** de la Bolsa Mercantil de Colombia, desarrollado por el equipo **ASpectrum** como parte del DataLab Challenge. Su objetivo es anticipar la tendencia del mercado agropecuario y medir la volatilidad para optimizar la toma de decisiones y las coberturas financieras.

## 2. Componentes del Repositorio
* **`Concurso.xlsx`**: Archivo que contiene los datos oficiales, la tabla de validación histórica (con el cálculo del MAPE para los últimos 12 meses) y la proyección oficial a 12 meses (incluyendo octubre de 2026).
* **`untitled5.py`**: Script en Python / Google Colab que ejecuta la limpieza de datos, el análisis gráfico de series temporales y la modelación econométrica avanzada de volatilidad mediante **GARCH(1,1)**.
* **`Resultados_GARCH_Indices.xlsx`**: Consolidado de parámetros estimados (`mu`, `omega`, `alpha`, `beta`), persistencia de la volatilidad y criterios de información (AIC, BIC) para cada subsector.
* **`Presentacion_Final.pdf`**: Pitch deck ejecutivo de 5 diapositivas que resume el problema, la solución, la innovación y los beneficios para la BMC.

## 3. Principales Resultados Cuantitativos
* **Validación Histórica (MAPE):** Se alcanzó un desempeño sobresaliente con un error porcentual absoluto medio del **7%** en la prueba histórica de los últimos 12 meses.
* **Poder Explicativo ($R^2$):** El modelo econométrico base logra un coeficiente de determinación ajustado del **98.18%**, capturando de manera efectiva la estacionalidad extrema del sector agropecuario (como el subsector de flores).
* **Persistencia de la Volatilidad (GARCH):** Los modelos GARCH(1,1) revelan que la suma de $\alpha + \beta$ es cercana a 1 (ej. >0.99 en múltiples índices), lo que demuestra que los choques de precios son altamente persistentes y requieren herramientas activas de gestión de riesgos en la BMC.

## 4. Instrucciones de Reproducibilidad
1. Clone o descargue este repositorio.
2. Abra el archivo `Concurso.xlsx` para verificar las tablas de validación histórica y el pronóstico a 12 meses.
3. Ejecute el script `untitled5.py` en un entorno compatible con Python y la librería `arch` para replicar la estimación de los modelos GARCH de volatilidad.
