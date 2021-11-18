# SAS-Project--Forecast-Loan-Default-Model
## 1.Executive Summary
The bank loan status data set obtained from Kaggle. We use 100,000 observations and 19 variables, including 2 binary variables, 8 nominal variables, and 11 continuous variables. We use data detection, establishing a linear regression model ,decision tree model and logistic regression model on the existing basic customer information and related materials, and conduct comparative analysis to find the best model. According to the model, the customer's credit risk situation is analyzed and scored, and the best credit score to distinguish good customers from bad customers is obtained, so that credit card companies can effectively deal with a large number of credit card applicants, quickly accept Judgment of rejection, and the initial credit limit given. For customers who borrow from a bank, we can use the model to distinguish the credit rating of the customer and help the bank determine whether it should borrow from the customer. Through analysis, we found that most customers are short-term loans, mainly liquidity.
## 2.Project Motivation/ Background
The business question  for our project is whether the customers’ loan request will be approved. Based on the information of this loan customer group through this dataset, we can establish a logistic regression, a linear regression, or Decision Tree model of default customers, then we can train these three models and score it. For banks, who loan to customers, this quantitative model can be constructed to differentiate customers' credit ratings and help the bank to make a decision of whether we should loan to this customer. After knowing the default probability of each account, we can also estimate the proportion of bad debts and address some business problems in the future.
## 3.Data Description
The bank loan status dataset which was obtained from Kaggle.com. The target variable Loan Status is a binary variable. And it is expressed as Full paid normal: 0, charged off overdue: 1. The goal of the target variable Loan Status in the multiple linear regression is to predict which classification the target variable ultimately belongs to : 0 or 1. In this case, we will use 0.5 (50%) as a critical value in the prediction model, which means more than 0.5 will suggest that this model is inclined to Full Paid. As for variables, there are 2 binary variables, 8 nominal variables and 11 continuous variables.
- The data set is composed of 100000 observations and 19 variables:

![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.20.18.png)
