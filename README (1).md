<div align="center">

# 🏥 Diabetes Prediction System

### AI-Powered Clinical Risk Assessment Web Application

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

<br/>

> A machine learning web application that predicts diabetes risk from clinical health metrics using a trained **Support Vector Machine (SVM)** model — deployed as an interactive dashboard with real-time probability scoring and risk factor analysis.

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Dataset](#-dataset)
- [Model Performance](#-model-performance)
- [How It Works](#-how-it-works)
- [Project Structure](#-project-structure)
- [Installation & Setup](#-installation--setup)
- [Usage Guide](#-usage-guide)
- [Future Improvements](#-future-improvements)
- [Author](#-author)
- [Disclaimer](#-disclaimer)

---

## 🔍 Overview

The **Diabetes Prediction System** is an end-to-end machine learning project that covers the full ML pipeline — from exploratory data analysis and model training to production deployment via a web interface.

The system takes **8 clinical inputs** (glucose, BMI, blood pressure, etc.) and outputs:
- ✅ Diabetic / Non-Diabetic classification
- 📊 Probability score with confidence breakdown
- ⚠️ Risk factor highlights
- 💡 Personalized health recommendations

Built on the **Pima Indians Diabetes Dataset**, this project demonstrates practical application of supervised learning in healthcare.

---

## 🚀 Live Demo

> To run locally, follow the [Installation](#-installation--setup) steps below.

```
streamlit run app.py
```
App launches at → `http://localhost:8501`

---

## ✨ Key Features

| Feature | Description |
|--------|-------------|
| 🔮 Real-time Prediction | Instant classification on button click |
| 📊 Probability Breakdown | % likelihood for diabetic vs non-diabetic |
| 🎯 Risk Gauge Chart | Plotly interactive speedometer visualization |
| ⚠️ Risk Factor Analysis | Flags high-risk indicators (glucose, BMI, BP, age) |
| 🟢 Positive Health Indicators | Highlights healthy parameters |
| 💡 Smart Recommendations | Tailored advice based on prediction outcome |
| 🏗️ Clean UI | Wide-layout Streamlit app with sidebar inputs |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python 3.8+ |
| ML Framework | Scikit-learn |
| ML Algorithm | Support Vector Machine (SVM — Linear Kernel) |
| Preprocessing | StandardScaler (Z-score normalization) |
| Web Framework | Streamlit |
| Visualization | Plotly, Matplotlib, Seaborn |
| Data Handling | NumPy, Pandas |
| Model Serialization | Joblib |

---

## 📊 Dataset

**Source:** [Pima Indians Diabetes Database — Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)  
**Origin:** National Institute of Diabetes and Digestive and Kidney Diseases  
**Population:** Female patients of Pima Indian heritage, age ≥ 21

| Property | Value |
|----------|-------|
| Total Samples | 768 |
| Features | 8 clinical inputs |
| Target | Binary (0 = Non-Diabetic, 1 = Diabetic) |
| Non-Diabetic (0) | 500 (65.1%) |
| Diabetic (1) | 268 (34.9%) |

### Input Features

| # | Feature | Unit | Description |
|---|---------|------|-------------|
| 1 | Pregnancies | count | Number of times pregnant |
| 2 | Glucose | mg/dL | Plasma glucose concentration (2-hr oral glucose tolerance test) |
| 3 | BloodPressure | mm Hg | Diastolic blood pressure |
| 4 | SkinThickness | mm | Triceps skin fold thickness |
| 5 | Insulin | mu U/ml | 2-hour serum insulin |
| 6 | BMI | kg/m² | Body mass index |
| 7 | DiabetesPedigreeFunction | score | Genetic predisposition score |
| 8 | Age | years | Patient age |

---

## 📈 Model Performance

### Training Configuration

```
Algorithm     : Support Vector Machine (SVM)
Kernel        : Linear
Train/Test    : 80% / 20% split (random_state=42)
Preprocessing : StandardScaler normalization
```

### Evaluation Metrics (Test Set)

| Metric | Score |
|--------|-------|
| ✅ Accuracy | **75.97%** |
| 🎯 Precision | 66.67% |
| 🔁 Recall | 65.45% |
| ⚖️ F1 Score | 66.06% |
| 🏋️ Train Accuracy | 77.20% |

### Confusion Matrix

```
                  Predicted
                  0     1
Actual  0  [  81    18  ]
        1  [  19    36  ]

True Negatives  = 81   |   False Positives = 18
False Negatives = 19   |   True Positives  = 36
```

> **Note:** Low false negatives (19) is critical in medical use cases — the model is reasonably conservative, avoiding missed diabetes cases.

---

## ⚙️ How It Works

```
User Inputs (8 features)
        │
        ▼
StandardScaler → Z-score normalization
        │
        ▼
Trained SVM Model (Linear Kernel)
        │
        ▼
  Prediction + Probability Score
        │
        ▼
Risk Factor Analysis + Recommendations
        │
        ▼
   Streamlit Dashboard (Live Output)
```

**Key steps in the ML pipeline:**

1. **EDA** — Distribution plots, class balance check, feature correlation analysis
2. **Preprocessing** — StandardScaler applied to all 8 features
3. **Model Training** — SVM with linear kernel, trained on 80% of data
4. **Evaluation** — Accuracy, Precision, Recall, F1, Confusion Matrix
5. **Serialization** — Model and scaler saved as `.pkl` via Joblib
6. **Deployment** — Streamlit app loads `.pkl` files and serves predictions

---

## 📁 Project Structure

```
diabetes-prediction/
│
├── 📓 diabetes-prediction.ipynb    # EDA, training, evaluation notebook
├── 🐍 app.py                       # Streamlit web application
├── 📄 diabetes.csv                  # Pima Indians dataset (768 samples)
├── 🤖 diabetes_model.pkl            # Trained SVM model (serialized)
├── ⚖️  scaler_svm.pkl               # Fitted StandardScaler (serialized)
├── 📦 requirements.txt              # Python dependencies
└── 📘 README.md                     # Project documentation
```

---

## 🔧 Installation & Setup

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Steps

**1. Clone the repository**

```bash
git clone https://github.com/AbdulRehmanRaza03/diabetes-prediction.git
cd diabetes-prediction
```

**2. (Optional) Create virtual environment**

```bash
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

**4. Run the Streamlit app**

```bash
streamlit run app.py
```

**5. Open in browser**

```
http://localhost:8501
```

> The model files (`diabetes_model.pkl` and `scaler_svm.pkl`) are already included. No re-training needed.

---

## 📖 Usage Guide

1. Open the app — you'll see **3 summary metrics** (Model Type, Accuracy, Dataset Size)
2. On the **left sidebar**, enter patient data:
   - Adjust **Age** and **Pregnancies**
   - Set medical values: **Glucose, Blood Pressure, Skin Thickness, Insulin**
   - Enter **BMI** and **Diabetes Pedigree Function**
3. Click **🔮 Predict**
4. View results:
   - 🔴 High Risk / ⚠️ Moderate Risk / ✅ Low Risk label
   - Probability % for both classes
   - Gauge chart with color zones (green / yellow / red)
   - Risk factors flagged in red/yellow
   - Positive indicators highlighted in green
   - Recommendations section tailored to outcome

---

## 🔮 Future Improvements

- [ ] Add more models (Random Forest, XGBoost) with comparison table
- [ ] Cross-validation (k-fold) for more robust evaluation
- [ ] Handle zero-value imputation (glucose=0 is biologically invalid)
- [ ] SHAP values for model explainability
- [ ] Docker containerization for cloud deployment
- [ ] Deploy to Streamlit Cloud / HuggingFace Spaces

---

## 👤 Author

**Abdul Rehman**  
BS Data Science — Superior University Lahore (2024–2028)  
Member, Google Developer Program | NVIDIA Developer Community

🔗 GitHub: [github.com/AbdulRehmanRaza03](https://github.com/AbdulRehmanRaza03)  
🌐 Portfolio: [abdulrehmanraza03.github.io/My-Portfolio](https://abdulrehmanraza03.github.io/My-Portfolio/)

---

## ⚠️ Disclaimer

> This application is built for **academic and educational purposes only**.  
> It is **NOT** a substitute for professional medical advice, clinical diagnosis, or treatment.  
> Predictions are based on statistical patterns in a limited dataset and may not generalize to all populations.  
> **Always consult a qualified healthcare professional for any medical concerns.**

---

<div align="center">

If this project helped you, consider giving it a ⭐ on GitHub!

</div>
