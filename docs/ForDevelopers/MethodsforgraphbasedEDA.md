Once the pandas dataframe is given, using data visualization methods we will get corresponding data in the form of graph.


![](../img/TSD-3.png)

## Correlation Heatmaps

![Sample heatmap](../img/heatmap.png)

 
Method Name    |correlation_heatmap|   |
------------ | ------------- | -----|
| | Method Description |This method will be used to generate interactive heatmap plot to show the pairwise correlation of input variables
 | |Input parameter  names |self,dataframe
 | |Input Parameter Description|   data: the input dataframe with target column 
 | |ouptput    |son file with correlation information that can be used by plotly to generate interactive plots.
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 

## Check for balance/imbalance

![](../img/balanced.jpg)

balance_imbalance_check

Method Name    |balance_imbalance_check|   |
------------ | ------------- | -----|
| | Method Description | This method will be used to plot the balance/imbalance datasets using barplot/countplot
 | |Input parameter  |self, dataframe, target column 
 | |Input Parameter Description|   data: the input dataframe with target column.
 | |                            |   target: target column name.
 | |ouptput    |plot of target variable value count.
 | |On Exception|  Write the exception in the log file. Raise an exception with the appropriate error message 

