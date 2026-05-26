# Predicción de abandono de clientes (Churn)
## Industria: Telecomunicaciones / SaaS · Metodología: CRISP-DM

Un modelo de clasificación que identifica qué clientes tienen alta probabilidad de cancelar su suscripción, permitiendo intervención proactiva antes de que ocurra el abandono.

### Contexto y necesidad de negocio
Las empresas de telecomunicaciones y SaaS enfrentan tasas de churn de 5–25% anuales. Adquirir un cliente nuevo cuesta entre 5 y 7 veces más que retener uno existente. Sin embargo, los equipos de retención actúan de forma reactiva: intervienen cuando el cliente ya decidió irse.

La necesidad central es pasar de un modelo reactivo a uno predictivo, identificando señales de abandono con semanas de anticipación para activar campañas personalizadas de retención.

### Fases CRISP-DM aplicadas
1. Comprensión del negocio
- Definir KPIs de retención, umbral de riesgo aceptable y presupuesto de intervención por cliente.
2. Comprensión de datos
- EDA: distribución de churn, correlaciones, detección de outliers, análisis de valores nulos.
3. Preparación de datos
- Encoding categórico, normalización, tratamiento de desbalance (SMOTE / class_weight), feature engineering.
4. Modelado
- Comparar Regresión Logística (base), Random Forest y XGBoost. 
5. Evaluación
- Métricas: ROC-AUC, F1, Recall (clase positiva). Análisis de curva de ganancia y costo-beneficio.
6. Despliegue
- API REST que entrega score de riesgo diario por cliente; integración con CRM para activar campañas.

## Cómo reproducir el proyecto

Este proyecto puede reproducirse localmente siguiendo los pasos de instalación y configuración descritos a continuación.

### 1. Clonar el repositorio

Primero, clona el repositorio en tu computadora:

`git clone URL_DEL_REPOSITORIO`

Después entra a la carpeta del proyecto:

`cd Notebook_Proyecto`

### 2. Crear el entorno virtual

Crea un entorno virtual llamado `.venv_DM`:

`python -m venv .venv_DM`

### 3. Activar el entorno virtual

En Windows PowerShell:

`.venv_DM\Scripts\Activate.ps1`

En Windows CMD:

`.venv_DM\Scripts\activate.bat`

En macOS o Linux:

`source .venv_DM/bin/activate`


### 4. Instalar las dependencias

Con el entorno virtual activado, instala las librerías necesarias usando el archivo requirements.txt:

`pip install -r requirements.txt`

### 5. Activar el kernel en Jupyter / VSCode

Para poder usar el entorno virtual como kernel del notebook, instala `ipykernel`:

`pip install ipykernel`

Después registra el entorno como kernel:

`python -m ipykernel install --user --name=.venv_dm --display-name "Python (.venv_DM)"`

### 6. Seleccionar el kernel

Abre el notebook del proyecto en VSCode o Jupyter Notebook y selecciona el kernel:

`Python (.venv_DM)`

### 7. Ejecutar el proyecto

Una vez instalado todo, abre el notebook principal del proyecto y ejecuta las celdas en orden.

Asegúrate de que los archivos de datos estén en la carpeta correspondiente del proyecto antes de correr el análisis.
