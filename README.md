# Cardiovascular-Risk-Prediction
Heart disease is the major cause of morbidity and mortality globally: it accounts for more deaths annually than any other cause. According to the WHO, an estimated 17.9 million people died from heart disease in 2016, representing 31% of all global deaths. Over three quarters of these deaths took place in low- and middle-income countries. Of all heart diseases, coronary heart disease (aka heart attack) is by far the most common and the most fatal.<br/>
The silver lining is that heart attacks are highly preventable and simple lifestyle modifications (such as reducing alcohol and tobacco use; eating healthily and exercising) coupled with early treatment greatly improves its prognosis. It is, however, difficult to identify high risk patients because of the multi-factorial nature of several contributory risk factors such as diabetes, high blood pressure, high cholesterol, et cetera. This is where machine learning and data analysis comes to the rescue.
In this document we will be giving a walk through on the development of a classification model for predicting whether a patient has 10-year risk of developing coronary heart disease (CHD) using different Machine Learning techniques on the Framingham dataset .

**Table of content**<br/>
>Introduction to the Subject of Cardiovascular Risk Prediction.<br/>
>Problem Statement.<br/>
>Data Overview.<br/>
>Exploratory Data Analysis.<br/>
>Machine Learning Models<br/>
>Conclusions.<br/>
>Future Work.<br/>
>Reference<br/> 

**Introduction**<br/>
The Framingham Heart Study is a long-term, ongoing cardiovascular cohort study of residents of the city of Framingham, Massachusetts.<br/>
The study began in 1948 with 5,209 adult subjects from Framingham, and is now on its third generation of participants.<br/>
Prior to the study almost nothing was known about the epidemiology of hypertensive or arteriosclerotic cardiovascular disease.<br/>
Much of the now-common knowledge concerning heart disease, such as the effects of diet, exercise, and common medications such as aspirin, is based on this longitudinal study.<br/>
It is a project of the National Heart, Lung, and Blood Institute, in collaboration with (since 1971) Boston University. Various health professionals from the hospitals and universities of Greater Boston staff the project.<br/>

**Problem Statement**<br/>
The dataset is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts.<br/> 
The classification goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD).<br/> 
The dataset provides the patients’ information. It includes over 3,000 records and 17
 attributes.<br/>
 
**Data Overview**<br/>
Observations:3390<br/>
Features:17<br/>

**EDA**<br/>
1.Data is highly imbalanced<br/>
2.Slightly more males are suffering from CHD than females.<br/>
3.The percentage of people who have CHD is almost equal between smokers and non smokers.<br/>
4.The percentage of people who have CHD is higher among the diabetic, and those with prevalent hypertension as compared to those who don’t have similar morbidities.<br/>
5.A larger percentage of the people who have CHD are on blood pressure medication.<br/>
6.Features that are highly correlated:<br/>
Systolic and diastolic blood pressures<br/>
Cigarette smoking and the number of cigarettes smoked per day<br/>

**Data Cleaning**<br/>
We used mean, median and KNN imputer to fill the null values.<br/>

**Data Balancing using SMOTE model**<br/>
Shape:<br/>
Original dataset shape : 3390<br/> 
Resampled dataset shape : 5758<br/>

Number of values for class 1&0:<br/>
Before : {1.0: 511, 0.0: 2879}<br/>
After :  {1.0: 2879, 0.0: 2879}<br/>

**Machine Learning Models**<br/>
SVC<br/>
K-NN<br/>
Decision Tree<br/>
Random Forest<br/>
Bagging Classifier<br/>
AdaBoost Classifier<br/>
XGB Classifier<br/>
AdaBoost Classifier with SVC<br/>
CatBoost Classifier<br/>
Stacking Classifier<br/>

**Conclusion**<br/>
After training and testing the data on multiple models ranging from simple to ensembled approaches, we have the result for different scores like ROC-AUC, Precision, Recall, F1, Accuracy and Cohen's Kappa score at a single place. On comparing the Cohen's kappa score we can observe that Stacking has the best value followed by Support Vector Classifier. Also if we go back to our problem statement, our goal is to predict the risk of heart disease. In this type of problem our priority should be to reduce the number of False Negatives or find maximum Recall score. If we misclassify someone as having no risk to heart disease, it can be highly detrimental, it can lead to loss of life. Stacking gives us an excellent Recall and at the same time doesn't compromise on Precision. If we require a model with more strict Recall values we can opt for KNN.<br/>

**Scope of Improvement:**<br/>
For future work we need to look for more optimal methods to handle the data imbalance. We can also go for hyper parameter tuning with more range of values and more number of parameters. More sophisticated approach like Neural nets can be used. With stacking we can use more optimal version of the base models and we can check with more combinations of base models.







