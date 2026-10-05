# Customer Churn Prediction Using Machine Learning

## 📌 Project Overview

This project focuses on predicting customer churn using supervised machine learning techniques.

Customer churn occurs when customers stop using a company's products or services. Predicting customers who are likely to churn can help businesses identify potential problems and take actions to improve customer retention.

The project follows a complete machine learning workflow, starting from data ingestion and validation, followed by exploratory data analysis, data cleaning, preprocessing, model training, hyperparameter tuning, model comparison, and final model evaluation.

---

## 🎯 Project Objectives

The main objectives of this project are:

* Analyze customer data and identify patterns related to churn.
* Clean and preprocess the dataset for machine learning.
* Explore the relationship between customer characteristics and churn.
* Train multiple classification models.
* Tune the machine learning models.
* Compare models using different evaluation metrics.
* Select a suitable final model for customer churn prediction.
* Evaluate the final model using a confusion matrix and ROC curve.
* Analyze feature importance to understand which features contribute most to predictions.

---

## 📊 Dataset

The project uses the **Telco Customer Churn Dataset**.

The dataset contains information about telecommunications customers, including demographic information, account information, subscribed services, and customer churn status.

The target variable is:

* `Churn` — indicates whether the customer left the company.

The raw dataset is stored in:

```text
data/raw/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

---

## 🔄 Machine Learning Workflow

The project follows the workflow below:

```text
Raw Dataset
     ↓
Data Ingestion
     ↓
Data Validation
     ↓
Exploratory Data Analysis
     ↓
Data Cleaning
     ↓
Data Preprocessing
     ↓
Model Training
     ↓
Hyperparameter Tuning
     ↓
Model Comparison
     ↓
Final Model
     ↓
Evaluation
```

---

## 🤖 Machine Learning Models

The following classification algorithms were trained and evaluated:

* Logistic Regression
* Decision Tree
* Random Forest
* K-Nearest Neighbors (KNN)
* Support Vector Classifier (SVC)

Hyperparameter tuning was performed before comparing the final model performance.

---

## 📈 Model Evaluation

The models were evaluated using the following metrics:

* **Accuracy** — measures the overall percentage of correct predictions.
* **Precision** — measures how many predicted churn customers actually churned.
* **Recall** — measures how many actual churn customers were correctly identified.
* **F1 Score** — provides a balance between precision and recall.
* **ROC-AUC** — measures the model's ability to distinguish between churn and non-churn customers.

### Tuned Model Results

| Model               | Accuracy | Precision |     Recall |         F1 |    ROC-AUC |
| ------------------- | -------: | --------: | ---------: | ---------: | ---------: |
| Logistic Regression |   0.8055 |    0.6572 |     0.5588 |     0.6040 |     0.8413 |
| Decision Tree       |   0.7935 |    0.6531 |     0.4733 |     0.5488 |     0.8301 |
| Random Forest       |   0.7559 |    0.5265 |     0.7968 | **0.6340** | **0.8424** |
| KNN                 |   0.7864 |    0.6022 |     0.5749 |     0.5882 |     0.8260 |
| SVC                 |   0.6941 |    0.4575 | **0.8209** |     0.5876 |     0.8359 |

The **Random Forest** model was selected as the final model based on its overall performance, particularly its F1 score and ROC-AUC.

---

## 🌲 Final Model

The final model is a:

**Random Forest Classifier**

The trained model is saved in:

```text
models/final_model.pkl
```

The preprocessing object used for the model is saved in:

```text
models/preprocessor.pkl
```

These files can be loaded later to make predictions on new customer data.

---

## 📊 Visualizations

The project includes several visualizations to analyze the dataset and evaluate the machine learning models.

### Customer Churn Distribution

The churn distribution shows the number of customers who stayed and the number of customers who churned.

```text
reports/figures/churn_distribution.png
```

### Model Comparison

The project compares the F1 scores of the different machine learning models.

```text
reports/figures/model_comparison.png
```

### All Model Metrics

A comparison of Accuracy, Precision, Recall, F1 Score, and ROC-AUC.

```text
reports/figures/all_model_metrics.png
```

### Confusion Matrix

The confusion matrix shows the classification performance of the final model.

```text
reports/figures/confusion_matrix.png
```

### ROC Curve

The ROC curve evaluates the ability of the final model to distinguish between churn and non-churn customers.

```text
reports/figures/roc_curve.png
```

### Feature Importance

Feature importance from the Random Forest model is used to identify the most influential features.

```text
reports/figures/feature_importance.png
```

---

## 📁 Project Structure

```text
customer-churn-ml/
│
├── data/
│   ├── raw/
│   │   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   │
│   └── processed/
│       ├── customer_churn_clean.csv
│       ├── X_train_processed.csv
│       ├── X_test_processed.csv
│       ├── y_train.csv
│       └── y_test.csv
│
├── models/
│   ├── final_model.pkl
│   └── preprocessor.pkl
│
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 02_data_validation.ipynb
│   ├── 03_EDA.ipynb
│   ├── 04_Data_cleaning.ipynb
│   ├── 05_Preprocessing.ipynb
│   ├── 06_model_training.ipynb
│   ├── 07_tuning.ipynb
│   ├── 08_model_comparison.ipynb
│   └── 09_final_model.ipynb
│
├── reports/
│   ├── baseline_model_results.csv
│   ├── final_model_results.csv
│   ├── tuned_model_comparison.csv
│   │
│   └── figures/
│       ├── all_model_metrics.png
│       ├── churn_distribution.png
│       ├── confusion_matrix.png
│       ├── feature_importance.png
│       ├── model_comparison.png
│       └── roc_curve.png
│
├── src/
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🛠️ Technologies and Libraries

The project was developed using Python and the following libraries:

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Jupyter Notebook

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/kareemkhouri2006/customer-churn-ml.git
```

Navigate to the project directory:

```bash
cd customer-churn-ml
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the virtual environment on Windows:

```bash
.venv\Scripts\activate
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Open the project in VS Code and run the notebooks in the following order:

```text
01_data_ingestion.ipynb
02_data_validation.ipynb
03_EDA.ipynb
04_Data_cleaning.ipynb
05_Preprocessing.ipynb
06_model_training.ipynb
07_tuning.ipynb
08_model_comparison.ipynb
09_final_model.ipynb
```

This order follows the complete machine learning workflow from the original dataset to the final model evaluation.

---

## 📌 Key Results

Based on the tuned model comparison:

* **Logistic Regression** achieved the highest accuracy at approximately **80.55%**.
* **SVC** achieved the highest recall at approximately **82.09%**.
* **Random Forest** achieved the highest F1 score at approximately **63.40%**.
* **Random Forest** achieved the highest ROC-AUC at approximately **84.24%**.
* Random Forest was selected as the final model.

The results show that model selection depends on the evaluation metric and the specific objective of the classification problem.

---

## 📚 Project Purpose

This project was developed as a practical machine learning project to apply concepts related to:

* Data preprocessing
* Exploratory Data Analysis (EDA)
* Feature engineering
* Classification
* Hyperparameter tuning
* Model evaluation
* Model comparison
* Feature importance

It demonstrates an end-to-end supervised machine learning workflow for a real-world classification problem.

---

## 👨‍💻 Author

**Kareem Khouri**

Data Science Student
Jordan University of Science and Technology (JUST)
