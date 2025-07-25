# Predicción del Estadio del Melanoma 🧬🧠

Este proyecto de Machine Learning tiene como objetivo predecir el **estadio del melanoma cutáneo (SKCM)**, uno de los cánceres de piel más agresivos, a partir de datos **clínicos** y **de expresión génica** de pacientes. Los datos fueron obtenidos del estudio [Skin Cutaneous Melanoma (TCGA, PanCancer Atlas)](https://www.cbioportal.org/study/summary?id=skcm_tcga_pan_can_atlas_2018), disponible en el portal [cBioPortal](https://www.cbioportal.org).

Este repositorio contiene tres enfoques de análisis: clínico, genético y completo (combinación de los dos).

---

## 📁 Estructura del Repositorio

 
  Notebooks de análisis y modelado:
  - `proyecto_EDA.ipynb` - análisis exploratorio de los datos
  - `proyecto_truetarget_clinico.ipynb` – análisis clínico
  - `proyecto_truetarget_genes.ipynb` – análisis de expresión genética
  - `proyecto_truetarget_completo.ipynb` – modelo completo

`README.md`  - Documentación del proyecto.

`environment.yml` - entorno para los notebooks.

---

## 🧾 Descripción del Proyecto

Este proyecto explora cómo los datos clínicos y genéticos pueden contribuir a entrenar modelos supervisados que predigan el estadio del cáncer.

Se han trabajado tres notebooks principales:

- `proyecto_truetarget_clinico.ipynb`: análisis y predicción usando solo datos clínicos.
- `proyecto_truetarget_genes.ipynb`: modelado usando expresión génica.
- `proyecto_truetarget_completo.ipynb`: combinación de ambos enfoques.

---

## 📊 Datos

- **Fuente:** [cBioPortal: SKCM - TCGA, PanCancer Atlas](https://www.cbioportal.org/study/summary?id=skcm_tcga_pan_can_atlas_2018)
- **Número de muestras:** ~470 pacientes con expresión de unos 20,000 genes.
- **Principales variables clínicas:**
    - Edad al diagnóstico
    - Sexo
    - Subtipo de melanoma
    - Estadio tumoral (AJCC)
    - Estado vital / supervivencia
    - Otros datos clínicos relevantes
- **Variables génicas:** Datos de expresión para ~20,000 genes por paciente.

---
## 🧠 Metodología

1. **Análisis Exploratorio (EDA)**
    - Limpieza y tratamiento de valores nulos.
    - Visualización de la distribución de estadios, edades, subtipos, etc.

2. **Procesamiento y reducción de dimensionalidad**
    - *PCA* para condensar los datos génicos.
    - *OneHotEncoding* y *StandardScaler* para clínicas.

3. **Modelado Supervisado**
    - Entrenamiento y comparación de modelos (Logistic Regression, Random Forest, Decision Tree, XGBoost, etc.) usando PyCaret.
    - Predicción: estadio del melanoma (avanzado/no avanzado).
    - Métricas principales: F1-score, matriz de confusión, classification report.

4. **Optimización**
    - Tuneo de hiperparámetros (PyCaret u Optuna).
    - Ajuste del umbral de decisión.

5. **Interpretabilidad**
    - Análisis de importancia de variables para identificar los genes y factores clínicos más relevantes.


---

## 🧪 Resultados Destacados

| Modelo               | F1-score | Precisión | Recall |
|----------------------|----------|-----------|--------|
| Clínico              | ~0.62    | ~0.59     | ~0.66  |
| Genético (PCA)       | **~0.66**    | **~0.60**     | **~0.73**  |
| Combinado            | ~0.63| ~0.54 | ~0.75  |


- La **Regresión Logística** mostró un buen rendimiento, especialmente con datos genéticos.
- Los datos clínicos por sí solos no permiten hacer buenas predicciones.
- Es mejor usar solamente los datos genéticos.

---

## 🚀 Cómo Usar este Proyecto

### 1. Clonar el repositorio

```bash
git clone https://github.com/helenaplans/prediccion-estadio-melanoma.git
cd prediccion-estadio-melanoma 
```
## 2. Entorno y dependencias

Para facilitar la instalación de todas las librerías y que los notebooks funcionen correctamente, se incluye un archivo `environment.yml` con el entorno Conda.

Para crear y activar el entorno, ejecuta:

```bash
conda env create -f environment.yml
conda activate melanoma_env
```

### 3. Ejecutar los notebooks

Abre los notebooks y ejecútalos en el siguiente orden:

  - `proyecto_EDA.ipynb` - análisis exploratorio de los datos
  - `proyecto_truetarget_clinico.ipynb` – análisis clínico y codificación de variables.
  - `proyecto_truetarget_genes.ipynb` – análisis de expresión genética y reducción de dimensionalidad.
  - `proyecto_truetarget_completo.ipynb` – modelo con todos los datos.


> Los resultados y gráficas se generan directamente al ejecutar los notebooks.
---

## 📚 Referencias

- [cBioPortal – SKCM study](https://www.cbioportal.org/study/summary?id=skcm_tcga_pan_can_atlas_2018)
- Librerías principales:  
  - [scikit-learn](https://scikit-learn.org/)  
  - [pandas](https://pandas.pydata.org/)  
  - [matplotlib](https://matplotlib.org/)  
  - [seaborn](https://seaborn.pydata.org/)  
  - [numpy](https://numpy.org/)  
  - [PyCaret](https://pycaret.org/)
  - [Optuna](https://optuna.org/)

---

## 👩‍💻 Autor

**Helena Plans**  
Proyecto final – Bootcamp de Data Science & Machine Learning  
Julio 2025
