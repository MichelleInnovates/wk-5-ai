# wk-5-ai
# 🏥 AI Patient Readmission Predictor

![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen)
![Python Version](https://img.shields.io/badge/Python-3.9%2B-blue)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

A machine learning model to predict the 30-day readmission risk for patients at discharge. This project was developed as part of an AI workflow case study to identify at-risk patients and enable proactive post-discharge care.



## 🎯 Table of Contents

* [Problem Definition](#-problem-definition)
* [Technical Workflow](#-technical-workflow)
* [Installation](#-installation)
* [Usage](#-usage)
* [Model & Evaluation](#-model--evaluation)
* [Ethical Considerations](#-ethical-considerations)
* [Contributing](#-contributing)
* [License](#-license)

---

## 📖 Problem Definition

The goal of this system is to predict the likelihood (High, Medium, Low) of a patient being readmitted to the hospital within 30 days of discharge.

* **Objectives:**
    1.  Reduce preventable readmissions.
    2.  Allocate post-discharge resources (e.g., follow-up calls, home nurses) more effectively.
    3.  Improve patient outcomes.
* **Stakeholders:**
    * Clinicians (Doctors, Nurses)
    * Hospital Administrators
    * Patients and their families

---

## ⚙️ Technical Workflow

This project follows a standard machine learning workflow:

1.  **Data Collection:** Pulls anonymized data from EHRs, medication records, and patient histories.
2.  **Preprocessing:** Cleans data, imputes missing values, and engineers features (e.g., comorbidity index, length of stay).
3.  **Modeling:** Uses a **Logistic Regression** model for its high interpretability in a clinical setting.
4.  **Evaluation:** Validated against a hold-out test set, focusing on **Recall** (to find all at-risk patients) and **Precision** (to avoid "alert fatigue" for clinicians).
5.  **Deployment:** Served via a secure, HIPAA-compliant REST API for integration into the hospital's EHR system.

---

## 🚀 Installation

To set up this project locally, follow these steps.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/readmission-predictor.git](https://github.com/your-username/readmission-predictor.git)
    cd readmission-predictor
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: `requirements.txt` would contain libraries like `pandas`, `scikit-learn`, `flask`, etc.)*

---

## 💻 Usage

There are two main ways to use this project.

### 1. Run Model Training

To train the model from scratch using the (anonymized) data in the `/data` directory:

```bash
# This script runs the full preprocessing and training pipeline
python train.py