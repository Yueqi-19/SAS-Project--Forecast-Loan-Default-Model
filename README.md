# SAS-Project--Forecast-Loan-Default-Model
## 1.Executive Summary
The bank loan status data set obtained from Kaggle. We use 100,000 observations and 19 variables, including 2 binary variables, 8 nominal variables, and 11 continuous variables. We use data detection, establishing a linear regression model ,decision tree model and logistic regression model on the existing basic customer information and related materials, and conduct comparative analysis to find the best model. According to the model, the customer's credit risk situation is analyzed and scored, and the best credit score to distinguish good customers from bad customers is obtained, so that credit card companies can effectively deal with a large number of credit card applicants, quickly accept Judgment of rejection, and the initial credit limit given. For customers who borrow from a bank, we can use the model to distinguish the credit rating of the customer and help the bank determine whether it should borrow from the customer. Through analysis, we found that most customers are short-term loans, mainly liquidity.
## 2.Project Motivation/ Background
The business question  for our project is whether the customers’ loan request will be approved. Based on the information of this loan customer group through this dataset, we can establish a logistic regression, a linear regression, or Decision Tree model of default customers, then we can train these three models and score it. For banks, who loan to customers, this quantitative model can be constructed to differentiate customers' credit ratings and help the bank to make a decision of whether we should loan to this customer. After knowing the default probability of each account, we can also estimate the proportion of bad debts and address some business problems in the future.
## 3.Data Description
The bank loan status dataset which was obtained from Kaggle.com. The target variable Loan Status is a binary variable. And it is expressed as Full paid normal: 0, charged off overdue: 1. The goal of the target variable Loan Status in the multiple linear regression is to predict which classification the target variable ultimately belongs to : 0 or 1. In this case, we will use 0.5 (50%) as a critical value in the prediction model, which means more than 0.5 will suggest that this model is inclined to Full Paid. As for variables, there are 2 binary variables, 8 nominal variables and 11 continuous variables.
- The data set is composed of 100000 observations and 19 variables:

![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.20.18.png)
## 4.Data Analysis
The histogram shows that the company's loan overdue situation is more serious, reaching 27.6%, and the vast majority of customers' working years are customers who have worked for more than 10 years.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.24.44.png)
The status of Home Ownership can also be seen that the customers are mainly renting and loan customers, and debt repayment accounts for the vast majority of loan purposes, which shows that the company's asset risk is greater, which can also be explained from the one hand the reason.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.25.09.png)
In the case of Bankruptcies and Tax Liens, we can see that the vast majority of customers have relatively good credit records, and very few customers have historically bad credit records, so we can also judge that most customers are actually the main liquidity risk , Less vicious fraud clients.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.25.30.png)
Through the pie chart, it is found that nearly 72% of the company's loan terms are short-term loans.This can explain the problem of high proportion of loan repayment in customer loan purposes from this perspective. Customer loans mainly use short-term debt repayment and provide liquidity as the Lord.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.25.46.png)
## 5.Prediction Models and Results
In order to verify the accuracy of the predicted data, three softwares are used to obtain the prediction results：1)SAS EM, 2)BASE SAS,3)PYTHON. In order to get a better prediction rate, in the latter two software BASE SAS,Python, we would compare the difference of the prediction score in the data set.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.26.09.png)
### 5.1 Prediction Models 
#### 5.1.1 Algorithm comparison
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.27.51.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.28.11.png)

Using the above different mining techniques to develop models, through comparative analysis, established a Logistic regression credit score model.
#### 5.1.2 Predict Steps
First use python to clean the data, remove some missing values. 
Second,import the cleaned data to the  ‘import file ’node of SAS EM.
Third ,we would use a cross-validation method in SAS EM software,the reason is that Cross-validation can "fully utilize" limited data to find suitable model parameters and prevent overfitting .
So the sample is divided into three randomly separate parts, which training set is 70%, the validation set  is 20%, and the test set is 10%. 
The training set is used to estimate the model, the validation set is used to determine the best model,select the model with the smallest average error rate ,and the test set is used to evaluate the performance of the best model(the accuracy rate of the best model).
### 5.2 Results
#### 5.2.1 SAS EM 
In the data set split, the 70% is training and the 20% is validation, use these two subsets to determine the lowest average square error on the three algorithms and choose the best.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.26.32.png)
- 1）The findings of the linear regression are shown below:
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.28.53.png)
From above result, we can see that Annual_ income ,Credit_Score,Current_Loan_Amount,
Monthly_Dept,home_Home_Mortgage,home_Own_Home,term_Long_Term are significant to our target variable churn, since they are associated with very small P values.
- 2）The findings of the decision tree are shown below:
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.02.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.10.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.16.png)
It can be seen from the output graph of the model that when a decision tree with 17 leaf nodes is generated, the misclassification rate of the training set is 21.8%, and the misclassification rate of the validation set is 21.6%. In the training set, 46,740 of "good customers"(Full paid normal: 0) have 45,740 correctly classified, and 17,608 of "bad customers"(charged off overdue: 1) have 4,121 correctly classified.
- 3）Since  the target variable Loan_stauts is binary, a logistic regression was run in SAS EM using stepwise method:
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.22.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.27.png)
It can be seen from the above training set graph that the overall model accuracy rate is 1-0.21 = 79%, and the model predicts 98.98% of good customers(Full paid normal: 0) as good customers and 1% of good customers as bad customers. 76% of bad customers(charged off overdue: 1) are predicted to be good customers, and the remaining 23% of bad customers are predicted to be bad customers.
