<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue"/> <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white"/> <img src="https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white"/> <img src="https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white"/>


# Predicción de Precios de Propiedades en Argentina

## Descripción del Proyecto

Este proyecto tiene como objetivo desarrollar un modelo de machine learning para predecir el precio de propiedades en Argentina. Se utilizará un dataset de propiedades en venta en Argentina, el cual será procesado y limpiado para luego ser utilizado en el entrenamiento del modelo.

## Pasos Realizados

1. **Carga de Datos y Librerías:** Se importaron las librerías necesarias (pandas, matplotlib, seaborn) y se cargó el dataset de propiedades en un DataFrame de pandas.
2. **Limpieza de Datos:** Se realizaron las siguientes tareas de limpieza de datos:
    - Eliminación de columnas irrelevantes como 'id', 'title', 'description', 'l6', 'ad_type', 'created_on'.
    - Renombrado de columnas para mayor claridad (e.g., 'l1' a 'pais', 'l2' a 'provincia', etc.).
    - Eliminación de entradas que no corresponden a Argentina.
    - Eliminación de entradas con valores nulos en la columna 'currency'.
    - Eliminación de la columna 'pais' ya que solo quedaron datos de Argentina.
    - Eliminación de entradas con valores 'Alquiler' y 'Alquiler temporal' en la columna 'operation_type'.
    - Eliminación de la columna 'operation_type'.
    - Eliminación de la columna 'price_period'.
    - Eliminación de entradas con valores como 'Lote', 'Otro', 'Cochera', etc. en la columna 'property_type'.
    - Eliminación de entradas con valores NaN en las columnas 'lat' y 'lon'.
    - Conversión de las columnas 'rooms', 'bedrooms', 'bathrooms', y 'price' a tipo entero.
    - Unificación de criterios en la columna 'provincia' para que solo queden las provincias sin detallar zonas.
    - Conversión de las columnas 'start_date' y 'end_date' a formato DATE.
    - Unificación de la moneda a dólares utilizando la cotización del día.
    - Eliminación de valores de latitud y longitud que no estén comprendidos entre los límites de Argentina.
3. **Análisis Exploratorio de Datos:** Se realizó un análisis exploratorio de los datos para entender la distribución de las variables y las relaciones entre ellas. **Este análisis incluirá la detección y tratamiento de outliers, así como la creación de gráficos de distribución para las variables relevantes.**
4. **Visualización de Datos:** Se graficaron los puntos en un mapa político de Argentina para visualizar la distribución geográfica de las propiedades.

## Hipótesis para un Modelo de Machine Learning

Las siguientes son algunas hipótesis que se pueden utilizar para desarrollar un modelo de machine learning para predecir el precio de una propiedad:

1. **Ubicación:** La ubicación de la propiedad es un factor clave en su precio. Se puede utilizar la latitud y longitud, la provincia, el partido y la comuna para predecir el precio.
2. **Tamaño:** El tamaño de la propiedad, medido en metros cuadrados o en cantidad de ambientes, también es un factor importante. Se pueden utilizar las columnas 'surface_total_in_m2', 'surface_covered_in_m2', 'rooms', 'bedrooms', y 'bathrooms' para predecir el precio.
3. **Tipo de Propiedad:** El tipo de propiedad (casa, departamento, etc.) también influye en el precio. Se puede utilizar la columna 'property_type' para predecir el precio.
4. **Características Adicionales:** Otras características como la presencia de amenities (pileta, gimnasio, etc.) pueden influir en el precio.


## Próximos Pasos

1. **Análisis de Outliers y Gráficos de Distribución:** Realizar un análisis de outliers y generar gráficos de distribución para las variables relevantes.
2. **Selección de Modelo:** Evaluar diferentes modelos de machine learning (regresión lineal, árboles de decisión, etc.) y seleccionar el que mejor se adapte a los datos.
3. **Entrenamiento y Evaluación del Modelo:** Entrenar el modelo seleccionado con los datos y evaluar su rendimiento utilizando métricas como el error cuadrático medio (RMSE).
4. **Despliegue del Modelo:** Desplegar el modelo para que pueda ser utilizado para predecir el precio de nuevas propiedades.
