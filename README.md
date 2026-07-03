# Early Disease Detection Pipeline

An end-to-end classification framework engineered to identify patient risk profiles for **Cardiovascular Diseases (CVDs)** based on clinical, demographic, and behavioral vectors. 

Rather than deploying naive models on unrefined datasets, this system implements a clean, production-grade preprocessing layer—standardizing continuous physiological features and hot-encoding categorical matrices—before running competitive cross-model validation tracking.

---

## System Architecture & Preprocessing

The pipeline isolates data preprocessing workflows into an automated transformation matrix, preventing feature weight dominance and data leakage.

* **Feature Engineering & Normalization:** Transformed raw clinical data vectors, converting continuous temporal tracking fields (`age`) from raw operational days into scaled years.
* **Production-Grade Data Pipeline (`ColumnTransformer`):** * Applied `StandardScaler` to continuous physiological features (`ap_hi`, `ap_lo`, `weight`, `cholesterol`, `height`) to maintain a unified mean of 0 and variance of 1.
  * Deployed `OneHotEncoder` matrices to map irregular text categorical fields (`occupation`) into algorithmic-readable binary sparse arrays.
* **Stratified Partitioning:** Implemented a strict train-test split utilizing a stratified ratio allocation (`stratify=y`) to ensure identical baseline distributions of healthy vs. diagnosed vectors across both sets.

---

## Competitive Benchmarking & Diagnostics

The framework evaluates model performance beyond simple surface-level accuracy, isolating **Recall** and **F1-Scores** as the critical clinical diagnostic metrics to mitigate dangerous false-negative predictions.

### Logistic Regression Performance
* **Accuracy** : 0.7262
* **Precision**: 0.7584
* **Recall** : 0.7023
* **F1-Score** : 0.7293

### Decision Tree Classifier Performance
* **Accuracy** : 0.7308
* **Precision**: 0.7645
* **Recall** : 0.7047
* **F1-Score** : 0.7334

### Key Analytical Insight
* **Statistical Impact Valuation:** By extracting individual model coefficients and running feature importance metrics, the pipeline isolates **Systolic Blood Pressure (`ap_hi`)** and **Cholesterol Levels** as the absolute leading statistical predictors governing cardiovascular health risk changes.

---

## Technical Stack

* **Language:** Python 3
* **Data Manipulation & Calculus:** `pandas`, `numpy`
* **Machine Learning Frameworks:** `scikit-learn`
* **Visual Rendering Engines:** `matplotlib`, `seaborn`

---

## Execution & Setup

1. Clone the repository and install the standard native optimization packages:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn openpyxl
