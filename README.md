# 6001CMD-Customer_Shopping_Behaviour_Machine_Learning

## Overview
This project performs a machine learning analysis of the **Customer Shopping Behaviour** dataset.

The analysis focuses on:

- Machine learning problem formulation
- Supervised vs. unsupervised learning
- Data quality analysis
- Data cleaning
- Data transformation
- Feature engineering
- Class balancing using SMOTE
- Preparation of the dataset for machine learning

The main machine learning problem is **binary classification**, where the target variable is:

**Subscription Status**
- `No = 0`
- `Yes = 1`

---

## Dataset

**Dataset:** Customer Shopping Behaviour Analysis  
**Source:** Kaggle  
**Publisher:** Ankit Raj Mishra

Dataset link:  
https://www.kaggle.com/datasets/ankitrajmishra/customer-shopping-behaviour-analysis

The working dataset contains:

- **5,050 records**
- **17 original attributes**
- Numerical and categorical variables
- Customer demographic, purchasing, product and behavioural information

The CSV file used by the notebook is:

```text
customer_shopping_behavior.csv
```

---

## Project Structure

A recommended GitHub structure is:

```text
customer-shopping-ml/
│
├── README.md
├── customer_shopping_behavior.csv
├── customer_shopping_analysis.ipynb
└── requirements.txt
```

---

## Requirements

### Python

Python **3.10 or newer** is recommended.

### Required Libraries

The project uses the following Python libraries:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn
- Jupyter Notebook

Install all required libraries using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
```

**Important:** Install `scikit-learn`, not `sklearn`.

---

## requirements.txt

You can create a `requirements.txt` file containing:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
jupyter
```

Then install everything using:

```bash
pip install -r requirements.txt
```

---

## Running the Project

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd customer-shopping-ml
```

### 2. Create a Virtual Environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open the project notebook and run the cells in sequence.

---

## Loading the Dataset

Avoid using a computer-specific absolute path such as:

```python
pd.read_csv(r"C:\Users\...\Dataset\customer_shopping_behavior.csv")
```

For GitHub, place the dataset in the project folder and use:

```python
import pandas as pd

df = pd.read_csv("customer_shopping_behavior.csv")
```

This allows the notebook to work on other computers.

---

## Data Quality Analysis

The dataset is investigated for:

- Missing values
- Duplicate records
- Outliers
- Feature distributions
- Skewness
- Correlation
- Class imbalance
- Noise
- Data inconsistencies

The initial analysis identified **2,075 missing values** and **50 duplicate records**.

---

## Preprocessing Pipeline

The preprocessing workflow used in this project is:

```text
Raw Dataset
     ↓
Data Cleaning
     ├── Remove duplicates
     ├── Check invalid/noisy values
     └── Impute missing values
     ↓
Data Transformation
     ├── Log transformation
     └── Standardisation
     ↓
Feature Engineering
     ├── Remove Customer ID
     ├── Create Age Group
     └── Encode categorical variables
     ↓
Train/Test Split
     ↓
SMOTE on Training Data
     ↓
Preprocessed Dataset
```

### Data Cleaning
