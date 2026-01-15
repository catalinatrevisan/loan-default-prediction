# Predicción de Default de Préstamos – Scoring Crediticio

## Problema de Negocio
Las instituciones financieras enfrentan pérdidas significativas debido a:
- Procesos manuales lentos
- Evaluaciones subjetivas
- Altos costos operativos
- Defaults no detectados a tiempo

Este proyecto propone un **sistema de scoring crediticio automático** basado en Machine Learning.

## Objetivo
Predecir la probabilidad de default de un préstamo para:
- Reducir el riesgo financiero
- Mejorar la consistencia en la toma de decisiones
- Optimizar el ROI
- Permitir evaluaciones en tiempo casi real

## Dataset
- Fuente: Kaggle – Loan Approval Classification
- Tamaño: 44.993 préstamos × 14 variables
- Variable objetivo: `loan_status` (1 = Default, 0 = Pagado)
- Desbalance: 22.2% defaults / 77.8% pagados

## Análisis Exploratorio
Principales factores de riesgo identificados:
- Edad mayor a 55 años
- Préstamos para consolidación de deuda
- Tasas de interés elevadas
- Alta relación préstamo/ingreso

## Estrategia de Modelado
- Métrica principal: **ROC-AUC**, adecuada para clases desbalanceadas
- Partición del dataset:
  - Train: 66.7%
  - Validation: 16.7%
  - Test: 16.7%
- Modelos baseline para referencia

## Modelos Evaluados
- Regresión Logística
- Árbol de Decisión
- Random Forest
- Gradient Boosting
- XGBoost (modelo final)

## Optimización y Feature Engineering
- Grid Search con validación cruzada (5-fold)
- Variables creadas:
  - Ratio ingreso/préstamo
  - Carga de deuda
  - Crédito/ingreso
  - Binning de edad, ingreso y score crediticio

## Resultados
- ROC-AUC baseline: **≈ 0.505**
- ROC-AUC modelo final (CV): **0.9767**
- ROC-AUC en test: **0.9779**
- Mejora relativa: **+93.4%**

## Limitaciones
- Desbalance de clases
- Falta de validación temporal
- Variables externas limitadas
- Menor interpretabilidad de modelos basados en árboles

## Mejoras Futuras
- Técnicas de balanceo (SMOTE, ADASYN)
- Ensembles avanzados (stacking)
- Calibración de probabilidades
- Explicabilidad con SHAP values

## Herramientas
Python, Pandas, Scikit-learn, XGBoost, Matplotlib
