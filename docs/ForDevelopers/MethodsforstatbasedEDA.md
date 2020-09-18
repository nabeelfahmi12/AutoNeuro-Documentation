

## Technical solution 
![Technical solution design](../img/TSD-2.png)

## OLS
 Ordinary least squares
The OLS method corresponds to minimizing the sum of square differences between the observed and predicted values.

### OLS_summary
Method Name    |OLS_summary|   |
------------ | ------------- | -----|
| | Method Description |This method will be used to display the OLS summary of the given model.
 | |Input parameter  names |self,dataframe,target
 | |Input Parameter Description|    dataframe: the input dataframe with numeric columns. 
 | |                           |    target : target column 
 | |ouptput    |OLS summary of the model 
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 

## VIF

The variance inflation factor (VIF) is the quotient of the variance in a model with multiple terms by the variance of a model with one term alone. It quantifies the severity of multicollinearity in an ordinary least squares regression analysis.

**Correlation**:
Correlation is a statistical technique that can show whether and how strongly pairs of variables are related

### calculate_vif
Method Name    |calculate_vif|   |
------------ | ------------- | -----|
| | Method Description |This method will be used to calculate the vif scores for the cleaned data.
 | |Input parameter  names |self,dataframe 
 | |Input Parameter Description|    data: the input dataframe with numeric columns. 
 | |ouptput    |VIF values for each of the columns. 
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 


## Silhouette Coefficient
Silhouette Coefficient or silhouette score is a metric used to calculate the goodness of a clustering technique. Its value ranges from -1 to 1.
1: Means clusters are well apart from each other and clearly distinguished.
0: Means clusters are indifferent, or we can say that the distance between clusters is not significant.
-1: Means clusters are assigned in the wrong way.

 
## Exceptions Scenarios 

Step   |Exception |Mitigation|
-----|-----|------|
Column has mixed values(Integer & number)  |Give proper error message |Ask the user to correct the data.
Not all values are numbers |   Handle Internally  |Convert categorical to numerical values

## Seasonality:
Seasonality is a characteristic of a time series in which the data experiences regular and predictable changes that recur every calendar year. Any predictable fluctuation or pattern that recurs or repeats over a one-year period is said to be seasonal.

## Stationary Data:
A common assumption in many time series techniques is that the data are stationary. A stationary process has the property that the mean, variance and autocorrelation structure do not change over time

