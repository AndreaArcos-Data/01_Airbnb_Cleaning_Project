# Proyecto de limpieza y modelado de precios de Airbnb NYC 2019
Análisis Exploratorio · Limpieza Avanzada · Ingeniería de Características · Modelos Predictivos

Este proyecto forma parte del portafolio de análisis y limpieza de datos.
El objetivo es preparar y modelar un dataset real de Airbnb para predecir el precio de los alojamientos en la ciudad de Nueva York.

# Objetivos del proyecto 
- Realizar una limpieza completa del dataset original.
- Detectar y corregir valores nulos, outliers y formatos incorrectos.
- Crear variables nuevas (feature engineering).
- Aplicar codificación categórica, escalamiento y preparación final para modelado.
- Entrenar y comparar varios modelos:
  1. Regresión Lineal
  2. Random Forest
  3. Gradient Boosting
  4. XGBoost (baseline y mejorado con feature engineering)
Seleccionar el mejor modelo según:

1. MAE (Mean Absolute Error)
2. RMSE (Root Mean Squared Error)
3. R² (coeficiente de determinación)

   # Limpieza de datos (Notebook 1)
   - Eliminación de columnas irrelevantes
   - Conversión de variables de fecha y numéricas
   - tratamiento de valores nulos ![Valores nulos](figures/mapa_nulos.png)
  
  # Detección y tratamiento de outliers 
  Se revisaron variables numéricas clave:
- price
- minimum_nights
- number_of_reviews
- reviews_per_month
- availability_365

  Métodos aplicados:
✔ Winsorización
✔ Topes superiores para valores extremos
✔ Transformación logarítmica
![Distribución del precio](figures/distribucion_price.png)

# Variables categóricas 
✔ Reducción de cardinalidad en neighbourhood
Agrupación de barrios con <100 registros en una sola categoría "Other".

✔ One-Hot Encoding
Aplicado para:
- room_type
- neighbourhood_group
- neighbourhood_simplified

Resultado final: 79 columnas para modelado

 # MODELADO (Notebook 2)
# Preparación de datos 
- distribución de datos en prueba y entrenamiento.
- Modelo para determinar características e importancia de las variables
- Eliminación de variables
  ![Random Forest Feature Importance](figures/feature_importance_rf.png)

# Modelos 
  1. Regresión Lineal
  2. Random Forest
  3. Gradient Boosting
  4. XGBoost (baseline y mejorado con feature engineering)
     [Resultados distintos modelos](figures/resultados_modelos_tabla.png)
   
# Ingeniería de Características (Feature Engineering)
Se añadió la variable Distancia al Times Square usando fórmula de Haversine

# Conclusiones 
- La regresión lineal sirve únicamente como modelo base
- Los modelo basados en árboles mejoran considerablemente el modelo
- XGBoost es el mejor modelo, como se esperaba, debido a que es capaz de capturar patrones de mayor complejidad.
- Aumentar la variable de distancia no mejora el modelo, puede deberse a la redundancia de la infoamción que captura la nueva variable, con la que ya existe en las variables de barrios o las variables espaciales.

  # Autor
  Andrea Arcos
  aarcos.47@gmail.com 
