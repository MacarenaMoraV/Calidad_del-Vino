# 🍷 Predicción de la Calidad del Vino

Este proyecto busca predecir la calidad del vino a partir de distintas variables fisicoquímicas. Se realiza una limpieza rigurosa de los datos, análisis exploratorio, visualización, selección de características, y entrenamiento de modelos de clasificación.

## 📁 Dataset

- **Fuente:** [Wine Quality Dataset – Kaggle](https://www.kaggle.com/datasets/yasserh/wine-quality-dataset)
- **Archivo usado:** `WineQT.csv`
- **Muestras:** 1143 
- **Variables:** 11 variables fisicoquímicas + 1 variable objetivo (`quality`)

## 🛠️ Tecnologías y Librerías

- Python 3 (Google Colab)
- pandas, numpy
- seaborn, matplotlib
- scikit-learn

## 🧪 Etapas del proyecto

### 1. Carga y limpieza de datos
- Sin datos nulos ni variables categóricas.
- Eliminación de la columna `Id` por no aportar valor analítico.
- Detección y tratamiento de outliers en `free sulfur dioxide` y `total sulfur dioxide`

### 2. Análisis exploratorio (EDA)
- Estadísticas descriptivas.
- Boxplots de variables con outliers.
- Distribución de la variable `quality`, con mayoría de vinos de calidad media (5 y 6).
- Matriz de correlación: las variables más correlacionadas con `quality` fueron:
  - `alcohol` (0.48)
  - `sulphates` (0.26)
  - `citric acid` (0.24)
  - `fixed acidity` (0.12)

### 3. Selección de características
- Variables seleccionadas para modelar:
  - `alcohol`, `sulphates`, `citric acid`, `fixed acidity`

### 4. Modelado
- División de los datos en entrenamiento (80%) y test (20%) con `stratify`.
- Modelos utilizados:
  - `KNeighborsClassifier`
  - `RandomForestClassifier`
  - `LogisticRegression`
- Normalización de features, revision de hiperparámetros con `GridSearchCV`
  
### 5. Métricas de evaluación
- **Random Forest**:
  - CV Score: 62.7%
  - Test Accuracy: 66.4%
- **KNN**:
  - CV Score: 62.0%
  - Test Accuracy: 65.9%
- **Logistic Regression**:
  - CV Score: 56.9%
  - Test Accuracy: 61.6%

## ✅ Conclusiones

- **Random Forest** fue el modelo con mejor rendimiento, seguido de cerca por **KNN**.
- **Regresión Logística** tuvo menor desempeño, probablemente por la no linealidad de las relaciones.
- El análisis permitió identificar las variables más relevantes y aplicar un enfoque sólido de clasificación.

---

**Autor:** Macarena Mora V.  
**Fecha:** Julio 2025 
