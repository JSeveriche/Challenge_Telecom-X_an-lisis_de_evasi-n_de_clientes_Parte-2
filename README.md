# 📊 TelecomX — Churn Analysis & Prediction

Este repositorio contiene el flujo completo para **analizar y predecir la evasión de clientes (Churn)** en *Telecom X*:
1) *EDA* (análisis exploratorio)
2) *Feature engineering*
3) *Modelos predictivos* (Regresión Logística, Random Forest y opcional **XGBoost**)
4) *Importancia de variables* y reporte de métricas

## 🚀 Cómo usar
```bash
git clone https://github.com/tuusuario/TelecomX-Churn.git
cd TelecomX-Churn
python -m venv .venv && source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt
```
Abre los notebooks de `notebooks/` o entrena vía CLI:
```bash
python src/train_model.py --input data/TelecomX_Data.json --model rf --out_dir outputs/models
```

## 📂 Estructura
```
TelecomX-Churn/
├── data/
│   └── TelecomX_Data.json         # Dataset original (si se puede compartir)
├── notebooks/
│   ├── TelecomX_Churn_EDA.ipynb   # EDA (si estaba disponible)
│   └── TelecomX_Churn_Model.ipynb # Modelado ML
├── outputs/
│   ├── figures/                   # Gráficos generados
│   └── models/                    # Modelos entrenados (.joblib)
├── src/
│   ├── preprocess.py              # Limpieza y feature engineering
│   ├── utils.py                   # Utilidades comunes (métricas, plots)
│   └── train_model.py             # Entrenamiento desde línea de comandos
├── requirements.txt
├── .gitignore
└── README.md
```

## 📈 Modelos y métricas
- Baseline: **LogisticRegression** con *class_weight='balanced'*
- **RandomForestClassifier**
- **XGBoost** (si está instalado)
- Métricas clave: Accuracy, Precision, Recall, F1, ROC-AUC, Matriz de confusión, Curva ROC.

## 🔍 Variables importantes
- Para modelos lineales (Logistic): coeficientes estandarizados
- Para modelos de árbol: `feature_importances_` y *Permutation Importance*

## 🛡️ Notas
- Si `XGBoost` no está instalado, el flujo continúa sin él.
- Si tu dataset final limpio difiere del JSON, actualiza las rutas en `train_model.py` o en el notebook.
