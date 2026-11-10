# Experimento A/B de una landing page

Quería responder una pregunta sencilla: **¿vale la pena cambiar la versión A de una página por la B?** Para hacerlo, analicé los datos de 40,000 usuarios y comparé conversiones, gasto e ingreso por usuario.

## Lo más importante

| Indicador | Versión A | Versión B |
|---|---:|---:|
| Usuarios | 19,982 | 20,018 |
| Tasa de conversión | 12.57 % | 15.96 % |
| Gasto promedio entre compradores | 61.09 | 68.75 |
| **Ingreso por usuario expuesto** | **7.68** | **10.97** |

La versión B generó **3.29 unidades monetarias más por usuario expuesto** (+42.8 %). El intervalo de confianza del 95 % para la diferencia fue de **2.79 a 3.79** unidades; la prueba t de Welch dio *p* < 0.001. La diferencia en conversión también fue estadísticamente significativa (*p* < 0.001).

**Mi conclusión:** B es la mejor candidata, pero antes de implementarla revisaría la asignación de los usuarios y posibles efectos en otras métricas. El dataset no especifica la moneda, por lo que hablo de unidades monetarias.

## Qué analicé

- **Conversión entre A y B:** prueba Z de dos proporciones.
- **Gasto entre quienes compraron:** prueba t de Welch.
- **Ingreso por usuario expuesto:** promedio, prueba t de Welch e intervalo de confianza del 95 %.
- **Fuente de tráfico y tipo de usuario:** pruebas chi-cuadrada y gráficos comparativos.

Encontré una asociación pequeña entre fuente de tráfico y conversión (*p* = 0.034). En cambio, no encontré evidencia de asociación entre el tipo de usuario y la conversión (*p* = 0.474). No tomaría decisiones de inversión por canal sin conocer también los costos.

## Herramientas

Python, pandas, NumPy, SciPy, statsmodels, matplotlib, seaborn y Jupyter Notebook.

## Archivos y reproducción

- `Landing_AB_Analysis.ipynb`: notebook con el análisis, las pruebas y las conclusiones.
- `requirements.txt`: dependencias del proyecto.

El archivo `landing_experiment.csv` se utilizó para calcular y verificar los resultados, pero **no se publica** con este repositorio. Para ejecutar el notebook con una copia autorizada, colócala junto al notebook o en `data/landing_experiment.csv`, instala las dependencias con `pip install -r requirements.txt` y ejecuta las celdas en orden.

Proyecto desarrollado durante mi formación en análisis de datos en TripleTen. Los resultados corresponden a un ejercicio con datos de práctica, no a un experimento realizado para una empresa real.
