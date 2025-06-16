# Hematological-Analysis-for-Anemia-Diagnosis

This project explores how machine learning techniques can be applied to hematological (blood test) data to support the **diagnosis and classification of different anemia types**. Using a validated dataset derived from Complete Blood Count (CBC) tests, we investigate patient distributions, identify key diagnostic features, and evaluate model performance.

---

## 📁 Dataset Overview

- **Total Records:** 1,277 (after cleaning: 1,228)
- **Source:** CBC records from healthcare institutions
- **Validated By:** Medical professionals

### 📌 Hematological Features:
- `HGB` – Hemoglobin (oxygen transport capacity)
- `MCV` – Mean Corpuscular Volume (RBC size)
- `MCHC` – Mean Corpuscular Hemoglobin Concentration
- `RBC` – Red Blood Cell Count
- `WBC` – White Blood Cell Count
- `PLT` – Platelet Count
- `PDW`, `PCT` – Additional platelet-related parameters

### 🏷 Diagnosis Categories:
- Healthy
- Iron Deficiency Anemia
- Normocytic Hypochromic Anemia
- Normocytic Normochromic Anemia
- Macrocytic Anemia
- Leukemia
- Leukemia with Thrombocytopenia
- Thrombocytopenia
- Other Microcytic Anemia

---

## ⚙️ Methods

### 📊 Exploratory Data Analysis (EDA)
- Investigated class distribution
- Found common conditions: Normocytic Hypochromic (279) and Normocytic Normochromic Anemia (269)
- Rare conditions identified, e.g., Leukemia with Thrombocytopenia (11)

### 🔍 Data Preprocessing
- Removed outliers using **Z-score method**
- Removed 49 duplicate entries
- Final dataset: **1,228 clean and unique records**
- Feature scaling for consistent input across models
- Data split: **70% training, 30% testing**

---

## 🤖 Machine Learning Models

Implemented using **R** and **Weka**:

| Model | Highlights | Accuracy |
|-------|------------|----------|
| **J48 Decision Tree** | Highest performance; interpretable | **98.33%** |
| **Random Forest** | Balanced accuracy; feature importance analysis | 98% |
| **Multilayer Perceptron (MLP)** | Non-linear learning capability | 97–98% |
| **Logistic Regression** | Interpretable but limited on complex patterns | Lower than others |

📌 **Important Predictors** across models:
- HGB (Hemoglobin)
- MCHC (Mean Corpuscular Hemoglobin Concentration)
- MCV (Mean Corpuscular Volume)
- PLT (Platelet Count)

---

## 🧠 Key Findings

- HGB levels clearly distinguish healthy individuals from those with anemia.
- Certain models (e.g., J48) excelled at identifying subtle differences across anemia types.
- Relationships such as **HGB vs. PLT** and **HGB vs. MCHC** captured meaningful diagnostic patterns.
- Models successfully classified both common and rare conditions with minimal misclassification.

---

## 📈 Tools & Technologies

- **R**: For preprocessing, EDA, and modeling (e.g., Random Forest, Logistic Regression)
- **Weka**: For implementing and evaluating **J48 Decision Tree**
- **Visualization**: EDA plots for feature distribution, outlier detection, and feature correlation

---

## 🔮 Future Work

- Address class imbalance using SMOTE or other techniques
- Integrate real-time blood test data for dynamic modeling
- Apply **Explainable AI (XAI)** techniques to interpret complex model decisions
- Explore ensemble methods or hybrid classifiers
