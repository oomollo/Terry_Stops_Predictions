## Terry Traffic Stops Prediction for Supreme Court 

## Overview
The project Terry Stop Arrest Prediction leverages machine learning to uncover patterns in police stop data and provide actionable insights into arrest outcomes. It is designed to support law enforcement agencies in identifying key factors influencing arrest decisions and promoting fairness, accountability, and transparency in policing practices.

## Business Problem
Increased public concern over fairness and accountability in policing has put pressure on law enforcement agencies to better understand the factors influencing arrest decisions—especially during discretionary encounters like Terry Stops. Without clear, data-driven insight into what drives these outcomes, agencies risk perpetuating bias, losing public trust, and facing legal and reputational consequences.

This project aims to analyze historical Terry Stop data to uncover patterns associated with arrests. By identifying key predictive factors and assessing the role of sensitive attributes like race and gender, we can offer actionable recommendations to support equitable and transparent policing practices.

Key Business Questions:

• Are certain age groups more likely to be arrested during a Terry Stop?

• Does the subject’s perceived race or gender influence the likelihood of an arrest or frisk?

• How do arrest and frisk rates vary across different subject age groups?

• Do officer demographics (e.g., gender, race, age) influence arrest outcomes?

• Are there patterns in arrest decisions linked to specific officers or squads?

• Are subjects more likely to be frisked or arrested when certain weapon types are involved?

• Are certain precincts, sectors, or beats more prone to arrests or frisks?

### Dataset Summary

Source: Terry Stop reports

Features Used:

Subject Age Group

Weapon Type

Frisk Flag

Officer Gender and Race

Subject Perceived Gender and Race

Initial Call Type

Reported Year

Target Variable: Arrest Flag (0 = No Arrest, 1 = Arrest)

## Data Preparation

1. Cleaned and standardized the dataset

2. One-hot encoded categorical features

3. Scaled numerical features using StandardScaler

4. Addressed class imbalance using resampling techniques

## Models Used

1. Logistic Regression

Simple, interpretable baseline model

Performs well on majority class (no arrest) but struggles on minority class (arrest)

ROC-AUC: 0.9734

2. Random Forest

Ensemble model capturing complex patterns

Better performance on arrest prediction with improved recall

ROC-AUC: 0.9741

## Feature Importance Insights

**Weapon Type (None)** and **Frisk Flag** were the top predictors of arrest.

Subjects frisked were significantly more likely to be arrested.

Arrests often occurred even when no weapon was present.

## Conclusion

**Logistic Regression** demonstrates high performance on the majority class (non-arrest), with precision and recall values of 0.99 and 0.96 respectively. However, it underperforms on the minority class (arrest), yielding a precision of 0.45 and recall of 0.73. Despite its strong ROC-AUC score of 0.9734, the model struggles with class imbalance, making it less effective at correctly identifying positive arrest instances. Nonetheless, its simplicity, interpretability, and computational efficiency make it suitable for baseline modeling or when model transparency is required.


**Random Forest** provides a more balanced classification capability across both classes. It achieves similar overall accuracy (95.03%) and a slightly higher ROC-AUC score (0.9741), while improving recall for the arrest class to 0.80. This indicates better sensitivity to the minority class. Random Forest is more robust in handling imbalanced datasets and capturing complex feature interactions, making it a better fit when maximizing recall and overall detection of arrest outcomes is a priority.


## Recommendations

Use **Random Forest** for operational prediction tasks due to better arrest detection performance.
As shown in feature importance analysis:

**Weapon Type (None)**: This was the strongest predictor of arrest likelihood. It suggests that the absence of a weapon is strongly associated with decisions not to arrest, possibly indicating a lower perceived threat.

**Frisk Flag**: The presence of a frisk is another strong signal, likely correlated with heightened suspicion or safety concerns during the stop.