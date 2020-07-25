
Model selection is the process of selecting one final machine learning model from among a collection of candidate machine learning models for a training dataset.

Model selection is a process that can be applied both across different types of models (e.g. logistic regression, SVM, KNN, etc.) and across models of the same type configured with different model hyperparameters (e.g. different kernels in an SVM).
![Technical solution design](../img/TSD-5.png)



|Step  |Exception |Mitigation|
--------|----------|----|
Wrong parameters passed to the methods|Handle Internally|Code should never give a wrong input|
       
<h2>8.   Model Tuning and Optimization**</h2>

## Divide into train and test

The data should have been divided into train and validation set before this.
Methods for hyper tuning all kinds of models.

**Regression:**
* Linear Regression
* Polinomial Regression


**Model selection criteria:**
1. MSE 
1. RMSE 
1. R squared
1. adjusted R squared

**Classification:**
* Logistic Regression
* Decision Tree
* Random Forest
* XG Boost
* Support Vector Classifier
* KNN Classifier
* Naïve Baye’s

**Model selection criteria:**
1. Accuracy
1. AUC
1. Precision
1. Recall
1. F Beta

**Clustering:**
* K-Means
* Hierarchial
* DBSCAN




![Technical solution design](../img/TSD-6.png)

![Technical solution design](../img/TSD-7.png)

Class Name |ModelTuner    | |
----|---|---|  
|Method Name    |get_tuned_knn_model||    
| |Method Description  |This method will be used to get the hypertuned KNN Model
| |Input parameter  names  |self,data
| |Input Parameter Description |Data: the training data Hyperparameters to tune   
| |ouptput|    A hyper parameter tuned model object
| |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message



Exceptions |Scenarios| Module Wise|
-----|-----|----|
Step   |Exception |Mitigation
| | |
      


