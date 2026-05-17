# Portafolio MachineLearning: Mario Alonso Vento Alvarado
Portafolio de Machine Learning en el cual entreno y evalúo modelos de  clasificación binaria  (aprendizaje Supervisado) y modelos de clusterización de datos (aprendizaje No Supervisado ) empleando Python y sus librerías asociadas, considerando algoritmos como regresión lineal y logística, árboles de decisión, técnicas ensemble K-Means y DBScan.

Este repositorio contiene dos notebooks de Google Colab los cuales abordan problemas de:
- 🎯 **Aprendizaje Supervisado** – Predicción de ventas para una aerolínea (*WestAirlines*)
- 🔍 **Aprendizaje No Supervisado** – Segmentación de clientes para un *e‑commerce*

## 📁 Estructura del repositorio

📁 Portafolio_MachineLearning_MarioAlonsoVentoAlvarado/
- `AprendizajeNoSupervisado/` 📂
  - `ecommerce_customers.xlsx` 🗃️ – Datos de clientes del e‑commerce
  - `fichero.sql` 💻 – Script SQL auxiliar
  - `MarioAlonsoVentoAlvarado_MachineLearning_ModelosNoSupervisado.ipynb` 📓
- `AprendizajeSupervisado/` 📂
  - `EastWestAirlinesNN.csv` 🗃️ – Datos de clientes de la aerolínea
  - `fichero.sql` 💻 – Script SQL auxiliar
  - `MarioAlonsoVentoAlvarado_MachineLearning_AprendizajeSupervisado.ipynb` 📓
- `README.md` 📄

## 📦 Requisitos

Los notebooks están diseñados para ejecutarse en **Google Colab**. Asegúrate de tener una cuenta de Google y acceso a Google Drive si es necesario.

Librerías principales utilizadas:
- `pandas`, `numpy`
- `matplotlib`, `seaborn`, `plotly`
- `scikit-learn`
- `imbalanced-learn` (para SMOTE)
- `ydata-profiling`
- `openpyxl` (para leer archivos Excel)

## 🧠 Instrucciones para ejecutar los notebooks

### 1️⃣ Aprendizaje Supervisado – WestAirlines

**🎯 Objetivo:** Predecir qué clientes comprarán un servicio de telecomunicaciones (`Phone_sale`).

#### 🗂️ Carga de datos
El notebook espera el archivo `EastWestAirlinesNN.csv` en una ruta específica dentro de Google Drive. Para ello:

1. Sube el archivo a tu Google Drive, por ejemplo en la ruta:

    /Mi Unidad/Portafolio Machine Learning - Mario Vento/Caso Aplicativo - West Airlines/Data West Airlines/

2. En el notebook, monta tu Drive ejecutando la celda:

    from google.colab import drive
    drive.mount('/content/drive')

3. La lectura del CSV se realiza con:

    data = pd.read_csv('/content/drive/MyDrive/Portafolio Machine Learning - Mario Vento/Caso Aplicativo - West Airlines/Data West Airlines/EastWestAirlinesNN.csv', sep=',')

💡Nota: Si prefieres otra ubicación, modifica la ruta en la celda correspondiente. También puedes subir el archivo directamente a Colab usando files.upload(), pero el notebook está configurado para usar Drive.

#### ⚙️ Ejecución
Ejecuta todas las celdas en orden. El notebook incluye:
- Análisis exploratorio de datos (EDA)
- Preprocesamiento (log1p, escalado, one‑hot encoding, SMOTE)
- Entrenamiento de modelos: Regresión Logística, Árbol de Decisión, Random Forest
- Optimización con GridSearchCV
- Guardado del modelo final (best_random_forest_model.pkl)

### 2️⃣ Aprendizaje No Supervisado – Segmentación de clientes de e‑commerce

**🎯 Objetivo:** Identificar segmentos de clientes mediante clustering (K‑Means y DBSCAN).

#### 🗂️ Carga de datos
El notebook utiliza el archivo ecommerce_customers.xlsx. Para cargarlo:

1. Ejecuta la celda que contiene:
from google.colab import files
uploaded = files.upload()

2. Se abrirá un cuadro de diálogo: haz clic en Elegir archivos y selecciona ecommerce_customers.xlsx desde tu computadora.

3. Una vez subido, el archivo se lee con:
   df = pd.read_excel('ecommerce_customers.xlsx')

#### ⚙️ Ejecución
Ejecuta todas las celdas secuencialmente. El notebook realiza:
- Análisis exploratorio de datos (EDA)
- Preprocesamiento (escalado y one‑hot encoding)
- Selección del número óptimo de clusters con K‑Means (método del codo y silueta)
- Prueba de DBSCAN
- Perfilado de los 3 clusters obtenidos con visualizaciones: radar, boxplots, barras

## 📌 Notas importantes

- Los resultados de los modelos (métricas, gráficos, etc.) se muestran dentro de los notebooks.
- Si encuentras errores de rutas o permisos, verifica que los archivos de datos estén en las ubicaciones esperadas.
