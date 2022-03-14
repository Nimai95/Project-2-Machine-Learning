# PROJECT 2: APPLICATION OF MACHINE LEARNING IN PREDICTING STOCK DIRECTION
 

#### Team members: Amandeep Kaur, Hanna Ho, Nedal M., Nimai Desai, Ronald 

## Project Theme

Which machine learning model rendered the best results for determining stock direction?  

## Research Question

Predicting the direction of the stock has been always a strong interest of every trader because once we anticipate a trend we can make a profit via "buy low and sell high". However it's not an easy task. Stock market is subject to quick changes, random fluctuation, non linear, and non symentric mainly because participants are irrational, emotional, and implusive in their trading behavior . However complex the market is, there is a belief that given mass trading behaviors repetitive patterns exist, which is a foundation of technical analysis.

By using supervised machine learning models with the inputs as various of technical analysis indicators, we examine: 

1. Which is the best algo. model to determine stock trend?  
2. Which is the best model?
3. which time frame and ticker the model show the best result by testing various of prediction time frame and stocks of different stocks?  

## Setup

Steps

![alt_text](/Consol/Images/steps.jpeg)

Tested tickers : AAPL, MSFT, SPY, TSLA
Time Frame: 3 days, 5 days, 7 days

## Implementation

### 1. Get data

We used yFinance for daily trading data.  

### 2. Clean, prepare and manipulate data

We used Pandas and FinTA library to calculate the technical indicators.

### 3. Train Models

We chose to run the supervised machine learning models for classification as follows:

1. Logistic Regression
2. Gradient Boosting Tree 
3. Support Vector Machines
4. LSTM using PCA
5. Random Forest Classifer

For time series data, we split train and test by len function to avoid data leakage.
(please refer to folder file named "Supervised ML Models")

### 4. Testing Data and Result

4.1. Logistic Regression and Gradient boosting Classifier 

![](/Consol/Images/LR_and_GBC_test.png "ROC Curve for Logistic Regression")

![ROC Curve for Logistic Regression](Images/logistic_acc.png "Accuracy Result" )

---
4.2 Support Vector Machine

Key lesson learnt

---

4.3 LSTM using PCA

ROC for testing data
![](/Consol/Images/LSTM_test.png "ROC Curve for LSTM using PCA")

![ROC Curve ](Images/lstm_model.png "Accuracy Result")

---

4.4 Random Forest Classifer

![](/Consol/Images/ROC_test.png "ROC Curve for Radom Forest Classifier")

![](Images/RFC_model.png "Accuracy Result")

---

### 5. Improve - Random Forest Classifier Model

Method 1. Hyper Tunning using Gridsearch and Grid Search...[Ronald]


Method 2. Improve Data Quality

Continously try different indicators and choose the best features that matter, we could improve the model from 0.43 t0 0.55 

### 6. Deploying best model

We have used the best model with the best result of accuracy and deploy for 4 stocks include AAPL, MIC.., SPY, TSLA

![best_model](Images/table_result.png)

Please refer to notebooks named "final_model_production and Result" for more details.

## Findings and Lessons

### Findings

* Our best model is the Random Forest Classifier using GridSearchCV as a hyperparameter tunning tool 
* Though it is the best among all the models we have tested, it shows a modest result with around 0.5 accuracy
* We aimed at optimizing model to achieve higher precision and recall rate for uptrend, and the model shows good result to predict APPL in 3 days and TESLA in 5 days
* The results of the model are different for different stocks and time frames

### Lessons

* We have experienced both overfitting and underfitting and that understand that we need to find out the sweet pot for the best fit
* Imperfections when data grows when we split 70/30 and 80/20 the result significantly changes
* It's hard to find out one model fit all, and the challenge is to keep accuracy score stable


***
New library used: GridSearch.. [Ronald]

 



