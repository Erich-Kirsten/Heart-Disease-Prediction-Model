# 🫀 Heart Disease Prediction with Logistic Regression

A full end-to-end machine learning project using logistic regression to predict heart disease based on clinical patient data. This repo contains two datasets — one synthetic (referred to as “flawless”) and one real (UCI Cleveland dataset) — and compares the outcomes of modeling both.

---

## 🧠 Project Motivation

Logistic regression is a foundational algorithm for binary classification problems. Heart disease is a binary outcome (presence or absence), making it an excellent real-world case for this technique.

However, **data quality plays a massive role in model effectiveness**. So, we conducted experiments on two datasets:

1. **Flawless Dataset** – synthetic and likely AI-generated
2. **Real Dataset** – UCI Heart Disease (Cleveland) subset

This allowed us to not only apply machine learning but also critically evaluate dataset trustworthiness and interpretability.

---

## 📁 Dataset Overview

### 1. **Flawless Dataset**  
- 8700+ records  
- 25+ features, including unusual ones like “Hemisphere” and “Sedentary Hours Per Day”  
- No missing values  
- Suspiciously clean and complete  
- Weak correlation and unreliable patterns

### 2. **Real Dataset (UCI Cleveland)**  
- 303 records originally, 297 after cleaning  
- 13 medically validated features  
- `target = 1` → heart disease present  
- `target = 0` → no heart disease  
- Some missing values handled appropriately

---

## 🧪 Project Structure

Each dataset went through the following pipeline:

1. Data loading and cleaning
2. Exploratory data analysis (EDA)
3. Feature preparation
4. Logistic regression modeling
5. Performance evaluation
6. Feature importance interpretation

---

## 📊 Key Findings

### 🚨 Flawless Dataset (Synthetic)
| Dimension              | Result                                 |
|------------------------|----------------------------------------|
| Correlation            | ~0.00 for all features                 |
| Coefficients           | Scattered across 1000+ meaningless dummies |
| Model output           | Predicted only 1 class (always 0)      |
| Performance            | AUC < 0.5 — worse than guessing        |
| Visuals                | Flat and meaningless                  |

> ✅ Technically correct modeling, but the data was synthetic and unreliable.

---

### ✅ Real Dataset (UCI Cleveland)
| Metric     | Value   |
|------------|---------|
| Accuracy   | 0.833   |
| Precision  | 0.846   |
| Recall     | 0.786   |
| F1 Score   | 0.815   |
| ROC AUC    | 0.949   |

**Feature Importance Highlights:**
- `ca` (major vessels): strong positive predictor
- `thal`: highly predictive
- `cp` (chest pain type): clear signal
- `thalach` and `oldpeak`: reliable and explainable

> 🔍 This model performed **very well** and the results matched known clinical patterns.

---

## 📂 Files in This Repo

- `flawless_dataset.ipynb` – full notebook with synthetic dataset
- `realset.ipynb` – UCI Cleveland dataset analysis
- `processed.cleveland.data` – cleaned dataset
- `comparison.md` – short writeup comparing real vs. flawless datasets
- `report_realset.pdf` – final documentation 

---

## 📌 Lessons Learned

- A model is only as good as the data it learns from.
- “Flawless” synthetic data may look clean, but can be meaningless.
- Logistic regression still works **exceptionally well** with good data.
- Interpretation and correlation matter just as much as metrics.

---

## 🧾 References

- UCI Machine Learning Repository: [Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease)
- Scikit-learn documentation
- Matplotlib and Seaborn for visualization

---

## ✅ Conclusion

This project is both a machine learning tutorial and a cautionary tale about data quality. It shows how logistic regression can be effective for medical problems — but only when paired with **real, interpretable, and trusted data**.

Feel free to fork, adapt, and reuse this for your own ML or health data explorations!
