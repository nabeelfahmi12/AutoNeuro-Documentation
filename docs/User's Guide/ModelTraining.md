# **_Model Training_**

AutoNeuro will train the models with different hyper parameters and generate report for the best model. 
If the data is trained successfully then you will be able to see reports.

##Training the data

- select problem type from **Choose a problem type** dropdown (Regression/Classification)

- select unwanted columns to be dropped from **Drop Unwanted Columns** dropdown (all the columns from your dataset will be listed here)

- select the target Column (dependent column which you want to predict) from **Select Target Column** dropdown.(all the columns from your dataset will be listed here)

- enter the **Symbol to be replaced** to replace the null values in the dataset.

- enter the **Threshold for null values** (ffor the columns with null values)


![Select Problem](../img/6.png)

Once the model is trained , the reports will be displayed as given below:

##Reports

###XGBoost Model
 
![xgboost1](../img/xgboost_report1.png)

![xgboost2](../img/xgboost_report2.png)

###Random Forest Model

![rfboost1](../img/rf_report1.png)

![rfboost2](../img/rf_report2.png)

###Column Usage

![column_usage](../img/column_usage_report.png)
