Once the pandas dataframe is given, using data visualization methods we will get corresponding data in the form of graph.


![](../img/TSD-3.png)

## Correlation Heatmaps

![Sample heatmap](../img/heatmap.png)


## Check for balance/imbalance

![](../img/balanced.jpg)



## Data Visualisation 
Class Name |DataVisualization ||
------|---------|----| 
Method Name    |read_data_from_csv    |
| |Method Description| This method will be used to read data from a csv file or a flat file
| |Input parameter  names| self,file_name, header,names, use_cols, separator
| |Input Parameter Description|    file_name: name of the file to be read header: Row number(s) to be used as column names names : array-like, optional List of column names to use. If file contains no header row, then you should explicitly pass ``header=None``. Use_cols:  To load a subset of columns Separator: Delimiter to use
| |    output |A pandas Dataframe
| |On Exception|   Write the exception in the log file. Raise an exception with the appropriate error message


## Exceptions Scenarios Module Wise

Step   |Exception|    Mitigation|
|------|------|---------|
Wrong input to the methods |   Handle Internally| Code should never give a wrong input


