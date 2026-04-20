# 🚀 Insurance Risk Analysis Model

## 📌 Overview
This project focuses on predicting **insurance premium risk categories** using machine learning.  
The model analyzes user data such as BMI, income, lifestyle, and occupation to classify customers into different insurance risk/premium categories.

The system is built end-to-end with:
- ML model (Random Forest)
- API using FastAPI
- Frontend using Streamlit

---

## 🧠 Model Details
- **Algorithm Used:** Random Forest Classifier  
- **Problem Type:** Classification  
- **Target Variable:** `insurance_premium_category`  

Random Forest is used because:
- Handles both categorical & numerical data well  
- Captures non-linear relationships  
- Reduces overfitting via ensemble learning  

---

## ⚙️ Features Used
The model uses the following input features:

### 🔢 Numerical Features
- `bmi`  
- `income_lpa`  

### 🔤 Categorical Features
- `age_group`  
- `lifestyle_risk`  
- `occupation`  
- `city_tier`  

---

## 🔄 Data Preprocessing
- One-Hot Encoding applied on categorical features  
- Numerical features passed directly  
- ColumnTransformer used to combine preprocessing  
- Pipeline created for preprocessing + model training  

---

## 🧰 Tech Stack & Libraries

### 🐍 Core Libraries
- `pandas`
- `numpy`
- `scikit-learn`

### ⚙️ ML Components Used
- `RandomForestClassifier`
- `Pipeline`
- `ColumnTransformer`
- `OneHotEncoder`
- `train_test_split`

### 💾 Model Storage
- `pickle` for saving trained pipeline (`model.pkl`)

### ⚡ Backend (API)
- `FastAPI`
- `uvicorn`

### 🎨 Frontend
- `Streamlit`

---

## 🔌 API Implementation (FastAPI)
- Built REST API for predictions  
- Uses Pydantic for input validation  
- Loads trained `.pkl` model for inference  

Run API:
```bash
uvicorn main:app --reload
```

---

## 💻 Frontend (Streamlit)
- Interactive UI for entering user details  
- Sends input to FastAPI  
- Displays predicted insurance category  

Run frontend:
```bash
streamlit run frontend.py
```

---

## 📈 Model Workflow
1. User inputs data via Streamlit UI  
2. Request sent to FastAPI  
3. Data passes through preprocessing pipeline  
4. Random Forest model predicts category  
5. Result returned and displayed  
