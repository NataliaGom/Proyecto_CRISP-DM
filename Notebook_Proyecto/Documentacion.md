## Documentación rápida del notebook

### Proyecto: Predicción de Churn en clientes de Telco

Este notebook desarrolla un proyecto de minería de datos enfocado en analizar y predecir la cancelación de clientes, conocida como *churn*, dentro de una empresa de telecomunicaciones. El trabajo sigue la metodología **CRISP-DM**, principalmente en sus fases de entendimiento de los datos, preparación de los datos, modelado y evaluación.

El objetivo principal es identificar patrones de comportamiento asociados con clientes que abandonan el servicio, así como construir modelos predictivos que permitan anticipar dicho abandono. Esto es relevante porque el churn representa una pérdida directa de ingresos para la empresa y permite diseñar estrategias de retención más efectivas.

### 1. Carga y exploración inicial de datos

El notebook inicia con la importación de librerías necesarias para análisis de datos, visualización y modelado, como `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `imblearn`, `xgboost` y `shap`.

Posteriormente, se carga el dataset de clientes Telco y se realiza una revisión inicial de su estructura. En esta etapa se identifican las dimensiones del conjunto de datos, los tipos de variables, la presencia de valores nulos y la distribución general de la variable objetivo, `Churn`.

Esta fase permite comprender qué información contiene el dataset y detectar posibles problemas antes de construir modelos predictivos.

### 2. Análisis exploratorio de datos

Después de cargar los datos, se realiza un análisis exploratorio para entender la relación entre las variables y la cancelación del servicio. Se revisan variables demográficas, características del contrato, servicios contratados, cargos mensuales, cargos totales y antigüedad del cliente.

A través de gráficas se analizan diferencias entre clientes que permanecen y clientes que cancelan. Por ejemplo, se observa cómo el churn puede variar según el tipo de contrato, método de pago, servicios adicionales, tiempo de permanencia y nivel de gasto mensual.

Este análisis es importante porque ayuda a detectar patrones relevantes y posibles variables predictoras antes del modelado.

### 3. Preparación y limpieza de datos

En esta fase se corrigen problemas del dataset para que pueda ser utilizado por los modelos de machine learning. Se tratan valores faltantes, se convierten variables al tipo de dato correcto y se eliminan o ajustan columnas que no aportan valor predictivo directo.

También se transforman variables categóricas a formato numérico mediante técnicas como codificación binaria u *one-hot encoding*. Esto es necesario porque la mayoría de los modelos no pueden trabajar directamente con texto o categorías.

Además, se separan las variables predictoras de la variable objetivo y se divide el dataset en conjuntos de entrenamiento y prueba. Esto permite entrenar los modelos con una parte de los datos y evaluar su desempeño con datos no vistos.

### 4. Feature Engineering

Una de las partes más importantes del notebook es la creación de nuevas variables a partir de las existentes. El *feature engineering* permite enriquecer el dataset y capturar relaciones que no son evidentes en las variables originales.

Se crean variables relacionadas con la antigüedad del cliente, el nivel de gasto, la intensidad de servicios contratados, el tipo de contrato y el riesgo potencial de cancelación. Estas nuevas variables ayudan a representar mejor el comportamiento del cliente.

Esta fase fue necesaria porque el churn no depende únicamente de variables individuales, sino de combinaciones de factores. Por ejemplo, un cliente con contrato mensual, poca antigüedad y cargos altos puede tener un perfil de riesgo distinto al de un cliente antiguo con contrato de largo plazo.

### 5. Modelado predictivo

Una vez preparados los datos, se entrenan diferentes modelos de clasificación para predecir si un cliente cancelará o no el servicio. Entre los modelos utilizados se incluyen algoritmos tradicionales y modelos más avanzados, como regresión logística, árboles de decisión, random forest y XGBoost.

También se aplican técnicas para manejar el desbalance de clases, como **SMOTE**, debido a que normalmente hay menos clientes que cancelan que clientes que permanecen. Esto ayuda a que el modelo no se incline únicamente por predecir la clase mayoritaria.

Los modelos se entrenan con el conjunto de entrenamiento y después se evalúan con el conjunto de prueba.

### 6. Evaluación de modelos

El desempeño de los modelos se analiza mediante métricas como accuracy, precision, recall, F1-score, matriz de confusión y curva ROC-AUC.

Para este tipo de problema, no basta con observar únicamente el accuracy, ya que puede ser engañoso si las clases están desbalanceadas. Por eso, se da especial importancia al recall de la clase churn, pues interesa identificar correctamente a los clientes que tienen mayor probabilidad de abandonar el servicio.

También se comparan los modelos para elegir aquel que ofrece el mejor balance entre capacidad predictiva e interpretación.

### 7. Interpretabilidad del modelo

Finalmente, se utilizan herramientas de interpretabilidad como **SHAP** para analizar qué variables influyen más en las predicciones del modelo. Esto permite entender no solo qué predice el modelo, sino también por qué lo hace.

La interpretabilidad es fundamental en proyectos de negocio, ya que ayuda a traducir los resultados técnicos en decisiones prácticas. Por ejemplo, permite identificar qué características de los clientes están más asociadas con el riesgo de churn y orientar estrategias de retención.

### Conclusión

El notebook permite desarrollar un flujo completo de minería de datos aplicado a un problema real de negocio. A partir del análisis exploratorio, la limpieza de datos, el feature engineering, el modelado y la evaluación, se construye una solución predictiva para identificar clientes con riesgo de cancelación.

El valor principal del proyecto está en que no solo predice el churn, sino que también permite entender los factores que lo explican, lo cual puede apoyar la toma de decisiones estratégicas dentro de una empresa de telecomunicaciones.
