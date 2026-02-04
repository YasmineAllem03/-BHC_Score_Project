#  BHC Score: BioOmics Health Check  Algorithm

**Author:** Yasmine Allem
**Status:** Completed (Jan 2026)

##  Overview
This project develops and validates the **BHC Score** **(BioOmics Health Check)**, a novel algorithm that aggregates multi-omics data into a single health metric (0-100 scale). Using extensive health survey data (NHANES), the algorithm integrates lifestyle, nutritional, and biological markers (Omics) to quantify metabolic health in adults.

##  Methodology
The analysis processes **6,057 adult profiles** through a custom Python pipeline:

### 1. Data Engineering
* **Data Sources:** Merged Demographics, Body Measures, and Laboratory files.
* **Filtration:** Excluded pediatric data (<20 years) and incomplete profiles to ensure statistical quality.

### 2. The Algorithm
The BHC Score is calculated using a **Min-Max Normalization** technique across three categories:
* **Lifestyle:** Sleep Duration, Physical Activity, Smoking Status.
* **Nutrition:** Fiber Intake, Sugar Intake, Alcohol Consumption.
* **Omics:** HbA1c (Glycated Hemoglobin), Vitamin D, Blood Pressure, BMI.

*Note: Negative risk factors (like BMI and Sugar) were inverted so that a higher score always indicates better health.*

##  Key Results
The algorithm was validated using logistic regression and correlation analysis:

* **Sample Size:** N = 6,057
* **Hypertension Prediction:** The score successfully predicts hypertension risk with high statistical significance (p < 0.001).
* **Risk Reduction:** An Odds Ratio of **0.77** was observed, indicating a **23% reduction in hypertension risk** for every 1-point increase in the Health Score.
* **Biological Validity:** The score shows a strong negative correlation with BMI and Age, confirming it accurately reflects biological aging and metabolic status.

##  Technologies Used
* **Language:** Python 3.9
* **Data Processing:** Pandas, NumPy
* **Statistics:** Statsmodels (Logit Regression, Pearson Correlation)
* **Visualization:** Seaborn, Matplotlib
