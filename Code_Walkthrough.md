# Code Walkthrough: BBB Penetrability Prediction

This document provides a brief step-by-step explanation of the code used to predict drug permeability across the blood-brain barrier (BBB) using machine learning.

## 1. Library Imports
The script begins by importing essential libraries:
- `pandas`, `numpy`: Data handling and numerical operations
- `matplotlib.pyplot`, `seaborn`: Data visualisation
- `sklearn`: Machine learning tools for model training, evaluation, and preprocessing
- `rdkit`: Used to compute molecular descriptors from SMILES strings

## 2. Data Loading and Preprocessing
- The dataset is loaded using `pandas`.
- The `SMILES` column (representing molecular structures) is processed using RDKit to generate over 200 molecular descriptors.
- Duplicates are removed, and missing values are handled.
- The `Class` column (BBB+ or BBB-) is retained for classification.

## 3. Feature Engineering
- Molecular descriptors are calculated using RDKit for each compound.
- These descriptors form the input features for the machine learning models.

## 4. Exploratory Data Analysis (EDA)
- **Box plots and histograms**: Used to visualise the distribution of top molecular descriptors.
- **Correlation heatmap**: Identifies relationships and multicollinearity among descriptors.
- Descriptors like TPSA, NOCount, and Partial Charge metrics are highlighted as potentially important features.

## 5. Model Building
Three classification models are applied:
- **Random Forest**
- **Logistic Regression**
- **Support Vector Machine (SVM)**

Each model is trained on the processed features and evaluated using:
- Accuracy
- Confusion matrix
- ROC curve (for Logistic Regression)

## 6. Model Evaluation
- **Random Forest** achieved ~84.3% accuracy and strong recall for BBB+.
- **Logistic Regression** showed ~80.9% accuracy but some imbalance in class performance.
- **SVM** performed moderately with a good confusion matrix but unusual AUC value (~0.13), suggesting potential issues with evaluation or class imbalance.

## 7. Observations
- Feature distributions and correlations offer insight into chemical characteristics influencing BBB permeability.
- Class imbalance is a major factor affecting performance—oversampling techniques like SMOTE are suggested but not implemented.

## Conclusion
The code implements a full ML pipeline from preprocessing to evaluation. Improvements such as PCA, SMOTE, and more robust validation could enhance results further.

