# Online Shoppers Purchasing Intention Prediction

## Project Overview

This project predicts whether an online visitor session will end in a purchase using real-time browsing behavior, session context, and visitor profile data. The objective is to help e-commerce teams reduce cart abandonment by identifying high-intent visitors early and triggering intelligent interventions such as discount popups, chatbot assistance, or personalized recommendations.

This is a **binary classification problem** where the target variable is:

* **Revenue = True** → Purchase
* **Revenue = False** → No Purchase

---

## Business Problem

E-commerce websites receive thousands of visits every day, but only a small percentage convert into actual purchases. Showing the same popup or offer to every visitor can harm user experience and waste marketing resources.

This project solves that problem by:

* Predicting purchase intent in real time
* Reducing unnecessary interventions
* Protecting revenue by minimizing missed buyers
* Supporting smarter customer engagement strategies

---

## Dataset

* **Dataset Name:** Online Shoppers Purchasing Intention Dataset
* **Source:** UCI Machine Learning Repository
* **Type:** Session-level website browsing data
* **Target Variable:** Revenue

### Key Features

* Administrative pages visited
* Informational pages visited
* Product-related pages visited
* Product-related duration
* Bounce rate
* Exit rate
* Page values
* Month
* Visitor type
* Weekend

---

## Project Workflow

### 1. Data Loading and Understanding

* Imported libraries
* Loaded dataset
* Checked shape, data types, and class distribution

### 2. Data Preprocessing

* Missing value check
* Duplicate removal
* Encoding categorical variables
* Feature scaling
* Train-test split

### 3. Handling Class Imbalance

Since buyer sessions were the minority class, **SMOTE** was used on the training data to generate synthetic buyer examples.

### 4. Exploratory Data Analysis

Key behavioral insights were extracted using visualizations:

* High page values strongly indicate purchase intent
* November shows peak conversions
* Higher exit rates reduce conversion probability
* Deeper engagement matters more than broad browsing

### 5. Model Building

The following machine learning models were trained and compared:

* Logistic Regression
* Decision Tree
* Random Forest
* XGBoost

### 6. Model Evaluation

Evaluation metrics used:

* Recall
* F1 Score
* Precision
* ROC-AUC

---

## Model Performance Summary

| Model               | F1 Score | Recall | Precision | ROC-AUC |
| ------------------- | -------: | -----: | --------: | ------: |
| Logistic Regression |    0.653 |  0.762 |     0.572 |   0.891 |
| Decision Tree       |    0.671 |  0.783 |     0.587 |   0.919 |
| Random Forest       |    0.664 |  0.744 |     0.600 |   0.922 |
| XGBoost             |    0.630 |  0.853 |     0.499 |   0.924 |

### Best Model Insights

* **Decision Tree:** Best balance using F1 Score
* **XGBoost:** Best buyer detection using Recall
* **XGBoost:** Best ranking performance using ROC-AUC

---

## Business Deployment Logic

The final model output is converted into actionable intervention rules:

* **> 70% probability:** Show discount popup
* **40%–70% probability:** Trigger chatbot assistance
* **< 40% probability:** No intervention

This enables a **real-time marketing decision engine**.

---

## Key Business Insights

* High-value product pages drive conversions
* Returning visitors need stronger personalization
* Weekday campaigns perform better
* Exit behavior is a major warning signal
* Product engagement depth matters most

---

## Future Improvements

* Hyperparameter tuning
* Better precision–recall threshold optimization
* Add cart activity and clickstream features
* Real-time API deployment
* Continuous model retraining

---

## Tools and Libraries Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Imbalanced-learn (SMOTE)
* XGBoost

---

## Project Outcome

The project demonstrates how machine learning can transform browsing session data into revenue-saving business actions. By predicting purchase intention before the customer exits, the company can improve targeting, reduce cart abandonment, and optimize customer experience.
