# Cardiovascular_Risk_Prediction.

INTRODUCTION

Heart disease is one the major cause of moribity and mortality globally. A heart attack happens when the flow of oxygen-rich blood to a section of heart muscle suddenly becomes blocked and the heart can’t get oxygen. If blood flow isn’t restored quickly, the section of heart muscle begins to die.

Doctors and Scientists across the globe have started to look into Machine Learning Techniques to develop screening tools.

OBJECTIVE:

In this project, we shall be giving you a walk through on the development of a screening tool for predicting whether a patient has a 10-year risk of developing coronary heart disease (CHD) based on their present health conditions using different Machine Learning Techniques.

PROBLEM STATEMENT:

Heart disease is the leading cause of morbidity and mortality worldwide, killing more people each year than any other cause. In this project, we shall be giving you a walk through on the development of a screening tool for predicting whether a patient has a 10-year risk of developing coronary heart disease (CHD) using different Machine Learning techniques. The given dataset provides the patients’ information. It includes over 3,390 records and 17 attributes. Each attribute is a potential risk factor. There are both demographic, behavioural, and medical risk factors given for the analysis.


Data Description:
The classification goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD). The dataset provides the patients’ information. It includesover 4,000 records and 15 attributes.

Variables

Each attribute is a potential risk factor. There are both demographic, behavioral, and medical risk factors.

Data Description Demographic:

• Sex: male or female("M" or "F")

• Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous) Behavioral

• is_smoking: whether or not the patient is a current smoker ("YES" or "NO")

• Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.)

Medical( history)

• BP Meds: whether or not the patient was on blood pressure medication (Nominal)

• Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)

• Prevalent Hyp: whether or not the patient was hypertensive (Nominal)

• Diabetes: whether or not the patient had diabetes (Nominal) Medical(current)

• Tot Chol: total cholesterol level (Continuous)

• Sys BP: systolic blood pressure (Continuous)

• Dia BP: diastolic blood pressure (Continuous)

• BMI: Body Mass Index (Continuous)

• Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)

• Glucose: glucose level (Continuous)

Predict variable (desired target)

• 10-year risk of coronary heart disease CHD(binary: “1”, means “Yes”, “0” means “No”) - DV

PROJECT WORKFLOW:

Data Cleaning Checking for Duplicates – None found Handling NaN values – 510 NaN values which is 0.01% of the entire dataset Outlier Treatment Feature Engineering Binary Encoding / One-Hot Encoding Deriving of a new feature i.e., avgBP (replacing diaBP & sysBP) EDA – Feature Analysis Heat Map EDA on Features Handling Imbalance Data Model Training, Testing & Hyper-Parameter Tuning Performance Comparison

DATA CLEANING:

Handling NaN Values:

KNN Imputer – For continuous Simple Imputer – For categorical

Outlier Treatment:

totChol has values > 600 Replacing that with 500

FEATURE ENGINEERING:

Binary Encoding / One-Hot Encoding:

sex & is_smoking has (Male/Female) and (Yes/No) data respectively. Since only two features are to be treated, we simply did binary encoding to represent (Male = 1, Female = 0) & (Yes = 1 & No = 0)

New Feature – avgBP We have diaBP & sysBP in our dataset, which represents diastolic and systolic BP. For a healthy person BP measure is 120/80. Both these are co-related with each other (78%). avgBP = (sysBP+diaBP)/2

EDA:

EDA on Features – Age & Smoking: Risk is High in age group of (42 to 45),(56 to 58) and age above 62 despite they are smoking or not.

EDA on Features – CigsperDay, Sex & Risk: There is no Exact Inference to say that - less the cigarettes consumption means less heart disease and vice versa. But Male, more than Female are in the high risk of Heart disease, since the proportion of male smokers v/s female are high and on a reality smokers will be having high risk of getting heart disease.

EDA on Features – Diabetic, Sex & Risk: Non Diabetic – Less risk of heart disease. Diabetic – High risk of heart disease

Handling Imbalance Data:

Common Methods to Handle Imbalance Data

Under sampling the majority class Over sampling the minority class SMOTE Synthetic Minority Over Sampling Technique Reduces overfitting during oversampling Synthetic Sampling is used. Evaluation Metrics: 1. Recall 2. F1 Score 3. ROC Curve

DATA MODELLING AND TRAINING:

We shall study the following training models:
1.Logistic Regression 2.K Nearest Neighbour 3.Decision Tree 4.SVM


CONCLUSION:
Among all the Classifiers used here, K Nearest Neighbour classifier has the best performance with highest RECALL and F1 SCORE of 89%.
