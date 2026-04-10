# TripleTen Integrated Project – Gold Recovery Optimization

This is one of the most advanced projects I completed in the TripleTen Data Science program. It focused on analyzing industrial process data from a gold recovery operation and building predictive models to estimate recovery efficiency at different stages of production.

---

# Gold Recovery Prediction

A gold extraction plant provided data from multiple processing stages — from raw ore feed to rougher and cleaner concentrate outputs. The company wanted to understand how stable the process was and whether machine learning models could reliably predict gold recovery at two key stages:

- **Rougher concentrate recovery**
- **Final concentrate recovery**

The goal of this project was to clean and validate the data, analyze process behavior, and build regression models to predict recovery using a domain‑specific metric (sMAPE).

---

# The Data

The dataset contains industrial measurements from various stages of the gold purification process. Each row represents a snapshot of the process at a given time, including metal concentrations, particle sizes, and output recovery values.

The data was provided by TripleTen.

### Columns (examples)

- **rougher.input.feed_au** — gold concentration in the feed  
- **rougher.output.recovery** — rougher stage recovery (target variable 1)  
- **final.output.recovery** — final stage recovery (target variable 2)  
- **rougher.input.feed_ag** — silver concentration in the feed  
- **rougher.input.feed_pb** — lead concentration in the feed  
- **rougher.input.feed_size** — particle size distribution  
- **cleaner.output.concentrate_au** — gold concentration after cleaner stage  
- **Various f0–fN features** — process measurements across stages  

Each dataset (train, test, full) contains the same structure, but the test set lacks some features that must be handled during preprocessing.

---

# The Process

### 1. Data Preparation
- Verified the correctness of the recovery formula.  
- Identified and removed rows with abnormal or impossible values.  
- Ensured train/test alignment by selecting only features present in both sets.  
- Handled missing values and validated feature distributions.

### 2. Data Analysis
- Examined how **Au, Ag, and Pb concentrations** changed across processing stages.  
- Compared **feed particle size distributions** between training and test sets.  
- Investigated anomalies in total metal concentrations.  
- Visualized process behavior to understand stability.

### 3. Feature Engineering
- Selected relevant features for each target.  
- Standardized numerical features where appropriate.  
- Ensured no data leakage between stages.

### 4. Model Training
Trained regression models for both targets:

- Linear Regression  
- Random Forest Regressor  
- (Optional) Gradient Boosting Regressor  

Implemented the project’s required metric:

- **sMAPE (Symmetric Mean Absolute Percentage Error)**

### 5. Model Evaluation
- Used cross‑validation to compare model performance.  
- Evaluated models on the test set using sMAPE.  
- Compared rougher vs. final recovery prediction difficulty.  
- Assessed whether the model generalized well to unseen data.

### 6. Sanity Check
- Checked for overfitting by comparing train/test sMAPE.  
- Verified that predictions followed expected process behavior.  
- Ensured that the model did not rely on unavailable test‑set features.

---

# Results

The final models produced stable predictions for both rougher and final recovery, with sMAPE values that met project expectations.  
The rougher stage was generally easier to model due to clearer signal in the data, while the final stage required more careful feature selection.

This project strengthened my understanding of:

- Working with messy, real‑world industrial data  
- Building regression models for multi‑stage processes  
- Implementing custom evaluation metrics (sMAPE)  
- Detecting anomalies and validating data quality  
- Comparing model performance across multiple targets  
- Communicating complex process insights clearly  

Please refer to the Jupyter Notebook in this repository for the full workflow, code, and analysis.
