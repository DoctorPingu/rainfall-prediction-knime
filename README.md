# Rainfall Prediction Using KNIME

This repository contains two distinct KNIME workflows designed for rainfall data analytics using historical weather observations.  

- The **Exploratory Analysis** workflow focuses on understanding the dataset, cleaning and preprocessing it, and performing feature analysis to derive meaningful insights.  
- The **Predictive Modeling** workflow builds on these insights by applying machine learning algorithms to predict whether it will rain tomorrow (`RainTomorrow`) based on weather attributes.

Both workflows were developed as part of a data analytics subject to demonstrate the full lifecycle of a data-driven project: from raw data exploration to predictive modeling and evaluation.

---

## Core Features

### **Exploratory Analysis Workflow**
- Performs **data cleaning** by handling missing values, removing irrelevant columns, and formatting attributes for analysis.
- Generates **summary statistics** (mean, median, mode, range) for numerical attributes.
- Produces **visualisations** such as histograms, boxplots, and scatter plots to identify trends and outliers.
- Evaluates relationships between attributes (e.g., correlations between temperature, humidity, and rainfall).
- Outputs an **Excel file (`Rainfall_Exploratory_Analysis_Results.xlsx`)** documenting preprocessing results and insights.

### **Predictive Modeling Workflow**
- Builds on the cleaned dataset from the exploratory phase.
- Applies **preprocessing techniques** such as:
  - Column filtering
  - Normalisation/scaling of numerical features
  - Oversampling using SMOTE to handle class imbalance
- Trains **multiple classifiers**:
  - Decision Tree
  - Random Forest
  - K-Nearest Neighbour (KNN)
  - Naïve Bayes
  - Multi-Layer Perceptron (MLP)
  - Support Vector Machine (SVM)
- Evaluates models using:
  - **Accuracy, Precision, Recall, F1-score, AUC**
- Produces **predictions for an unseen dataset**, formatted for Kaggle submission.

---

## Implementation Details / Technology Used

- **Platform:** [KNIME Analytics Platform]
- **Exploratory Analysis Techniques:**
  - Data cleaning and formatting
  - Missing value imputation
  - Statistical summaries and visualisations
- **Predictive Modeling Techniques:**
  - Preprocessing: Normalisation, column filtering, SMOTE
  - Supervised learning algorithms (Decision Tree, Random Forest, KNN, Naïve Bayes, MLP, SVM)
  - Evaluation metrics for classification models

---

## Execution Instructions

### Prerequisites
- Install [KNIME Analytics Platform](https://www.knime.com/downloads) (version 5.2 or later recommended).

### Opening a Workflow
1. Download or clone this repository.
2. In KNIME: **File → Import KNIME Workflow...**
3. Select the appropriate workflow:
   - **Exploratory Analysis:**  
     `exploratory_analysis/workflow/Rainfall_Exploratory_Analysis_Workflow.knwf`
   - **Predictive Modeling:**  
     `predictive_modeling/workflow/Rainfall_Predictive_Modeling_Workflow.knwf`

### Running the Workflows
1. Place the required CSV files inside the respective `data/` folders.
2. Update CSV Reader node paths in KNIME if necessary.
3. Execute all nodes to run the workflows.

---

## Outputs

### **Exploratory Analysis Output**
- Preprocessing summary saved to **`Rainfall_Exploratory_Analysis_Results.xlsx`**.
- Visualisations for attribute distributions, outliers, and correlations.
- Cleaned dataset ready for use in predictive modeling.

### **Predictive Modeling Output**
- Trained models with evaluation metrics for each classifier.
- Kaggle-ready CSV prediction files for each algorithm:
  ```
  Decision Tree.csv
  Random Forest.csv
  K Nearest Neighbour.csv
  Naive Bayes.csv
  MultiLayer Perceptron.csv
  Support Vector Machine.csv
  ```

Each CSV file follows this format:

```
Row ID,PredictRainTomorrow
1,0
2,1
3,0
4,0
...
```

---

## Key Differences Between the Two Workflows

| **Aspect**              | **Exploratory Analysis**                                        | **Predictive Modeling**                                  |
|--------------------------|----------------------------------------------------------------|---------------------------------------------------------|
| **Goal**                | Understand the dataset, clean and preprocess data              | Build and evaluate models to predict rainfall          |
| **Main Output**         | Insights, statistics, cleaned dataset, and preprocessing summary | Predictions for unseen data and model evaluation metrics |
| **Techniques Used**     | Data cleaning, visualisation, basic statistics                 | Machine learning, evaluation metrics, SMOTE oversampling |
| **Final Deliverable**   | `Rainfall_Exploratory_Analysis_Results.xlsx`                   | CSV files with predicted `RainTomorrow` values         |

---

## Assumptions / Limitations

- Both workflows assume the dataset follows the same structure as `WeatherData.csv`.
- Predictive modeling assumes a binary classification target (`RainTomorrow` = Yes/No).
- Model performance is specific to the dataset; retraining is required for new datasets.
- SMOTE is used to address class imbalance but may affect generalisation if data distribution differs significantly.

---

## License

## License
This project is licensed under the [MIT License](LICENSE).  
You are free to use, modify, and distribute this project, provided proper credit is given.