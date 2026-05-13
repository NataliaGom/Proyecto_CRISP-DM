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
- Comparar Regresión Logística (base), Random Forest y XGBoost. Optimización con GridSearchCV.
5. Evaluación
- Métricas: ROC-AUC, F1, Recall (clase positiva). Análisis de curva de ganancia y costo-beneficio.
6. Despliegue
- API REST que entrega score de riesgo diario por cliente; integración con CRM para activar campañas.
