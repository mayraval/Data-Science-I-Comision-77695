# Proyecto Final – Análisis de Rendimiento Estudiantil

## Comisión
77695  

## Autora
- Mayra Belen Lopez  

## Descripción
El presente proyecto se centra en el análisis del conjunto de datos **Students Performance in Exams**, disponible en Kaggle.  
Este dataset contiene información sobre el desempeño académico de 1000 estudiantes en tres asignaturas:  
- Matemáticas (`math score`)  
- Lectura (`reading score`)  
- Escritura (`writing score`)  

Además, incluye variables contextuales y demográficas:  
- Género (`gender`)  
- Grupo étnico (`race/ethnicity`)  
- Nivel educativo de los padres (`parental level of education`)  
- Tipo de almuerzo (`lunch`)  
- Curso de preparación para el examen (`test preparation course`)  

El objetivo principal es explorar cómo estas variables influyen en el puntaje de escritura y entrenar modelos predictivos que permitan identificar los factores más determinantes.

---

## Objetivos del Proyecto
1. Analizar la distribución de los puntajes y variables contextuales.  
2. Aplicar técnicas de **feature selection** para reducir dimensionalidad y elegir las variables más relevantes.  
3. Entrenar y evaluar modelos predictivos:  
   - Regresión Lineal  
   - Random Forest  
   - Gradient Boosting  
4. Evaluar los modelos con métricas: **MSE**, **MAE** y **R²**.  
5. Generar conclusiones sobre los factores más importantes que afectan el puntaje en escritura.

---

## Contenido del Repositorio
```
ProyectoFinal/
│
├─ data/
│   └─ StudentsPerformance.csv       # Dataset original
│
├─ notebooks/
│   └─ ProyectoFinal_Analisis_Rendimiento.ipynb   # Notebook principal
│
├─ resultados/
│   ├─ feature_selection_summary.csv
│   ├─ perm_importance_rf.csv
│   ├─ predicciones_modelos.csv
│   └─ conclusiones.txt
│
└─ README.md
```

---

## Librerías Utilizadas
- `pandas`  
- `numpy`  
- `matplotlib`  
- `seaborn`  
- `scikit-learn`  
- `os`  

---

## Metodología

### 1. Análisis Exploratorio
- **Univariado:** histogramas para `math score`, `reading score` y `writing score`.  
- **Bivariado:** boxplots por género para cada asignatura.  
- **Trivariado:** scatterplot entre `math score` y `reading score` con tamaño por `writing score`.  
- **Correlación:** heatmap entre las tres asignaturas.  

### 2. Preparación de Datos
- Codificación de variables categóricas con `pd.get_dummies()`.  
- Escalado de variables numéricas con `StandardScaler`.  
- División de dataset en **train (80%)** y **test (20%)**.

### 3. Feature Selection
- **Correlación absoluta** con el target (`writing score`).  
- **SelectKBest** con función `f_regression`.  
- **LassoCV** para identificar variables con coeficientes significativos.  

### 4. Modelado Predictivo
- **Regresión Lineal:** baseline.  
- **Random Forest Regressor:** manejo de outliers y dispersión.  
- **Gradient Boosting Regressor:** optimización de errores y R².  

### 5. Evaluación de Modelos
- Métricas usadas: **MSE**, **MAE**, **R²**.  
- Importancia de features mediante **Permutation Importance**.  
- Análisis de residuos para verificar dispersión y sesgos.

---

## Resultados Principales

1. Las variables **`reading score`** y **`math score`** son las más predictivas del puntaje en escritura.  
2. Random Forest y Gradient Boosting superan a Regresión Lineal en R² y errores.  
3. Variables contextuales como género, nivel educativo y preparación aportan, pero en menor medida.  
4. Análisis descriptivo puro (histogramas) muestra distribución, pero no refleja influencia real sobre escritura.  
5. La importancia de `reading score` es consistente entre Lasso, SelectKBest y Permutation Importance.

---

## Conclusiones
- El puntaje en lectura está fuertemente correlacionado con escritura, por lo que domina en los modelos de machine learning.  
- La preparación y contexto educativo son factores secundarios pero significativos.  
- Modelos basados en árboles (Random Forest y Gradient Boosting) manejan mejor los outliers y la dispersión.  
- Para trabajos futuros, se recomienda explorar ensamblados más complejos y agregar más variables contextuales.

---

## Instrucciones para Ejecutar
1. Clonar el repositorio.  
2. Instalar librerías:  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
3. Ejecutar el notebook `ProyectoParteIII+Lopez.ipynb`.  
4. Los resultados se guardarán automáticamente en la carpeta `resultados/`.

---

## Referencias
- [Kaggle – Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)  
- [scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html)  
- [Seaborn Documentation](https://seaborn.pydata.org/)

---

## Autora
Mayra Belen Lopez  
2025
