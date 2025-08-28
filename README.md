# 🧠 Depression Prediction using Emotion Patterns

## 📌 Introduction
This project explores the use of **machine learning models** to predict depression based on emotional patterns collected over two weeks.  
The dataset includes binary emotion features (joy, sadness, anger, etc.) normalized or counted in frequency.  
The aim is to determine which feature representation (**Freq-PHO-Binary** vs. **Norm-PHO-Binary**) produces better classification performance.

## 🎯 Objectives
- Analyze the dataset for depression classification.
- Apply multiple machine learning algorithms (KNN, Decision Tree, Naive Bayes, SVM).
- Compare the performance of **frequency-based** vs. **normalized** features.
- Identify the best-performing model and suggest future improvements.

## 📂 Dataset
- **Freq-PHO-Binary.csv** → Emotion frequency counts in binary format.
- **Norm-PHO-Binary.csv** → Normalized version of the dataset (each day scaled to fixed sum = 15).
- **Target variable** → Depression (`YES` / `NO`)

**Class distribution:**
- NO: 218 (56%)  
- YES: 173 (44%)  

Dataset is relatively **balanced**.

## ⚙️ Methodology
- **Preprocessing:** Label encoding categorical variables (e.g., Gender).
- **Validation:** 10-fold cross-validation.
- **Models tested:**  
  - Dummy Classifier (baseline)  
  - KNN  
  - Decision Tree  
  - Gaussian Naive Bayes  
  - Bernoulli NB  
  - Multinomial NB  
  - SVM (Linear, RBF, Sigmoid, Polynomial)  
- **Hyperparameter tuning:** GridSearchCV.

## 📊 Results
| Algorithm        | Freq-PHO-Binary Accuracy | Norm-PHO-Binary Accuracy |
|------------------|--------------------------|---------------------------|
| Dummy Classifier | 49%                      | 50%                       |
| KNN              | 60%                      | 61%                       |
| Decision Tree    | 60%                      | 63%                       |
| Gaussian NB      | 59%                      | 60%                       |
| Bernoulli NB     | 59%                      | 60%                       |
| Multinomial NB   | 62%                      | 62%                       |
| SVM (Linear)     | 63%                      | 61%                       |
| SVM (RBF)        | 62%                      | 63%                       |
| SVM (Sigmoid)    | 60%                      | 59%                       |
| SVM (Polynomial) | 63%                      | **65%**                   |

✅ **Best model:** SVM (Polynomial) on **Norm-PHO-Binary** with **65% accuracy**.  
Normalization improved performance compared to frequency-based features.
