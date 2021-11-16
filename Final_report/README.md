
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

https://www.kaggle.com/rohitrox/healthcare-provider-fraud-detection-analysis

There are four datasets: Beneficiary, Inpatient, Outpatient and Train. Here is a short description about each dataset.

### A. Beneficiary data
This dataset contains Medicare beneficiaries KYC (Know Your Customer) details; their health conditions, gender, Insurance coverage, race and region (county and state) they belong to.

### B. Inpatient data
This dataset provides claims details filed by the Providers for Beneficiaries those treated  in hospitals. It lists Physicians, admission and discharge dates, diagnosis and procedure codes, and Claim amount reimbursed. 

### C. Outpatient data
This dataset provides claims detail filed by the Providers for Beneficiaries who visited hospitals but  not admitted there for treatment.  It includes data on Physicians, Diagnosis and Procedure codes, claims amount reimbursed.

### D: Train data
This dataset lists Providers as Potential Fraud or not.

All the four datasets are large with following rows and columns:

Beneficiary: (138556, 25)

Inpatient: (40474, 30)

Outpatient: (517737, 27)

Train: (5410, 2)

# 4. Data Wrangling:

The raw data obtained from Kaggle was not clean enough to carry out Exploratory Data Analysis (EDA) or further Machine Learning(ML) buildding, hence Data wrangling was carried out on them.  These are the  few issues observed  and fixed them as follows:

**Problem-1:** Datetime columns were listed as object.

**Solution:** These are converted to Timestamp.


**Problem-2:** The renal disease indicator column has listed two values “Y” and 0.

**Solution:** The “Y” was assigned to 1 and then the converted to converted to numeric.


**Problem-3:** In the ‘DOD’ column, most of the values (97%) were missing.

**Solution:** The entire column was dropped from the dataframe. 


**Problem-4:** In all three Physicians columns (Attending Physician, Operating Physician, Other Physician), there were many null values.

**Solution:** The null values were replaced with 0 (here it was assumed that missing values represent physicians were absent, not data is missing). Also, the entries with a value were replaced with 1, thus the column became categorical.


**Problem-5:** For diagnosis/procedure columns, some entries were missing.

**Solution:** The missing values were replaced with 0 (assuming diagnosis/procedures were really not carried out, because for a treatment all diagnosis/procedures need not have to be carried out). The entries values were replaced with 1.


**Problem-6:** The Gender column values were 1 and 2.

**Solution:** The entries with 2 were replaced with 0.


**Problem-7:** In Inpatient dataset, few of the Deductible amount paid entries were missing, these null values were constituting only 2% of the total.

**Solution:** The null values were replaced with median in that column because the entries in that column was only one value, hence its mean, median and mode were same.


**Problem-8:** The Potential Fraud column had two values “Yes” and “No”.

**Solution:** The “Yes” and “No ” were replaced with 1 and 0 respectively.

# 5. Exploratory Data Analysis (EDA)
The EDA showed 
•	Mean IPAnnualReimbursementAmt, Mean OPAnnualReimbursementAmt: 3660, 1298
•	Mean IPAnnualDeductibleAmt, Mean OPAnnualDeductibleAmt: 340, 377
•	There are 9.3% Potential Fraud Providers as compared to 90.7% non-Potential Fraud Providers. Here is bar plot below showing both categories:




