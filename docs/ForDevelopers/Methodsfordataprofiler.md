# **_Data profiling_**

**Data profiling** is the process of reviewing source data, understanding structure, content and interrelationships.   

![Data Profiling](../img/data_profiling.png)

Method Definition

## Data Profiler

Class Name |DataProfiler||
---------|--------|-------|
Method Name    |get_data_profile  |
||Method Description|  This method will be used to give various insighst about data.
| |Input parameter  names| self, dataframe
| |Input Parameter Description |dataframe: the inpt data just loaded from source 
| |ouptput |a)    The number of rows 
| | |b)    The number of columns
| | |c)    Number of missing values per column and their percentage
| | |d)    Total missing values and it’s percentage
| | |e)    Number of categorical columns and their list
| | |f)    Number of numerical columns and their list
| | |g)    Number of duplicate rows
| | |h)    Number of columns with zero standard deviation and their list
| | |i)    Size occupied in RAM
| |On Exception    |Write the exception in the log file. Raise an exception with the appropriate error message
