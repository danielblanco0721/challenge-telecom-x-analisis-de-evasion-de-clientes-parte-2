# Challenge Telecom X - Análisis de Evasión de Clientes (Parte 2)

## Descripción

Proyecto de análisis de datos y machine learning para identificar los factores que influyen en la cancelación de clientes (churn) de TelecomX. Este notebook corresponde a la Parte 2 del desafío, enfocándose en la creación, evaluación y comparación de modelos predictivos.

## Objetivo

Desarrollar modelos predictivos que permitan identificar clientes con alta probabilidad de cancelación y proporcionar recomendaciones estratégicas basadas en datos para reducir la tasa de churn actual del 26.54%.

## Datos

- **Fuente**: API de TelecomX (JSON)
- **Registros**: 7,043 clientes
- **Variables**: 21 características originales
- **Variable objetivo**: Churn_num (0: Retenido, 1: Fuga)

## Metodología

### 1. Preparación de Datos
- Carga del dataset tratado desde CSV
- Eliminación de columnas irrelevantes (customerID)
- Encoding de variables categóricas con get_dummies
- Separación de datos en entrenamiento (80%) y prueba (20%)

### 2. Modelos Implementados
- **Regresión Logística**: Modelo lineal que requiere normalización de datos
- **Random Forest**: Modelo basado en árboles que no requiere normalización

### 3. Evaluación
- Métricas: Accuracy, Precision, Recall, F1-Score
- Matriz de confusión
- Análisis de overfitting/underfitting
- Importancia de variables

## Resultados

### Desempeño de Modelos

| Modelo | Accuracy | Precision | Recall | F1-Score | Overfitting |
|--------|----------|-----------|--------|----------|-------------|
| Regresión Logística | 80.18% | 66% | 52% | 58% | No |
| Random Forest | 77.91% | 61% | 48% | 54% | Sí (21.75%) |

**Modelo recomendado**: Regresión Logística por mejor generalización

### Factores Principales de Churn

1. **Antigüedad del cliente**: Correlación -0.352 (clientes nuevos fugan más)
2. **Tipo de contrato**: Contratos mensuales tienen 15 veces más fuga que contratos de 2 años
3. **Cargo mensual**: Clientes que pagan más tienen mayor probabilidad de fuga
4. **Facturación electrónica**: Asociada con el doble de tasa de churn
5. **Adultos mayores**: 41.7% de fuga vs 23.6% del resto

## Estructura del Proyecto
├── README.md
├── challenge_telecom_x_analisis_de_evasion_de_clientes_parte_2.ipynb
└── telecomx_estandarizado.csv
