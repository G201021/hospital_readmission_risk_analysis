
## Business Problem

Hospitals can face financial penalties when patients are readmitted within 30 days of discharge. In this project, I analyzed 10 years of data from 130 U.S. hospitals to find patient factors, diagnoses, and care patterns linked to higher readmission risk.

The goal was to identify which patients are more likely to be readmitted so hospitals can focus follow-up care on higher-risk patients and reduce avoidable readmissions.

## Data & Tools

- **Dataset:** Diabetes 130-US Hospitals for Years 1999–2008 from the UCI Machine Learning Repository. The dataset contains about 100,000 patient encounters from 130 U.S. hospitals.
- **Database:** MySQL Workbench
- **SQL Used:** CTEs, window functions, CASE statements, subqueries, and joins

## Approach

- **Data Cleaning:** Replaced missing-value placeholders with `NULL`, removed a column that was about 97% empty, kept one encounter per patient to reduce duplicate bias, and removed hospice and inactive patients.
- **Exploratory Analysis:** Compared readmission rates across factors such as age, admission type, diagnosis, and previous hospital visits.
- **Risk Analysis:** Used CTEs and window functions to identify and rank higher-risk patients. I also grouped patients based on medication use and number of diagnoses and compared diagnosis categories against the overall readmission rate.
- **Results:** Used the analysis to identify several patterns associated with higher readmission risk.

## Key SQL Techniques

- Used **CTEs** to create reusable patient groups for multiple analyses.
- Used **`RANK()`** and **`NTILE()`** window functions to rank patients and divide them into risk groups.
- Used **`CASE` statements** to turn patient data into easier-to-understand risk categories.
- Used **subqueries** to find diagnosis groups with readmission rates above the overall average.
- Used **joins** to connect hospital codes with readable descriptions.

## Findings

1. **Circulatory conditions and diabetes** had some of the highest readmission rates and were above the overall average.
2. Patients with **more previous inpatient visits** were more likely to be readmitted, making past hospital use an important risk factor.
3. **Where a patient was discharged to** was also related to readmission risk. Some discharge locations had higher readmission rates than patients discharged home.
4. **Medication changes and A1C testing** showed patterns related to readmission and helped explore the original research question behind the dataset.

## Recommendations

- Prioritize follow-up care for patients with a history of frequent hospital visits.
- Give additional attention to patients with circulatory conditions or diabetes who show other risk factors.
- Review discharge processes and follow-up procedures for discharge locations associated with higher readmission rates.

