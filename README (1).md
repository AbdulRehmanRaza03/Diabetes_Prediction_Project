# 🏥 Diabetes Prediction System

An AI-powered diabetes risk assessment web application built with **Support Vector Machine (SVM)** and deployed using **Streamlit**. Enter patient health metrics and get instant diabetes risk predictions with visual analytics.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Dataset](#dataset)
- [Model Performance](#model-performance)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Disclaimer](#disclaimer)

---

## 🔍 Overview

This project uses the **Pima Indians Diabetes Dataset** to train an SVM classifier that predicts whether a patient is diabetic based on 8 clinical features. The trained model is deployed as an interactive Streamlit web app with a gauge chart, risk factor analysis, and health recommendations.

---

## ✨ Features

- **Real-time prediction** — instant diabetes risk assessment from patient inputs
- **Probability breakdown** — shows % likelihood for diabetic vs non-diabetic
- **Interactive gauge chart** — visual risk level display using Plotly
- **Risk factor analysis** — highlights high-risk health indicators
- **Personalized recommendations** — actionable health advice based on prediction
- **Clean Streamlit UI** — user-friendly sidebar for all inputs

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.x |
| ML Model | Scikit-learn (SVM) |
| Web App | Streamlit |
| Data Processing | NumPy, Pandas |
| Visualization | Plotly, Matplotlib, Seaborn |
| Model Serialization | Joblib |

---

## 📊 Dataset

**Source:** Pima Indians Diabetes Database

| Property | Value |
|----------|-------|
| Total Samples | 768 |
| Features | 8 |
| Classes | 2 (Diabetic / Non-Diabetic) |
| Non-Diabetic | 500 |
| Diabetic | 268 |

**Input Features:**

| Feature | Description |
|---------|-------------|
| Pregnancies | Number of pregnancies |
| Glucose | Plasma glucose concentration (mg/dL) |
| Blood Pressure | Diastolic blood pressure (mm Hg) |
| Skin Thickness | Triceps skin fold thickness (mm) |
| Insulin | 2-hour serum insulin (mu U/ml) |
| BMI | Body mass index (kg/m²) |
| Diabetes Pedigree Function | Genetic predisposition score |
| Age | Age in years |

---

## 📈 Model Performance

| Metric | Value |
|--------|-------|
| Model | Support Vector Machine (SVM) |
| Accuracy | ~78% |
| Preprocessing | StandardScaler normalization |

---

## ⚙️ Installation

**1. Clone the repository**

```bash
git clone https://github.com/your-username/diabetes-prediction.git
cd diabetes-prediction
```

**2. Install dependencies**

```bash
pip install -r requirements.txt
```

**3. Run the app**

```bash
streamlit run app.py
```

App opens at `http://localhost:8501`

---

## 🚀 Usage

1. Open the app in your browser
2. Use the **sidebar** to enter patient details:
   - Age, Pregnancies
   - Glucose, Blood Pressure, Skin Thickness, Insulin
   - BMI, Diabetes Pedigree Function
3. Click **🔮 Predict**
4. View prediction result, risk gauge, and recommendations

---

## 📁 Project Structure

```
diabetes-prediction/
│
├── app.py                      # Streamlit web application
├── diabetes-prediction.ipynb   # EDA & model training notebook
├── diabetes.csv                # Dataset
├── diabetes_model.pkl          # Trained SVM model
├── scaler_svm.pkl              # Fitted StandardScaler
├── requirements.txt            # Python dependencies
└── README.md                   # Project documentation
```

---

## ⚠️ Disclaimer

> This tool is built for **educational and academic purposes only**.  
> It is **NOT** a substitute for professional medical advice, diagnosis, or treatment.  
> Always consult a qualified healthcare professional for medical concerns.

---

## 👤 Author

**Abdul Rehman**  
BS Data Science — Superior University Lahore  
Member, Google Developer Program | NVIDIA Developer Community

---

*If you found this project helpful, consider giving it a ⭐ on GitHub!*
