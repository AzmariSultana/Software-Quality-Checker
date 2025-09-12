# Software-Quality-Checker
This project predicts the quality of software modules (Low, Medium, High) using supervised machine learning models trained on static code metrics. The goal is to help developers identify modules that require more attention, testing, and refactoring.

# Overview
Software quality is a critical factor in ensuring reliability, minimizing bugs, and maintaining long-term project sustainability. In this project, we apply machine learning to classify software modules into High, Medium, or Low quality categories.

# Dataset
Size: 1600 records

Attributes: 9 features (quantitative + categorical)

Target variable: Quality_Label (Low, Medium, High)

# Features

1.Quantitative:

- Lines_of_Code

- Cyclomatic_Complexity

- Num_Functions

- Code_Churn

- Comment_Density

- Num_Bugs

- Code_Owner_Experience

2.Categorical:

- Has_Unit_Tests (Yes/No)

# Pre-processing

- Missing values → replaced with median for numeric features.

- Categorical encoding → converted to binary/numeric (e.g., Yes=1, No=0).

- Scaling → StandardScaler applied for consistent feature range.

- Data split → 70% training, 30% testing (stratified to preserve balance).

# Models & Results
1. Decision Tree 

  - Accuracy: 32.08%

  - Macro-F1: ~0.32

  - Strengths: Interpretable, works with mixed data types.

2. Naive Bayes 

  - Accuracy: 35.42% (best)

  - Macro-F1: ~0.34

  - Weakness: Confused Low vs. Medium quality due to overlapping features.

3. Neural Network 

  - Accuracy: 29.79%
    
  - Macro-F1: ~0.29
    
  - Struggled due to small dataset & class imbalance.

# Project Setup Guide

1. Clone the repository

2. Open in Google Colab

  - Go to Google Colab
  
  - Upload Notebook or open the notebook directly from GitHub.

3.Upload Dataset to Google Drive

  - Upload the dataset to your Google Drive (e.g., inside a folder datasets/).

Mount Google Drive in Colab:

```
from google.colab import drive
drive.mount('/content/drive')
```

4.Change Dataset Path in Code
```
df = pd.read_csv("/content/drive/MyDrive/datasets/software_quality_dataset.csv")
```

5.Run the notebook

  - Execute all cells step by step to train and test the model.
