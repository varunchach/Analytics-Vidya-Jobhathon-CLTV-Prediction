# Analytics-Vidya-Jobhathon-CLTV-Prediction

It was a Jobhackathon in which we were asked to predict Customer life time value for identifying most potential customer for an insurance company.

### Problem Statement

VahanBima is one of the leading insurance companies in India. It provides motor vehicle insurances at best prices with 24/7 claim settlement.  It offers different types of policies for  both personal and commercial vehicles. It has established its brand across different regions in India. 

Around 90% of the businesses today use personalized services. The company wants to launch different personalized experience programs for customers of VahanBima. The personalized experience can be dedicated resources for claim settlement, different kinds of services at doorstep, etc. Inorder to do so, they would like to segment the customers into different tiers based on their customer lifetime value (CLTV).

Inorder to do it, they would like to predict the customer lifetime value based on the activity and interaction of the customer with the platform. So, as a part of this challenge, your task at hand is to build a high performance and interpretable machine learning model to predict the CLTV based on the user and policy data.


### About the Dataset

We are provided with the sample dataset of the company holding the information of customers and policy such as highest qualification of the user, total income earned by a customer in a year, employee status,  policy opted by the user, type of policy and so on and the target variable indicating the total customer lifetime value.

Initial Data Snapshot

![image](https://user-images.githubusercontent.com/58731031/213914252-9441c5b3-bf3b-4f45-89aa-eec2d083f274.png)


Distribution of response variable CLTV :-

![image](https://user-images.githubusercontent.com/58731031/213914194-42ae4c2f-2813-4852-9605-48a82f0a1cf5.png)

CLTV refers to customer's life time value which is annoted by VahanBima organization. More the value , better is the customer.

We see data is right skewed (positively skewed) with most density concentrated between [24828,103440].



### Exploratory Data Analysis :-

Please refer EDA.html for detailed Exploratory analysis report.

Example :-
1. Income variable

![image](https://user-images.githubusercontent.com/58731031/213914379-69a15755-13d5-4f5c-b377-d85218a8cd90.png)


### Conclusions

If we compare the means for different categories then we can see that for variables :-
1. Gender wise avg cltv doesnt changes much.
2. Area wise cltv is changing , in Urban area avg cltv is higher than rural area i.e company is rating urban area insured more than rural.
3. Qualification wise avg cltv is same across high school & Bachelor but lower avg cltv is observed if you have any other qualification.
4. For income story is interesting , i.e we are able to see a monotonic increase in avg cltv as income range decreases i.e higher income >10L have least avg CLTV & it increases and maximum if your income is less than <2L
5. Number of Policies :- Avg CLTV is much higher for users with more than 1 policies
6. Avg CLTV is same for policy name A & C but significant lower in case of policy B
7. For type of policy Silver , avg cltv is observed to be lower than Gold & Platinum policy.
8. Avg CLTV is lesser for unmarried users than married users.
9. For users who havent claimed the insurance have less avg cltv than that of those who havent claimed.


### Data Cleaning 
1. Identified the ordinal variables and encoded them in order of avg CLTV they have in each categories.
2. Capped & Floored outliers for numerical feature claim amount


### Modelling

![image](https://user-images.githubusercontent.com/58731031/213914516-b68a48c0-621e-4837-86dc-319745022597.png)


Used automl package and tried out 3 different algorithms , LightGBM, XGBoost & Catboost. 
LightGBM gave me best score of 15.86% (coefficient of determination)(rank 70).
Its a pretty low value but the fact that there are no reasonable associations between cltv and the data we have this still holds a reasonable good model.



