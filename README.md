# Business-Analytics

## Project 1) Survival analysis for customer churn

In this project I am building a survival model to predict customer churn for an internet & phone service company. The idea is to predict churn before it happens and try to prevent it by targeting at-risk customers for marketing campaigns offering a discount or a new package. Survival analysis can create an estimate of the risk of attrition over our time and that is exactly what we are interested in in this project.

The dataset includes information about:

* Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
* Customer account information – how long they have been a customer, contract, payment method, paperless billing, monthly charges, and total charges
* Demographic info about customers – gender, senior citizen or not, and if they have partners and dependents
* Customers who left within the last month – Churn.

**Why use survival analysis instead of linear or logistic regression?**

With linear regression (dependent variable = time of churn) we cannot use the data from the users who have not churned already (censored data). However, survival analysis can use that data. With logistic regression we either assume tenure does not have an effect on the churn probability (not a feature) or we assume after reaching some tenure, tenure will no longer have an effect on churn and customers who have been around long enough never tend to leave (sigmoid curve). However, survival analysis does not assume a particular shape for risk as a function of time.

**Summary of results:**

In the first step, I have provided Kaplan Meier curves which allow for comparing different cohorts of customers in terms of survival probablity. Next, I built a Cox proportional hazard model for cutomers with internet and phone services (4835 customers). I have excluded a few features (monthly and total charges) from the model due to high multicollinearity with service types. My model achieved a concordance score of 0.85 and showed that 13 features were significant (alpha = 0.05). For the next step, I plan to use regularization and cross validation to build a model with Lasso regularization for automatic feature selection. I will also have to work on checking the assumptions of the model.
