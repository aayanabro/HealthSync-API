# HealthSync: Integrated Patient Management & Insurance Analytics

HealthSync is a dual-purpose health-tech solution. It combines a robust **Patient Management System (PMS)** with an **ML-powered Insurance Premium Categorization engine**. Built with FastAPI, the system leverages Pydantic for high-integrity data validation and automated health metric computation.

---

## 🛠️ Tech Stack
* **Backend Framework:** FastAPI (Asynchronous support)
* **Data Validation:** Pydantic v2 (Annotated types & Computed Fields)
* **Machine Learning:** Scikit-Learn (via Pickle serialization)
* **Data Processing:** Pandas (for ML feature engineering)
* **Frontend:** Streamlit (Interactive UI)
* **Storage:** JSON-based persistence

---

## 📂 System Components

### 1. Insurance Predictor (`app.py`)
Predicts insurance premium categories using a machine learning model.
* **Feature Engineering:** Dynamically calculates BMI, Lifestyle Risk, and City Tier from raw inputs.
* **Risk Logic:** Classifies risk levels based on smoking status and BMI thresholds (e.g., High risk if smoker and $BMI > 30$).
* **City Tiering:** Automatically categorizes 50+ Indian cities into Tier 1, 2, or 3 for localized risk assessment.

### 2. Patient Management (`main.py`)
A complete RESTful API for handling medical records.
* **CRUD Operations:** Create, Read, Update, and Delete patient profiles.
* **Automated Verdicts:** Generates medical status (Underweight, Normal, Obese) based on real-time BMI calculations.
* **Data Persistence:** Uses `load_data` and `save_data` functions to maintain state in `patients.json`.

### 3. User Dashboard (`frontend.py`)
A user-friendly Streamlit interface for the insurance model.
* Provides numeric inputs for age, weight, and income.
* Communicates with the FastAPI backend via the `requests` library.

---
