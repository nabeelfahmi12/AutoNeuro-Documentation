

![Technical Design](../img/TSD-4.png)

## Preprocessing 

### **replace_sym_null**

This method will be used to replace the null values with the symbol if entered

### **identify_thresh_cols**
This method will be used to identify the columns with threshold of null values more than the thershold value entered.

###  **remove_columns**
The unwanted columns selected by the user and selected by identify_thresh_cols will be removed.

###  **impute_missing_values**
This method will be used to impute missing values in the dataframe. 

 * ‘median’ : default for continuous variables, replaces missing value(s) with median of the concerned column
 * ‘mean’ : replace missing values with the mean of the concerned column
 * ‘mode’ : default for categorical variables
 * ‘fixed’ : replaces all missing values with a fixed ‘explicitly specified’ value

###  **handle_outliers_IQR**
This method replaces outliers in numerical variables with their median

### **label_encoding**
This method will be used to convert column datatype from categorical  to numerical. 

### **OLS_summary**
This method will be used to display the OLS summary of the given regression model.

### **feature_selection**
This method will return the selected features from the Dataset based on feature importance Calculated by ExtraTreeRegressor and ExtraTreeClassifier with SelectfromModel Method.

### **check_correlation**
This method will be used find correlation of the dataframe

### **calculate_vif**
This method will be used to calculate the vif scores for the cleaned data and outputs the correlation of each column.

### **remove_imbalance**
This method will be used to handle unbalanced datasets(rare classes) through oversampling/ undersampling techniques

### **separate_label_feature**
This method separates the features and a Label Coulmns. It returns two separate Dataframes, one containing features and the other containing Labels .

### **standardize_data**
This method will be used to standardize al the numeric variables. Where mean = 0, std dev = 1.

## Exceptions Scenarios Module Wise

Step|  Exception| Mitigation|
---|---|----|
Wrong parameters passed to the methods |   Handle Internally  |Code should never give a wrong input


