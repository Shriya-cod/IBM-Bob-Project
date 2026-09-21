# 🔬 Erythemato-Squamous Disease Classifier

> An end-to-end machine-learning project that predicts the type of **Erythemato-Squamous Disease** from clinical and histopathological features using a Random Forest classifier, with a fully interactive frontend built inside a Jupyter Notebook using `ipywidgets`.

---

## 📋 Project Description

Erythemato-Squamous Diseases (ESD) are a group of chronic inflammatory skin disorders that are notoriously difficult to distinguish from one another because they share many clinical features. Early and accurate diagnosis is critical for effective treatment.

This project uses the **UCI Dermatology dataset** (366 patient records, 34 features) to:

1. **Explore and visualise** the dataset — class distributions, feature correlations, and per-class feature profiles.
2. **Train a Random Forest classifier** to differentiate between the six ESD types with ≥ 97% cross-validated accuracy.
3. **Serve an interactive prediction dashboard** (no server required — runs entirely inside Jupyter) where a clinician enters a patient's feature scores and instantly sees the predicted disease, confidence probabilities per class, and the top driving features.

### Disease Classes

| Code | Disease                  |
|------|--------------------------|
| 1    | Psoriasis                |
| 2    | Seborrhoeic Dermatitis   |
| 3    | Lichen Planus            |
| 4    | Pityriasis Rosea         |
| 5    | Chronic Dermatitis       |
| 6    | Pityriasis Rubra Pilaris |

---

## 🗂️ Project Structure

```
Dermat/
├── dermatology_database.csv(https://www.kaggle.com/datasets/olcaybolat1/dermatology-dataset-classification)                  # Source dataset (UCI Dermatology)
├── Erythemato_Squamous_Disease_Classifier.ipynb  # Main notebook (backend + frontend)
├── requirements.txt                          # Python dependencies
└── README.md                                 # This file
```

---

## 🛠️ Technologies Used

| Category        | Library / Tool          | Purpose                                      |
|-----------------|-------------------------|----------------------------------------------|
| **Language**    | Python 3.9+             | Core language                                |
| **Data**        | Pandas, NumPy           | Data loading, manipulation, preprocessing    |
| **ML Backend**  | scikit-learn            | Random Forest, cross-validation, metrics     |
| **Visualisation** | Matplotlib, Seaborn   | EDA charts, confusion matrix, feature plots  |
| **Frontend UI** | ipywidgets              | Interactive sliders, buttons, output widgets |
| **Notebook**    | Jupyter Notebook        | Integrated backend + frontend environment    |

---

## 🚀 Setup & Run Instructions

### 1. Clone / download the repository

```bash
git clone <your-repo-url>
cd Dermat
```

### 2. (Recommended) Create a virtual environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Enable ipywidgets (first-time only)

```bash
jupyter nbextension enable --py widgetsnbextension
```

### 5. Launch the notebook

```bash
jupyter notebook Erythemato_Squamous_Disease_Classifier.ipynb
```

### 6. Run all cells

In the Jupyter menu choose **Kernel → Restart & Run All**, then scroll to **Section 6** to use the interactive prediction dashboard.

---

## 📊 Notebook Sections

| Section | Content |
|---------|---------|
| **1 — Imports & Configuration** | Libraries, class label map, feature group definitions |
| **2 — Data Loading & Exploration** | Shape, missing values, class distribution charts, correlation heatmap, per-class mean feature profiles |
| **3 — Data Preprocessing** | Feature / target split, missing-value imputation, stratified 80/20 train-test split |
| **4 — Model Training** | Random Forest (200 trees, balanced class weights), 5-fold stratified cross-validation |
| **5 — Model Evaluation** | Test-set accuracy, full classification report (precision/recall/F1), confusion matrix |
| **6 — Interactive Dashboard** | `ipywidgets` UI — sliders for all 34 features + age, predict button, result card with disease description, probability bar chart, top-feature chart |
| **7 — Model Summary** | Consolidated performance metrics table |

---

## 🔑 Key Information

- **Dataset source**: [UCI Machine Learning Repository — Dermatology Data Set](https://www.kaggle.com/datasets/olcaybolat1/dermatology-dataset-classification)
- **Records**: 366 patients, 6 disease classes, 34 input features (11 clinical + 22 histopathological + age)
- **Model**: Random Forest — chosen for robustness on small tabular datasets, built-in feature importance, and resistance to overfitting
- **Typical accuracy**: ≥ 97% on 5-fold cross-validation; ≥ 95% on held-out test set
- **Frontend approach**: Pure Python — `ipywidgets` renders an interactive UI directly in the notebook output without any JavaScript, HTML files, or external servers
- **Score scale used**: 0 = absent, 1 = mild, 2 = moderate, 3 = severe; family history is binary (0/1)

---

## 📎 Dataset Link

[https://www.kaggle.com/datasets/olcaybolat1/dermatology-dataset-classification]

---

