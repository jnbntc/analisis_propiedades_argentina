<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue"/> <img src="https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white"/> <img src="https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white"/>

# README: Predicción de Precios de Propiedades en Argentina

Este repositorio contiene un modelo de machine learning para predecir el precio de propiedades en Argentina utilizando un conjunto de datos de propiedades y tasas de cambio históricas. A continuación, se detalla el análisis realizado y las conclusiones.

---

## **Descripción del Proyecto**

El objetivo de este proyecto es predecir el precio de propiedades en Argentina utilizando técnicas de machine learning. El modelo se basa en un conjunto de datos que incluye características como la ubicación, el tamaño de la propiedad, el número de habitaciones, baños, y otros atributos relevantes. Además, se utilizan datos históricos de tasas de cambio para convertir los precios a dólares estadounidenses.

---

## **Análisis y Conclusiones**

### **1. Preprocesamiento de Datos**
- **Limpieza de Datos**: Se eliminaron columnas irrelevantes y se filtraron las propiedades que no pertenecen a Argentina. También se eliminaron valores nulos en columnas clave como `currency`, `lat`, `lon`, `rooms`, `bedrooms`, `bathrooms`, `surface_total`, y `surface_covered`.
- **Transformación de Variables**: Se convirtieron las fechas a formato `datetime` y se normalizaron los precios a dólares utilizando tasas de cambio históricas.
- **Eliminación de Outliers**: Se aplicó el método IQR para eliminar valores atípicos en las columnas numéricas, mejorando la calidad del dataset.

### **2. Modelos Implementados**
Se implementaron y evaluaron varios modelos de machine learning:

- **Random Forest**: 
  - **MSE**: 2,820,812,421.91
  - **RMSE**: 53,111.32
  - **R²**: 0.600
  - **Conclusión**: Un buen rendimiento inicial, con un R² que indica que el modelo explica aproximadamente el 60% de la variabilidad en los precios.

- **XGBoost**:
  - **MSE**: 2,718,002,176.00
  - **RMSE**: 52,134.46
  - **R²**: 0.615
  - **Conclusión**: Mejoró ligeramente el rendimiento respecto a Random Forest, especialmente después de la optimización de hiperparámetros.

- **LightGBM**:
  - **MSE**: 2,845,805,956.26
  - **RMSE**: 53,346.10
  - **R²**: 0.597
  - **Conclusión**: Aunque no superó a XGBoost, LightGBM demostró ser eficiente en términos de velocidad y manejo de grandes volúmenes de datos.

- **CatBoost**:
  - **MSE**: 2,971,299,388.90
  - **RMSE**: 54,509.63
  - **R²**: 0.579
  - **Conclusión**: CatBoost tuvo un rendimiento ligeramente inferior, pero su manejo automático de variables categóricas lo hace atractivo para futuras iteraciones.

### **3. Conclusiones Generales**
- **Fuerzas del Modelo**:
  - **Precisión Aceptable**: El modelo XGBoost logró un R² de 0.615, lo que indica que explica aproximadamente el 61.5% de la variabilidad en los precios de las propiedades.
  - **Optimización de Hiperparámetros**: La optimización de hiperparámetros mejoró significativamente el rendimiento de XGBoost, reduciendo el RMSE en comparación con Random Forest.
  - **Escalabilidad**: LightGBM y XGBoost demostraron ser escalables y eficientes para grandes volúmenes de datos.
