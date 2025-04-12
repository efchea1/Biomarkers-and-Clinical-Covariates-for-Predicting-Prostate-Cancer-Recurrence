# Biomarkers-and-Clinical-Covariates-for-Predicting-Prostate-Cancer-Recurrence
Prostate cancer poses high recurrence risks post-prostatectomy. This study assessed whether combining 40 biomarkers with clinical factors (age, PSA, Gleason score, tumor stage) improves 5-year recurrence prediction compared to using clinical covariates alone.


## Statistical Analysis Plan (SAP)
**NOTE:** Only the Statistical Analysis Plan (SAP) and the code used for the data analysis are posted on this repository. The Statistical Analysis Report and the dataset used will not be posted.

## INTRODUCTION
**Prostate cancer (PCa)** is a prevalent health issue, necessitating improved methods for predicting recurrence post-surgery. Multiple biomarkers have been proposed for their potential predictive value. This study evaluates if combining 40 candidate biomarkers with clinical covariates enhances predictive accuracy for PCa recurrence within five years post-prostatectomy. The research specifically addresses the following:
Can these biomarkers be combined with clinical covariates to develop a predictive model for prostate cancer recurrence within five years of prostatectomy?
Does adding the biomarkers to the clinical covariates result in better predictions than using the clinical covariates alone?

## DATASET
The analysis utilizes the "40genes_data.csv" dataset, originating from the University of Minnesota Medical Center, comprising data from 400 men who underwent radical prostatectomy between 1999 and 2008. The dataset contains:
**Clinical Covariates:** Age, preoperative PSA, Gleason score, and tumor stage.
**Biomarkers:** 40 biomarkers standardized to have an SD = 1.

**Modifications:**
Created binary outcome variable for recurrence within five years based on biochemical failure and follow-up time.
Gleason score was recoded as an ordered factor with levels (3+3, 3+4, 4+3, 4+4, 4+5).

Justification: Having the Gleason score as an ordered factor helps in accurately modeling the relationship between Gleason scores and the likelihood of PCa recurrence. It allows the models to recognize the inherent order in the Gleason scores, which can impact the predictions and interpretations.

## EXPLORATORY DATA ANALYSIS (EDA)
A descriptive analysis summarized demographic and clinical variables (Table 1).
Evaluated distributions of age and preoperative PSA via histograms.
Presented frequency distributions for Gleason score and tumor stage.

## METHODS
The analysis will employ:
**Model A (Clinical Covariates Only):** Logistic regression with age, preoperative PSA, Gleason score, and tumor stage.
**Model B (Clinical + Biomarkers):** Penalized logistic regression (LASSO), integrating clinical covariates and biomarkers to address potential overfitting and multicollinearity.

Justification: Logistic regression suits binary outcomes; penalized regression helps select predictors effectively and prevents overfitting, critical given numerous biomarkers.

**Analytic Details**
**Outcome Variable:** Binary recurrence within five years.
**Predictors:** Clinical covariates and biomarkers.
**Adjustments:** Clinical covariates only.
**Observations:** Complete cases only.
**Missing Data:** Complete case analysis if present. However, there were no missing data.
Model Selection & Validation: 10-fold cross-validation for assessing performance.
**Metrics:** Area Under the ROC Curve (AUC), sensitivity, specificity; DeLong test for model comparison.
**Software:** R software (version ≥ 4.0).
**Significance Level:** p-value < 0.05 is considered statistically significant.
