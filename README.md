# Challenge_Alura_TelecomX2
#  Telecom X: Predictive Churn Analysis & Machine Learning

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

##  Propósito del Análisis
El objetivo principal de este proyecto es desarrollar un motor de **Machine Learning** capaz de predecir la cancelación (**churn**) de clientes. Mediante el análisis de variables demográficas y de servicios, identificamos patrones críticos que permiten a Telecom X ejecutar estrategias de retención proactivas, interviniendo antes de que el cliente abandone el servicio.

##  Estructura del Proyecto
* **`/datos`**: Contiene el dataset `datos_tratados.csv` (resultado de la limpieza y transformación).
* **`/notebooks`**: Cuaderno principal `TelecomX_MachineLearning.ipynb` con el flujo de desarrollo.
* **`/visualizaciones`**: Gráficos de evaluación, importancia de variables y matrices de confusión.

##  Preparación de los Datos
Para garantizar la estabilidad de los modelos en Google Colab, se implementó el siguiente pipeline:
1.  **Clasificación:** Separación de variables categóricas y numéricas.
2.  **Tratamiento de Nulos:** Aplicación de `dropna()` post-encoding para eliminar inconsistencias.
3.  **Codificación:** Uso de **One-Hot Encoding** para transformar categorías en datos procesables.
4.  **Normalización:** Aplicación de `StandardScaler` para equilibrar la escala de las variables en modelos lineales.
5.  **División:** Segmentación en **70% Entrenamiento** y **30% Prueba**.

##  Rendimiento de los Modelos
Se evaluaron tres arquitecturas, seleccionando la **Regresión Logística Balanceada** como modelo final:

| Modelo | Accuracy | Recall (Churn) | F1-Score |
| :--- | :---: | :---: | :---: |
| Regresión Logística (Normal) | 80% | 0.55 | 0.58 |
| Random Forest | 78% | 0.74 | 0.54 |
| **Logística (Balanceada)** | **74%** | **0.79** | **0.62** |

> **Nota:** Se priorizó el **Recall (0.79)** para asegurar la detección de la mayor cantidad de clientes en riesgo, minimizando los falsos negativos.



##  Insights y Factores de Riesgo
1.  **Tipo de Contrato:** El contrato mensual (*Month-to-month*) es el predictor más fuerte de abandono.
2.  **Internet de Fibra Óptica:** Presenta una tasa de churn del 42%, indicando una posible brecha de calidad/precio.
3.  **Antigüedad (Tenure):** La vulnerabilidad es máxima en los primeros 12 meses.
4.  **Servicios de Valor:** La falta de *TechSupport* y *OnlineSecurity* duplica el riesgo de fuga.



##  Estrategias de Retención Sugeridas
* **Migración de Contratos:** Incentivar el paso de planes mensuales a anuales mediante descuentos progresivos.
* **Atención Temprana:** Implementar protocolos de *onboarding* proactivo durante el primer semestre del cliente.
* **Venta Cruzada:** Ofrecer servicios de seguridad técnica gratuitos por tiempo limitado para "anclar" a los usuarios de fibra óptica.
* **Scoring Mensual:** Correr el modelo al final de cada ciclo para obtener la lista de clientes con alta probabilidad de cancelación.

##  Instrucciones de Ejecución
1. Clonar el repositorio.
2. Instalar dependencias:
   ```bash
   pip install pandas seaborn scikit-learn matplotlib
