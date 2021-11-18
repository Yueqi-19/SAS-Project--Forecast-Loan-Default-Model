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
##### 5.2.1.1Which one is the best model
In three models: the smallest average squared error rate is 0.15347=15%, the best model is the Logistic Regression Model.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.34.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.41.png)
In addition ,the ROC curve also showed the performance of the model.
From the above plot,better performance can be reflected by the curve near the upper left corner.
So on the other hand, near the upper left corner is the logistic regression model(red line), from which we can know that the logistic regression model is the best model in prediction.
##### 5.2.1.2 Accuracy Measures in SAS EM:
In test set:Use the logistic regression model on the training set (90%)to predict the last 10% test 
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.47.png)

The accuracy rate of test set in logistic regression model-Model Comparison(2):
Note:Loan status (0) is expressed as Full paid, Loan status (1) is expressed as charged off, because the target variable is loan status, so the accuracy rate is clearly expressed here as the correct rate of predicting the passing loan.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.29.55.png)
Accuracy rate=(TP+TN)/(TP+FN+FP+TN)=1-Misclassification Rate=1-21%=79%
The logistic regression model predicted 79% of correct results,this means that the loan classifier performs very well in identifying fraudulent customers.
#### 5.2.2 Base SAS(Predict Score1)
Note:
P_Loan_Status1    Predicted: Loan_Status=1

P_Loan_Status0    Predicted: Loan_Status=0


To get the Loan Status ’ predicted probability, use the optimized SAS code from the score node,save the SAS optimized code in the same file path and run it in Base SAS.
The predicted score of Loan Status(0) and  Loan Status(1):(pick up 10 observations)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.30.05.png)
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.30.13.png)
When we move to the probability of classification，we notice that the first 10 observations have the same probability in both status 0 and 1. Which means they have 72% of probability to be fully-paid, and 27% to be charged off. which means the customer's credit score is good and the bank can lend to the customer.
#### 5.2.3 Python-(Predict Score2)
To get the Loan Status predicted score:78%
Train the model and give a score, the accuracy rate is 78.88%, and the prediction success rate is high.
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.30.21.png)
## 6.Conclusions
![image](https://github.com/Yueqi-19/SAS-Project--Forecast-Loan-Default-Model/blob/main/SAS%20IMG/%E6%88%AA%E5%B1%8F2021-11-18%20%E4%B8%8A%E5%8D%882.30.28.png)
The reason why we use three softwares to score customers is to verify whether the logistic regression models obtained by these three softwares have too much deviation. As can be seen from the above figure, the deviation is not big，the error is very small, only from 0.1% to 0.7%. The accuracy rate of the model is between 72% -79%. The reason why the BASE SAS software score is the smallest is because we took the average of 10 observations and selected the average model accuracy rate.
To the most important, based on the critical value of 0.5, the value of 70% is greater than 0.5. It can be inferred that the bank can lend to the customer and the customer has good credit.

Our experiences and suggestions:
In this project we learned a lot, applied the knowledge of this class, and learned how to use different software to score credit cards.
Credit scoring is actually the application of scoring technology in credit risk management. The establishment of a credit score is based on the statistical results of a large number of data, which has very high accuracy and reliability. The application credit score is used exclusively for the credit evaluation of new applicants. It can quickly and effectively identify and divide the advantages and disadvantages of customers through the relevant identity information filled out by the applicant, prevent customers with bad credit from applying for credit cards, improve the credit level of cardholders, realize the precaution of credit card business risks, and help banks establish The first credit risk safety net. 
However, the credit card application scoring model designed in this paper cannot replace the credit scoring system. Only with the support of the credit scoring system will it be possible to obtain rich and complete customer information. With the development of the credit card business and the credit status of the entire society, the key factors that determine customer credit will also continue to change. Therefore, data mining methods can Flexible use. By discovering the rules in the customer information, finding out the elements that the bank needs to focus on, it plays a directional guiding role for the verification and verification of the bank. In this way, both efficiency and efficiency are guaranteed. In addition, some new models discovered through data mining can further adjust the customer credit scoring system, thereby playing an important role in improving the credit scoring system in the future. The credit card scoring table model constructed in this paper uses a variety of data modeling and mining techniques, which can effectively, objectively, accurately and consistently make effective credit evaluations for credit card applicants, which has a certain auxiliary effect on the actual credit card application scoring business. 
Due to the short research time, coupled with the limitations of own knowledge, information, experience, and energy, this credit scoring model still has some limitations and needs to be developed, mainly in the following aspects because this research involves some commercial banks Secretly, the data samples obtained are very limited. Even the data obtained has problems in all aspects of data quality. Many key data have been fuzzified, and at the same time, the missing values ​​are serious, which leads to a decrease in the accuracy of the scoring model. The data obtained in this research is based on the customer data that has been scored by bank credit staff, but the credit staff itself has certain subjective factors, and there are certain errors and inconsistencies in the classification of customers, so this model will inevitably produce this aspect error. 
Since the United States has a very sound personal credit system, the data related to personal credit is distributed among various functional departments and related units, and between various departments and banks. In this situation, the credit risk assessment of the credit card mainly relies on the data characteristics of the customer, which is used to evaluate the customer's credit status. Banks may still face some credit risks in the process of credit card approval. This credit card scoring model is only a preliminary attempt to use data mining techniques to analyze the customer data of the issuing bank to assist the risk management of the issuing bank. With the development of the American personal credit system, the improvement of the corresponding legal environment, the development of informatization, the realization of information resource sharing, the strengthening of the national personal credit concept and the recognition of credit, data mining technology will become the bank ’s credit risk management, customers An important tool for relationship management, financial product development, marketing decision analysis, and improved banking management.
