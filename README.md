# Multi-Parameter Signal Analysis for Patient Monitoring

## Intro:  
Given a set of three correlated physiological signals:
- S1: Heart Rate (HR)
- S2: Pulse Rate (PR)
- S3: Respiration Rate (RESP).
  
Loaded the dataset -> _patient_data.mat_ consists of 2 variables:
- _data_ (physiological signals) and _golden_alarms_ (physician annotations)
- _data_ is an array of 3 rows and 30,000 columns.

## 📊 Task 1: Statistical Analysis of Respiration Rate Signal
 - Sampled RESP data at sizes 70, 1000, and 30,000.
 - Computed PMF of Y = floor(X), estimated PDF and CDF.
 - Derived empirical thresholds (a, b) from CDF where 96% of data lies.
 - Compared data to a normal distribution using plots, probability plots, and equations.
 - Calculated normal-distribution-based thresholds for anomaly detection.
   
## 🚨 Task 2: Alarm Generation + Evaluation Using Thresholding
 - Generated alarms using empirical thresholds for HR, PR, and RESP.
 - Coalesced alarms in 10-sample windows.
 - Implemented a majority voter to combine alarms from all signals.
 - Evaluated system performance using physician-labeled golden alarms:
   - Computed false alarm rate, miss detection rate, and overall error probability.
     
## 🧠 Task 3: Feature Selection and Classification with ML and MAP Rules
- Split data into training/testing sets for 9 patients.
- Learned ML and MAP rules using single and paired features.
- Used correlation analysis and decision rule visualization to choose optimal feature pairs.
- Selected 3 patients and identified their best feature pairs based on lowest error.
  
## 📈 Task 4: Joint Hypothesis Testing Using Selected Feature Pairs 
- Built joint likelihood matrices for selected feature pairs.
- Generated ML and MAP decision rules and alarm sequences for testing data.
- Visualized conditional joint PMFs under H0 and H1 in 3D.
- Evaluated performance using false alarms, miss detections, and error rates across 3 patients.
- Compared ML vs MAP performance, drawing insights from selected features and metrics.

## 🤖 Bonus Task: Neural Network vs. Logistic Regression – Classification Performance
- Calculated MAP and ML thresholds based on empirical priors.
- Used black-box neural network outputs and implemented logistic regression.
- Compared both models across MAP/ML thresholds using:
- False alarm rate, miss detection rate, and probability of error.
- Tabulated results and compared with MAP rule from Task 4.
