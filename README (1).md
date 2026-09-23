# WattWise AI — Home Energy Comfort & Anomaly Intelligence

## AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026 | BharatCares

### Project Overview

**WattWise AI** is an end-to-end Data Analytics and AI/ML capstone that analyzes 10-minute household energy observations and combines demand prediction, comfort-context analysis, explainability and anomaly detection.

Instead of simply predicting appliance energy, the project asks a broader analytical question:

> **When does high household energy demand occur together with unusual comfort conditions, and which variables help explain the load?**

### Core Capabilities

- Data cleaning and quality checks
- Time-series feature engineering
- Exploratory Data Analysis
- Hourly energy profiling
- Configurable Comfort–Energy Conflict Index
- Time-ordered appliance-energy prediction
- Linear Regression, Gradient Boosting and Random Forest comparison
- MAE, RMSE and R² evaluation
- Permutation feature importance
- Isolation Forest anomaly detection
- Automated analyst brief
- Exportable result tables
- SDG-oriented recommendations

### Dataset

**UCI Machine Learning Repository — Appliances Energy Prediction**

Official dataset page:
https://archive.ics.uci.edu/dataset/374/appliances%2Benergy%2Bprediction

DOI: **10.24432/C5VC8G**

The dataset contains **19,735 observations** recorded at 10-minute intervals for approximately 4.5 months in a low-energy house. It includes appliance energy use, lighting, indoor temperature/humidity, outdoor weather variables and two random variables. UCI identifies `Appliances` as the target for regression.

The notebook downloads the research dataset automatically from the original GitHub repository, with a UCI URL fallback. A local `energydata_complete.csv` can also be placed beside the notebook.

### Why This Project Is Different

Many student projects stop at “predict energy consumption.”

WattWise AI adds a second analytical layer:

**Energy Demand + Indoor Comfort Context + Anomaly Intelligence**

The project deliberately avoids claiming that high consumption equals “waste.” Instead, it creates a configurable relative **Comfort–Energy Conflict Index** to highlight periods where energy pressure and deviations from the chosen comfort bands occur together.

### Methodology

```text
UCI Energy Dataset
        ↓
Data Quality & Timestamp Processing
        ↓
Time / Lag / Rolling Feature Engineering
        ↓
Exploratory Data Analysis
        ↓
Comfort–Energy Conflict Index
        ↓
Chronological Train/Test Split
        ↓
Regression Model Comparison
        ↓
Permutation Explainability
        ↓
Isolation Forest Anomaly Detection
        ↓
AI Analyst Brief
        ↓
Recommendations
```

### Machine Learning

The notebook compares:

1. Linear Regression
2. Gradient Boosting Regressor
3. Random Forest Regressor

Evaluation metrics:

- MAE
- RMSE
- R²

The last 20% of observations are used as a chronological holdout.

### Explainability

Permutation importance is used to identify variables that the selected model relies on most strongly. This is a model-reliance measure and not causal evidence.

### Anomaly Detection

Isolation Forest flags unusual combinations of energy, environmental and temporal variables. An anomaly is treated as a review candidate, not proof of sensor failure or waste.

### Comfort–Energy Conflict Index

The prototype uses configurable comfort assumptions:

- Indoor temperature: **20°C–24°C**
- Indoor relative humidity: **30%–60%**

The resulting index is relative to the project dataset and is not a universal building standard, AQI, medical measure or regulatory score.

### Setup

#### Google Colab

1. Open Google Colab.
2. Upload `PrathameshJagtap_WattWiseAI.ipynb`.
3. Run the notebook from top to bottom.
4. Internet access is required if the dataset is not already stored locally.

#### Local Jupyter

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
jupyter notebook
```

Open:

```text
PrathameshJagtap_WattWiseAI.ipynb
```

### Outputs

The notebook produces:

- EDA charts
- Hourly energy profile
- Comfort–Energy Conflict Index distribution
- Model comparison table
- Actual vs predicted plot
- Residual distribution
- Permutation importance table and chart
- Anomaly table
- Automated WattWise AI Analyst Brief

It also exports:

```text
model_results.csv
permutation_importance.csv
wattwise_summary.csv
```

### Responsible AI and Limitations

- The dataset represents one historical low-energy house.
- The project should not be generalized to all homes or buildings without validation.
- High energy use does not automatically mean waste.
- Comfort thresholds are configurable assumptions.
- Anomaly detection does not diagnose equipment failure.
- Model performance can change on new buildings or climates.
- Feature importance does not prove causation.

### SDG Alignment

- **SDG 7 — Affordable and Clean Energy**
- **SDG 11 — Sustainable Cities and Communities**
- **SDG 12 — Responsible Consumption and Production**

### Project Deliverables

```text
PrathameshJagtap_WattWiseAI.ipynb
requirements.txt
PrathameshJagtap_ProjectReport.docx
README.md
```

### Author

**Prathamesh Jagtap**

AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026
