

![Technical Design](../img/TSD-3.png)

##Transformations
### Null value handling
### Categorical to numerical
### Imbalanced data set handling
### Handling columns with std deviation zero or below a threshold
### Normalisation
### PCA


## Data Preprocessor

Class Name |DataPreprocessor| |
----|-------|--------|    
|Method Name    |impute_missing_values ||
| |Method Description  |This method will be used to read data from a csv file or a flat file. 
| |Input parameter  names| self,file_name, header,names, use_cols, separator. Input Parameter Description file_name: name of the file to be read. header: Row number(s) to be used as column names. names : array-like, optional. List of column names to use. If file contains no header row, then you should explicitly pass ``header=None``. Use_cols:  To load a subset of columns. Separator: Delimiter to use.
| |output| A pandas Dataframe
| |On Exception|   Write the exception in the log file. Raise an exception with the appropriate error message

## Exceptions Scenarios Module Wise

Step|  Exception| Mitigation|
---|---|----|
Wrong parameters passed to the methods |   Handle Internally  |Code should never give a wrong input


