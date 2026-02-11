# Mushroom Edibility Classification

## 1. Introduction
This project focuses on classifying mushrooms as either **edible (e)** or **poisonous (p)** based on their physical characteristics using machine learning techniques. The dataset used is the famous **Mushroom Dataset** from the UCI Machine Learning Repository, containing 8,124 instances with 22 categorical features.

The goal is to develop an accurate classification model to automate the identification process, which is critical given the safety risks associated with mushroom consumption.

## 2. Dataset Overview
- **Source:** UCI Machine Learning Repository
- **Instances:** 8,124
- **Attributes:** 22 (all categorical) + 1 Target Variable (`class`)
- **Class Distribution:**
  - **Edible:** 4,208 (51.8%)
  - **Poisonous:** 3,916 (48.2%)
- **Balance:** The dataset is well-balanced, allowing for bias-free training without rebalancing techniques.

## 3. Methodology

### 3.1 Preprocessing
To prepare the categorical data for machine learning algorithms, the following steps were taken:
- **Feature Selection:** 
  - `veil-type` was removed as it contained only a single unique value, offering no predictive power.
  - `stalk-root` was removed due to a high volume of missing values (2,480 instances). Feature importance analysis showed it contributed less than 0.5% to model accuracy.
- **Encoding:** Label Encoding was applied to convert all categorical text data into numeric format suitable for algorithms like KNN and Random Forest.
- **Data Splitting:** The dataset was split into **80% training** and **20% testing** sets.

### 3.2 Machine Learning Models
Two classification algorithms were implemented and compared:
1.  **K-Nearest Neighbors (KNN):** Selected for its simplicity and effectiveness on balanced, structured datasets.
2.  **Random Forest:** Selected for its robustness, ability to handle categorical features, and high accuracy in prior literature.

### 3.3 Evaluation Technique
- **10-Fold Cross-Validation:** Used to robustly evaluate model performance and prevent overfitting.
- **Metrics:** Accuracy, Precision, Recall, F1-Score, and Confusion Matrix.

## 4. Results & Performance

| Model | Evaluation Metric | Result |
|-------|-------------------|--------|
| **KNN** | Mean CV Accuracy (10-Fold) | **94.83%** |
| | Test Set Accuracy | 99.57% |
| **Random Forest** | Test Set Accuracy | **100.00%** |

- **Random Forest** achieved perfect classification on the test set with **zero misclassifications**.
- **KNN** performed exceptionally well but had a few misclassifications (7 false positives/negatives in total on the test set).

## 5. Conclusion
Both models demonstrated high effectiveness. However, **Random Forest** outperformed KNN by achieving 100% accuracy, making it the most reliable choice for this safety-critical task of identifying poisonous mushrooms.

## 6. Dependencies
To run the notebook `mushroom test 2.ipynb`, ensure you have the following Python libraries installed:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```
