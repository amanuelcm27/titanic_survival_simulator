# Titanic Survival Prediction 🚢🎯

This project is a machine learning solution to the famous [Titanic - Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic) competition on Kaggle. The goal is to predict which passengers survived the Titanic shipwreck using classification models trained on features like age, gender, ticket class, and more.

---

## 📂 Dataset

The dataset contains demographic and passenger information:
- `train.csv`: labeled data used for training and validation
- `test.csv`: unlabeled data for prediction (submission file based on this)

---

## 🔍 Features Used

After preprocessing and feature engineering, the following features were used:
- Age (with missing values filled using median)
- SibSp (siblings/spouses aboard)
- Parch (parents/children aboard)
- Fare (with missing values filled using median)
- Embarked (one-hot encoded: Q, S)
- Sex (one-hot encoded: male)
- Pclass (one-hot encoded: 2nd and 3rd class)

---

## 🛠 Preprocessing Steps

- Dropped unused columns: `Name`, `Ticket`, `Cabin`, and `PassengerId`
- Handled missing values in `Age`, `Fare`, and `Embarked`
- Applied one-hot encoding to categorical variables (`Embarked`, `Sex`, `Pclass`)
- Ensured consistent preprocessing for both train and test data

---

## 🧠 Models Trained

| Model                     | Accuracy (Validation) |
|--------------------------|------------------------|
| Logistic Regression       | 79.9%                  |
| Random Forest Classifier  | 82.1%                  |
| Support Vector Machine    | 82.1%                  |
| Bagging (Random Forest)   | 81.6%                  |
| **Stacking Classifier** (RF + SVM → LR) | **83.0%** ✅ |

📌 Final model used: `StackingClassifier` with Random Forest and SVM as base models and Logistic Regression as the meta-learner.

---

## 📈 Evaluation Metrics

On the validation set:
- **Accuracy**: 83%
- **Confusion Matrix** and **Classification Report** printed for deeper insight
Confusion Matrix:
 [[96  9]
 [21 53]]



