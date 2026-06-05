# Credit Risk Modeling Project (PD, EL, Stress Testing)

## Overview
This project develops a Credit Risk Probability of Default (PD) model using Logistic Regression.  
The model estimates borrower default risk and computes Expected Loss (EL) using a standard credit risk framework.

---

## Objective
- Predict Probability of Default (PD)
- Estimate Expected Loss using:
  
  EL = PD × LGD × EAD

- Identify key drivers of credit risk
- Perform stress testing on portfolio exposure

---

## Project Structure
credit-risk-model/
├── notebooks/
│   └── credit_risk_model.ipynb
├── data/
├── README.md

---

## Dataset Features
- loan_amnt: Loan amount
- int_rate: Interest rate
- annual_inc: Annual income
- dti: Debt-to-income ratio
- loan_status: Target variable (default / non-default)

---

## Methodology

### Data Preprocessing
- Handled missing values
- Converted interest rate to numeric format
- Selected key financial variables

### Target Variable
Default defined as:
- Charged Off
- Default
- Late (31–120 days)

### Model
- Logistic Regression classifier
- Train/test split (80/20)
- Feature scaling applied

### Evaluation
- ROC-AUC score
- ROC curve analysis

### Risk Framework
- Probability of Default (PD)
- Loss Given Default (LGD = 0.6 assumed)
- Exposure at Default (EAD = loan amount)

---

## Key Results
- AUC Score: 0.68
- Strongest predictor: Interest rate
- Income has a negative relationship with default risk
- Model provides interpretable risk relationships

---

## Expected Loss Framework
Expected Loss is calculated as:

EL = PD × LGD × EAD

This allows estimation of credit risk exposure at an individual loan level.

---

## Stress Testing
The portfolio is evaluated under stress scenarios:
- 1.2x PD shock
- 1.5x PD shock
- 2.0x PD shock

Results show that expected loss increases significantly under stressed conditions.

---

## Key Insights
- Interest rate is the strongest driver of default probability
- Higher income reduces default risk
- Debt-to-income ratio increases risk exposure
- Loan amount has a weaker effect on default probability

---

## Future Improvements
- WOE / IV feature engineering
- Credit scorecard development (300–850 scaling)
- Model calibration for PD accuracy
- Advanced ML models (XGBoost, Random Forest)
- Portfolio segmentation analysis

---

## Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib


![ROC Curve](roc_curve.png)
![Stress Testing](stress_testing.png)
