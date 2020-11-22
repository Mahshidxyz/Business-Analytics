# Business-Analytics

## Project 1) Survival analysis for customer churn

In this project I am building a survival model to predict customer churn for an internet & phone service company. The idea is to predict churn before it happens and try to prevent it by targeting at-risk customers for marketing campaigns offering a discount or a new package. Survival analysis can create an estimate of the risk of attrition over time which makes it a perfect choice for this project.

The dataset includes information about:

* Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
* Customer account information – how long they have been a customer, contract, payment method, paperless billing, monthly charges, and total charges
* Demographic info about customers – gender, senior citizen or not, and if they have partners and dependents
* Customers who left within the last month – Churn.

**Why use survival analysis instead of linear or logistic regression?**

With linear regression (dependent variable = time of churn) we cannot use the data from the users who have not churned already (censored data). However, survival analysis uses that data and that makes it more powerful. With logistic regression we either assume tenure does not have an effect on the churn probability (not a feature) or we assume after reaching some tenure, tenure will no longer have an effect on churn and customers who have been around long enough never tend to leave (sigmoid curve). However, survival analysis does not have that limitation and does not assume a particular shape for risk as a function of time.

**Summary of results:**

In the first step, I have provided Kaplan Meier curves which allow for comparing different cohorts of customers in terms of survival probability. Next, I built a Cox proportional hazard model for customers with internet and phone services (4835 customers). I have excluded a few features (monthly and total charges) from the model due to high multicollinearity with service types. My model achieved a concordance score of 0.85 and showed that 13 features were significant (alpha = 0.05). For the next step, I plan to use regularization and cross validation to build a model with Lasso regularization for automatic feature selection. I will also have to work on checking the assumptions of the model.

## Project 2) Customer Segmentation for a Credit Card Company

This project is about customer segmentation for a credit card company. One way to reduce the costs associated with credit card signup incentives and offering successful marketing campaigns is to offer credit cards with carefully targeted benefits that will attract new cardholders. The goal of customer segmentation here is to get an idea of popular benefits to associate with each new card offering. To study the various kinds of users who use the company’s products we are looking at the user data over a 6 month period. The data consists of 8950 rows (one for each cardholder) organized in columns with descriptive headers. The data has been provided by J. Patrick Weller. Currently this data is not publicly available. 


**Summary of results:**

I used Kmeans and Hierarchical Clustering to segment customers. Both methods resulted in comparable outcomes. I identified 4 clusters with the following descriptions:

* Cluster 1: Low balance, infrequent users. Mostly use the card for one off purchases and cash advances. Rarely pay the balance in full. Low credit limit.

* Cluster 2: Low balance, frequent users. Don't spend too much money with this card but use it frequently for small purchases. Rarely do cash advance. Low credit limit. 

* Cluster 3: High balance driven by frequent cash advance not purchases. Prefer to pay for everything in cash! Rarely pay the balance in full. High credit limit. 

* Cluster 4: High balance driven by frequent purchases (both one-off purchases and installments), not so much by cash advances. Use credit to pay for everything!. High credit limit. 

**Reommendation:**

I came up with some simple offer componenets that can be attractive to different customer segments. Tailoring these offers requires a lot of knowledge about the costs associated with each type of offer. 

* Offer low APR for customers who rarely pay their balance in full (cluster # 1 and # 3)
* Offer low cash advance fee for customers who frequently take cash advances (cluster # 3)
* Offer sign up bonuses (e.g. $200 bonus if you spend $500 in the first 3 months) for customers with low balance, customers who use their cards frequently but for small purchases or do not use it often (cluster # 1 and # 2)
* Offer higher cash back for high spenders and frequent users (stay competitive in the credit card space) to retain customers (cluster # 1 and # 4)
