# Titanic Survival Prediction Project

## Project Overview
This project aims to predict **survival outcomes** of Titanic passengers using demographic, family, and ticket information. The dataset includes columns such as:

- `Pclass`, `Sex`, `Age`, `Siblings/Spouses Aboard`, `Parents/Children Aboard`, `Fare`, `Name`, `Survived`

The goal is to identify which passengers were likely to survive based on various features.

---

## Data Preprocessing & Feature Engineering
- **Data Cleaning:** Removed unnecessary columns like `Name`. Converted `Sex` to numeric values (`male=0`, `female=1`).  
- **Outlier Handling & Visualization:** Used **boxplots** and **histograms** for numeric features (`Age`, `Fare`, `Siblings/Spouses`, `Parents/Children Aboard`, `Pclass`).  
- **Exploratory Data Analysis (EDA):**  
  - KDE plots revealed that `Sex` and `Pclass` are strong predictors.  
  - `Age` has moderate predictive power, while individual family-related columns were weak.  

- **Feature Engineering:**  
  - Created `familysize` = `Siblings/Spouses Aboard` + `Parents/Children Aboard` + 1.  
  - Binned `Fare` into `FareBin` categories.  
  - Performed one-hot encoding for categorical features.  

- **Feature Selection:**  
  - Calculated **Information Value (IV)** for features to measure predictive power.  
  - Selected features with IV > 0.02 for model building.

---

## Modeling Approach
- Split dataset into training and test sets (80/20) and scaled `Age` using **MinMaxScaler**.  
- Built and compared multiple models:  
  - **Logistic Regression**  
  - **Random Forest Classifier**  
  - **XGBoost Classifier**  

- Addressed potential **class imbalance** using under-sampling and SMOTE-Tomek approaches.  
- Evaluated models using **Classification Report** and **ROC-AUC** metrics.

---

## Results & Insights
- Logistic Regression delivered the most reliable performance with an **81% ROC-AUC score**.  
- Strongest predictors of survival: `Sex`, `Pclass`, and `familysize`.  
- Family size proved more informative than individual family-related columns (`Siblings/Spouses` and `Parents/Children`).  

---

## Tech Stack
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Seaborn, Matplotlib  
- XGBoost  

---

## Key Takeaways
- Feature engineering, including `familysize` and fare binning, improved model accuracy.  
- Logistic Regression proved robust for binary classification in this dataset.  
- EDA and Information Value analysis guided effective feature selection.
