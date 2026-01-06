# Diabetes Risk Prediction Using Machine Learning

## Overview

This project implements a **lifestyle-based diabetes risk awareness system** using supervised machine learning techniques.
The system estimates the **risk of diabetes** based on self-reported lifestyle, demographic, and basic health indicators. It is **not a medical diagnostic tool** and is intended solely for **early risk awareness and educational purposes**.

The models are trained using the **CDC Diabetes Health Indicators dataset**, which is derived from the Behavioral Risk Factor Surveillance System (BRFSS). The dataset contains large-scale survey data collected through standardized public health questionnaires.

---

## Problem Context

Diabetes is a major global public health concern, and early awareness of risk factors plays an important role in prevention and lifestyle intervention.
In many contexts, especially resource-limited settings, access to clinical tests and laboratory diagnostics may be limited. This motivates the use of **non-clinical, self-reported data** to estimate diabetes risk at an early stage.

This project focuses on:

* Using **non-invasive lifestyle data**
* Handling **class imbalance** realistically
* Producing **probability-based risk estimates** rather than hard diagnoses

---

## Dataset Description

* **Source**: CDC Diabetes Health Indicators (BRFSS-based survey data)
* **Type**: Public, anonymized, self-reported survey dataset
* **Features include**:

  * Lifestyle factors (smoking, physical activity, alcohol consumption)
  * Demographic attributes (age group, sex, education, income category)
  * Health indicators (BMI, general health, mental health days, physical health days)
* **Target variable**:

  * `Diabetes_binary`

    * `0` → Non-diabetic
    * `1` → Diabetic

No clinical measurements (such as blood glucose or lab values) are used.

---

## Machine Learning Approach

The project follows a **structured machine learning pipeline**:

1. **Data loading and cleaning**
2. **Feature preprocessing and encoding**
3. **Train–test splitting with stratification**
4. **Model training**
5. **Model evaluation using multiple metrics**
6. **Probability-based risk prediction for new users**

The following supervised learning algorithms were implemented and evaluated:

* Logistic Regression (baseline and class-balanced)
* K-Nearest Neighbors (KNN)
* Decision Tree
* Random Forest (standard and class-balanced)
* XGBoost (with class imbalance handling)

Class imbalance is explicitly addressed using:

* `class_weight='balanced'` (where applicable)
* `scale_pos_weight` for XGBoost

---

## Evaluation Metrics

Model performance is evaluated using multiple metrics to provide a realistic assessment:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-score**
* **Confusion Matrix**
* **ROC–AUC score**

ROC–AUC is used as a primary comparison metric because it reflects the model’s ability to distinguish between diabetic and non-diabetic cases across decision thresholds.

---

## Risk Awareness Output

Instead of producing a medical diagnosis, the system outputs:

* A **binary risk classification** (low/high risk)
* A **probability score** indicating estimated diabetes risk

This design choice aligns with ethical AI principles and public health use cases.

---

## Predicting for New Users

The project includes a reusable prediction function that:

* Accepts new user inputs
* Applies the same preprocessing logic used during training
* Produces a diabetes risk prediction and probability

This allows repeated predictions without re-running the entire pipeline.

---

## Tools and Technologies Used

* **Programming Language**: Python
* **Libraries**:

  * pandas, numpy
  * scikit-learn
  * xgboost
  * matplotlib, seaborn
* **Environment**: Jupyter Notebook

---

## Ethical Considerations

* This system **does not diagnose diabetes**
* Predictions are based on **self-reported data**, which may contain bias or inaccuracies
* Users should always be advised to consult qualified healthcare professionals for medical decisions

---

## Project Structure

```
├── DiabetesPrediction.ipynb
├── README.md
├── LICENSE
```

---

## License

This project is released under the **MIT License**.
The dataset used is publicly available and subject to the original data provider’s terms.

---

## Academic Note

This project was developed as part of an academic AI coursework.
All implementation decisions, evaluations, and interpretations were performed with a focus on transparency, reproducibility, and ethical use of machine learning.

---
