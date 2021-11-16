
# Health Care Provider Fraud Detection Insured with Medicare

## 1. Introduction
![](https://github.com/damayantinaik/Health_care_Fraud_Detection_Medicare/blob/main/Final_report/Health_Care_Fraud_picture.jpg)

Medicare is an U.S Federal government program which provides hospitalization insurance and voluntary medical insurance for elderly person over 65 years. Healthcare provider Fraud is one of the biggest problems for Medicare. Government report claims, the total Medicare spending is increasing exponentially due to frauds in Medicare claims. In general, healthcare fraud is an organized crime in which providers, physicians and beneficiaries act together to make fraud claims.

Succinct, rigorous analysis of Medicare data has yielded many physicians who indulge in fraud. They adopt ways in which an ambiguous diagnosis code is used to adopt costliest procedures and drugs. Insurance companies are impacted badly due to these bad practices. Due to this reason, insurance companies increased their premium and as a result healthcare is becoming costlier day by day.

Healthcare fraud and abuse take place in many forms. Some of the most common types of frauds by providers are:
a) Billing for services that were not provided.
b) Duplicate submission of a claim for the same service.
c) Misrepresenting the service provided.
d) Charging for a more complex or expensive service than was actually provided.
e) Billing for a covered service when the service actually provided was not covered.

# 2. Problem Statement
The goal of this project is to build a Machine Learning (ML) model to predict/classify a Health Care Provider as Potential Fraud or not based on the claims filed by the Provider.  To obtain the best model, different ML classifier models will be built and evaluated using ROC AUC score (Receiver Operating Characteristic - Area Under Curve score) and the model with highest score will be chosen for deployment. 

# 3. Data:
For this project, I collected the data available in Kaggle at the following link:
[](https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis)

There are four datasets: Beneficiary, Inpatient, Outpatient and Train. Here is a short description about each dataset.



