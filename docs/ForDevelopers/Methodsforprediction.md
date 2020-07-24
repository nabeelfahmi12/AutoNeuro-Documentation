# Methods for prediction

<h2>Data Profiling</h2>

**Data profiling** is the process of reviewing source data, understanding structure, content and interrelationships, and identifying potential for data projects.   

![Data Profiling](img/data_profiling.png)


After reading the data, automatically the following details should be shown:
a) The number of rows
b) The number of columns
c) Number of missing values per column and their percentage
d) Total missing values and it’s percentage
e) Number of categorical columns and their list
f) Number of numerical columns and their list
g) Number of duplicate rows
h) Number of columns with zero standard deviation and their list
i) Size occupied in RAM

Method Definition

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

<h2>Stats based EDA:</h2>


**MVP**: Minimum Viable Product
Building a minimum viable product is an opportunity to quickly test an idea and see if it works. It doesn't need to be the best solution, it should just be a usable solution. If it is, then we can move on to the development stage and make it work well.
 
**OLS**: Ordinary least squares
The OLS method corresponds to minimizing the sum of square differences between the observed and predicted values.

**VIF**: 
The variance inflation factor (VIF) is the quotient of the variance in a model with multiple terms by the variance of a model with one term alone. It quantifies the severity of multicollinearity in an ordinary least squares regression analysis.
Correlation:
Correlation is a statistical technique that can show whether and how strongly pairs of variables are related

**Phase1:**

![Flow chart](img/stats_flowchart.jpg)

**Anova test:**
An ANOVA test is a way to find out if survey or experiment results are significant. In other words, they help you to figure out if you need to reject the null hypothesis or accept the alternate hypothesis. Basically, you're testing groups to see if there's a difference between them.

**Chi-square test** 
Pearson's chi-square test is used to determine whether there is a statistically significant difference between the expected frequencies and the observed frequencies in one or more categories of a contingency table.

**Z-test** 
A z-test is a statistical test to determine whether two population means are different when the variances are known and the sample size is large. It can be used to test hypotheses in which the z-test follows a normal distribution. A z-statistic, or z-score, is a number representing the result from the z-test.

**T test** 
The t test is one type of inferential statistics. It is used to determine whether there is a significant difference between the means of two groups. With all inferential statistics, we assume the dependent variable fits a normal distribution

**Weight of evidence** 
The weight of evidence tells the predictive power of an independent variable in relation to the dependent variable.

**F-test** 
An F-test is any statistical test in which the test statistic has an F-distribution under the null hypothesis. It is most often used when comparing statistical models that have been fitted to a data set, in order to identify the model that best fits the population from which the data were sampled.
         

Technical solution design
![Technical solution design](/docs/img/TSD-2.png)
 
**Exceptions Scenarios Module Wise**

Step   |Exception |Mitigation|
-----|-----|------|
Column has mixed values(Integer & number)  |Give proper error message |Ask the user to correct the data.
Not all values are numbers |   Handle Internally  |Convert categorical to numerical values

**Phase 2:**

**Seasonality:**
Seasonality is a characteristic of a time series in which the data experiences regular and predictable changes that recur every calendar year. Any predictable fluctuation or pattern that recurs or repeats over a one-year period is said to be seasonal.

**Stationary Data:**
A common assumption in many time series techniques is that the data are stationary. A stationary process has the property that the mean, variance and autocorrelation structure do not change over time
