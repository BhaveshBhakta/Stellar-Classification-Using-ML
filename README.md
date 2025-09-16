## Stellar Classification

### Project Overview

This project aims to classify **celestial objects** from the Sloan Digital Sky Survey (SDSS) into one of three categories: **Star, Galaxy, or Quasar (QSO)**. By analyzing a dataset of photometric measurements (magnitudes) and other astronomical properties, the goal is to develop a machine learning model that can accurately distinguish between these cosmic objects. This is a foundational task in astrophysics for cataloging and studying the universe.

-----

### Technical Highlights

  * **Dataset**: [Kaggle - Stellar Classification Dataset - SDSS17](https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17)
  * **Size**: 100,000 entries, 18 columns.
  * **Key Features**:
      * **Photometric Magnitudes**: `u`, `g`, `r`, `i`, `z`.
      * **Other Properties**: `redshift`, `alpha`, `delta`, `run_ID`, `cam_col`, `field_ID`, etc.
  * **Approach**:
      * **Data Cleaning**: Irrelevant columns that are unique identifiers (`obj_ID`, `alpha`, `delta`, `run_ID`, `rerun_ID`, `cam_col`, `field_ID`, `fiber_ID`) were dropped.
      * **Outlier Handling**: The Local Outlier Factor (LOF) algorithm was used to detect and remove outliers from the dataset.
      * **Exploratory Data Analysis**: Histograms, box plots, and a pairplot were used to visualize data distributions and relationships between features and the target class. A heatmap was generated to show feature correlations.
      * **Handling Class Imbalance**: The original dataset is highly imbalanced (`Galaxy`: 50000, `Star`: 49978, `QSO`: 22). `SMOTE` was applied to balance the classes.
      * **Data Scaling**: `StandardScaler` was applied to all feature columns to ensure they are on a similar scale.
      * **Multi-class Classification**: The target variable `class` has three distinct categories: 'Star', 'Galaxy', and 'QSO'.
      * **Models Used**:
          * Logistic Regression, Ridge Classifier, SVC, Random Forest, XGBoost, AdaBoost, Gradient Boosting, Bagging, Decision Tree.
  * **Best Accuracy**:
      * **97.7%** with XGBoost Classifier.
      * **97.4%** with Random Forest Classifier.
      * **96.3%** with AdaBoost, Gradient Boosting, and Bagging classifiers.

-----

### Purpose and Applications

  * **Automated Astronomical Object Classification**: Enables astronomers to quickly and accurately classify millions of celestial objects from large surveys.
  * **Catalyst for Discovery**: Assists in identifying new quasars, stars, and galaxies, accelerating research in cosmology and stellar evolution.
  * **Research Tool**: Provides a foundational model for studying the properties and distribution of different cosmic objects.
  * **Data-driven Science**: Demonstrates the power of machine learning in processing and making sense of massive astronomical datasets.

-----

### Installation

Clone the repository and extract the data from the zip file.

Install the necessary libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn imbalanced-learn xgboost
```

-----

### Collaboration

We welcome contributions to improve the project. You can help by:

  * Performing comprehensive hyperparameter tuning and cross-validation for the top-performing models to ensure robustness.
  * Exploring the use of different outlier detection and handling methods.
  * Investigating the impact of the `SMOTE` technique on the model's performance on the original, imbalanced data.
  * Adding explainability (e.g., SHAP or LIME) to understand which photometric magnitudes are the most critical predictors of each celestial class.
