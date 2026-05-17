# 🫀 Heart Attack Risk Prediction System

> **AI-Powered Clinical Decision Support System (CDSS) for Early Cardiovascular Risk Screening**

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3%2B-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-1.7%2B-0052CC?logo=xgboost&logoColor=white)](https://xgboost.ai/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 📖 Overview
This repository contains a production-ready machine learning pipeline designed to predict heart disease risk based on patient clinical features. Built with a focus on **medical reliability, interpretability, and reproducibility**, the system serves as a Clinical Decision Support System (CDSS) prototype for early cardiovascular screening.

The project follows industry-standard MLOps practices: stratified splitting, pipeline-based preprocessing, threshold optimization for clinical recall, and SHAP-based model explainability.

---

## ✨ Key Features
-  **XGBoost Classifier** optimized for tabular medical data
- 📊 **Stratified Train/Test Split** (80/20) preserving class distribution
- 🔄 **Scikit-learn Pipeline** preventing data leakage during preprocessing
- ⚖️ **Class Imbalance Handling** via `scale_pos_weight`
- 🎯 **Threshold Tuning** (Optimal: `0.42`) maximizing clinical recall
- 📈 **ROC-AUC: 0.902** | **Accuracy: 88%** | **Recall: 86%**
- 🔍 **SHAP Interpretability** for transparent, doctor-friendly predictions
- 💾 **Model Serialization** (`joblib`) ready for API/Streamlit deployment

---

## 🛠️ Tech Stack
| Category | Tools |
|----------|-------|
| **Language** | Python 3.10+ |
| **ML Framework** | `scikit-learn`, `XGBoost` |
| **Interpretability** | `SHAP` |
| **Data Manipulation** | `pandas`, `numpy` |
| **Visualization** | `matplotlib`, `seaborn` |
| **Environment** | Google Colab / Jupyter Lab |
| **Deployment Ready** | `joblib`, FastAPI/Streamlit compatible |

---

## 📊 Dataset
| Property | Details |
|----------|---------|
| **Source** | [UCI Heart Disease Dataset (Cleveland)](https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data) |
| **Samples** | 303 patients (after cleaning) |
| **Features** | 13 clinical variables (Age, Sex, CP, Trestbps, Chol, FBS, RestECG, Thalach, Exang, Oldpeak, Slope, CA, Thal) |
| **Target** | Binary: `0` = No Disease, `1` = Heart Disease |
| **Class Distribution** | ~54% Negative, ~46% Positive |

> ✅ This dataset is clinically validated and widely used in peer-reviewed ML research.

---

## 📈 Model Performance
| Metric | Value | Clinical Relevance |
|--------|-------|-------------------|
| **ROC-AUC** | `0.902` | Excellent discrimination ability |
| **Accuracy** | `88%` | Overall correct predictions |
| **Precision** | `89%` | Low false alarm rate |
| **Recall** | `86%` | Captures 86% of actual cases (critical for screening) |
| **F1-Score** | `87%` | Balanced precision-recall |
| **Optimal Threshold** | `0.42` | Tuned for higher sensitivity in medical context |

📊 **Confusion Matrix (Test Set)**
| | Predicted: No Disease | Predicted: Heart Disease |
|---|---|---|
| **Actual: No Disease** | 29 (TN) | 3 (FP) |
| **Actual: Heart Disease** | 4 (FN) | 24 (TP) |

---

## 🚀 Quick Start

### 1️⃣ Clone Repository
```bash
git clone https://github.com/YOUR_USERNAME/heart-attack-prediction.git
cd heart-attack-prediction
```

### 2️⃣ Setup Environment
```bash
# Using pip
pip install -r requirements.txt

# Or install manually
pip install pandas numpy scikit-learn xgboost shap matplotlib seaborn joblib
```

### 3️⃣ Run in Google Colab (Recommended)
1. Upload `Prediction.ipynb` to [Google Colab](https://colab.research.google.com/)
2. Select `Runtime → Change runtime type → GPU (optional)`
3. Click `Run All` ▶️
4. Outputs: Metrics, Plots, SHAP Explanation, and `heart_disease_uci_model.pkl`

### 4️⃣ Run Locally
```bash
jupyter notebook Prediction.ipynb
```

---

## 📁 Project Structure
```
📦 heart-attack-prediction/
├── 📄 Prediction.ipynb          # Main notebook (EDA → Training → Evaluation)
├── 📄 requirements.txt          # Python dependencies
├── 📄 heart_disease_uci_model.pkl # Trained pipeline + threshold config
├── 📄 README.md                 # Project documentation
└── 📄 LICENSE                   # MIT License
```

---

## 🔍 Model Interpretability
The model uses **SHAP (SHapley Additive exPlanations)** to explain predictions:
-  Red dots = Higher feature values increasing risk
- 🟦 Blue dots = Lower feature values decreasing risk
- 📏 X-axis = SHAP value (impact on prediction)
-  Top predictors: `CA` (Major Vessels), `Thal` (Defect Type), `ChestPainType`, `Age`, `Oldpeak`

> 💡 SHAP plots are generated automatically in Cell 9 of the notebook.

---

## ⚠️ Medical Disclaimer
> **This system is for EDUCATIONAL & RESEARCH PURPOSES ONLY.**  
> It is a prototype Clinical Decision Support System (CDSS) and **MUST NOT** be used as a substitute for professional medical diagnosis, treatment, or advice.  
> False negatives can be life-threatening. Always consult a certified cardiologist or healthcare provider for clinical decisions.  
> Deployment in production requires regulatory compliance (FDA/CE/Kemenkes), clinical validation, and ethical approval.

---

## 🤝 Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m 'Add YourFeature'`)
4. Push to branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 📜 License
This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author
**Your Name**  
📧 your.email@example.com  
 [LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)

---

> 🫀 *Built with care for clinical safety & ML best practices. If you find this useful, please ⭐ the repository!*
