

## Preprocessor():
This class shall be used to include all Data Pre-processing techniques to be fed to the Machine Learning Models

###   get_data_profile
```python
    def get_data_profile(self, data):
        self.data_profile = {}
        self.missing_values = {}
        self.missing_val_pct = {}
        self.data_profile['rows'] = data.shape[0]
        self.data_profile['columns'] = data.shape[1]
        self.missing_vals = data.isna().sum()
        for col in data.columns:
            if data[col].isnull().sum() > 0:
                self.missing_values[col] = data[col].isnull().sum()
                self.missing_val_pct[col] = (data[col].isnull().sum() / len(data)) * 100
        self.data_profile['missing_values'] = self.missing_values
        self.data_profile['missing_vals_pct'] = self.missing_val_pct
        self.data_profile['categorical_columns'] = list(data.select_dtypes(exclude=["int64", "float"]))
        self.data_profile['num_categorical_columns'] = len(self.data_profile['categorical_columns'])
        self.data_profile['numerical_columns'] = list(data.select_dtypes(exclude=["object"]))
        self.data_profile['num_numerical_columns'] = len(self.data_profile['numerical_columns'])
        self.data_profile['num_duplicate_rows'] = data.duplicated().sum()
        self.describe = data.describe().T
        self.standard_deviation = self.describe[self.describe['std'] == 0]
        self.standard_deviation = list(self.standard_deviation.index)
        self.data_profile['num_col_with_std_zero'] = len(self.standard_deviation)
        if len(self.standard_deviation) > 0:
            self.data_profile['cols_with_std_zero'] = self.standard_deviation

        self.size = data.size / (1024 * 1024)
        self.data_profile['datasize'] = str(round(self.size, 2)) + " MB"

        return self.data_profile
```
### separatete Label features
This is used to seperate the target and feature as X and Y
``` python
    def separate_label_feature(self, data, label_column_name):
            self.X = data.drop(labels=label_column_name,axis=1)  # drop the columns specified and separate the feature columns
            self.Y = data[label_column_name]  # Filter the Label columns
            return self.X, self.Y
```
### remove_columns
This method removes the given columns from a pandas dataframe.

```python
    def remove_columns(self, data, columns):
        self.data = data
        self.columns = columns
            self.useful_data = self.data.drop(labels=self.columns, axis=1)  # drop the labels specified in the columns
            return self.useful_data
```
###  impute_missing_values
This method will be used to impute missing values in the dataframe
```python
   def impute_missing_values(self, data, mv_flag=None, target=None, strategy='mode', impute_val=None,missing_vals=None):
                dataframe = data

                if mv_flag is True:
                    # Converting missing_vals to Nan Values
                    if missing_vals:
                        dataframe.replace(missing_vals, np.nan, inplace=True)
                    #  Checking for Missing Values in Dependent Variable
                    if dataframe[target].isna().any():
                        dataframe = dataframe[dataframe[target].notna()].copy()  # Selecting the Dataframe With No missing values in Dependent column
                    # Checking for Missing Values in Independent Variables
                    Missing_data_columns = dataframe.columns[
                        dataframe.isna().any()].tolist()  # Finding Columns with the missing data from dataframe
                    if strategy == 'fixed':  # checking if strategy == fixed
                        dataframe.fillna(impute_val,inplace=True)  # Filling the Nan values with the imputed value from user
                    else:
                        for columns in Missing_data_columns:  # Iterating over the columns having Nan Values
                            if dataframe[columns].dtype == 'object':  # Checking for the categorical data
                                mode = dataframe[columns].mode()[0]
                                dataframe[columns].fillna(mode,inplace=True)  # Imputing Nan values with mode of the column
                            else:
                                if strategy == 'median':  # checking if the strategy == median
                                    median = dataframe[columns].median()
                                    dataframe[columns].fillna(median,inplace=True)  # Imputing Nan values with median of the column
                                else:  # The only strategy remains is mean
                                    mean = dataframe[columns].mean()
                                    dataframe[columns].fillna(mean,inplace=True)  # Imputing Nan values with mean of the column

                else:
                    self.logger_object.log(self.file_object, "my_flag found False")
            return dataframe
```
### type_conversion
This method will be used to convert column datatype from numerical to categorical or vice-versa, if possible.
```python
   def type_conversion(self, dataset, cat_to_num=None, num_to_cat=None):
                if cat_to_num is not None:
                    for column in cat_to_num:
                        dataset[column] = pd.to_numeric(dataset[column])

                if num_to_cat is not None:
                    for column in num_to_cat:
                        dataset[column] = dataset[column].astype('object')
            return dataset
```
### remove_imbalance
* Used to handle unbalanced datasets(rare classes) through oversampling/ undersampling techniques
* Input Description: data: the input dataframe with target column.
                     threshold: the threshold of mismatch between the target values to perform balancing.
* Output: A balanced dataframe.
```python
    def remove_imbalance(self, data, target, threshold=10.0, oversample=True, smote=False):
            X = data.drop(target, axis=1)
            y = data[target]

            self.logger_object.log(self.file_object,
                                   'Class Imbalance Process Starts in the remove_imbalance method of the DataPreprocessor class')

            no_of_classes = data[target].nunique()

            if no_of_classes == 2:

                thresh_satisfied = ((data[target].value_counts() / float(len(data[target])) * 100).any() < threshold)
                if thresh_satisfied:
                    if smote:
                        smote = SMOTE()
                        X, y = smote.fit_resample(X, y)
                    elif oversample:
                        ROS = RandomOverSampler(sampling_strategy='auto', random_state=42)
                        X, y = ROS.fit_sample(X, y)
                    else:
                        ROS = RandomUnderSampler(sampling_strategy='auto', random_state=42)
                        X, y = ROS.fit_sample(X, y)
            else:

                high = (data[target].value_counts() / float(len(data[target])) * 100).ravel().max()
                low = (data[target].value_counts() / float(len(data[target])) * 100).ravel().min()

                thresh_satisfied = (high - low > 100.0 - threshold)

                if thresh_satisfied:
                    if smote:
                        for i in range(no_of_classes - 2):
                            smote = SMOTE()
                            X, y = smote.fit_resample(X, y)
                    elif oversample:
                        for i in range(no_of_classes - 2):
                            ROS = RandomOverSampler(sampling_strategy='auto', random_state=42)
                            X, y = ROS.fit_sample(X, y)
                    else:
                        for i in range(no_of_classes - 2):
                            ROS = RandomUnderSampler(sampling_strategy='auto', random_state=42)
                            X, y = ROS.fit_sample(X, y)

            y.to_frame(name=target)
            dfBalanced = pd.concat([X, y], axis=1)
            return dfBalanced

### remove_columns_with_minimal_variance
This method drops any numerical column with standard deviation below specified threshold
Input : data: input DataFrame in which we need to check std deviations
      : threshold : the threshold for std deviation below which we need to drop the columns
Output: A DataFrame with numerical columns with low std dev dropped.
```python

    def remove_columns_with_minimal_variance(self, data, threshold):
            sel = VarianceThreshold(threshold=(threshold * (1 - threshold)))
            columnlist = list(data.select_dtypes(include='number').columns)
            sel_var = sel.fit_transform(data[columnlist])
            new_data = data[data.columns[sel.get_support(indices=True)]]
            return new_data  # return the read data to the calling method
```
### standardize_data
This method will be used to standardize al the numeric variables. Where mean = 0, std dev = 1.
* Input : the input dataframe with numeric columns.
* Output: Standardized data where mean of each column will be 0 and standard deviation will be 1.
``` python           
    def standardize_data(self, dataframe):
            data = dataframe
            stdscalar = StandardScaler()
            scaled_data = stdscalar.fit_transform(data)
            scaled_data = pd.Dataframe(data=scaled_data, columns=data.columns)
            return scaled_data
```

###  normalize_data
This method will be used to normalize all the numeric variables. Where min value = 0 and max value = 1.
* Input : the input dataframe with numeric columns.
* Output: Normalized data where minimum value of each column will be 0 and maximum value of each column will be 1.
```python  
    def normalize_data(self, dataframe):
        data = dataframe
            normalizer = MinMaxScaler()
            normalized_data = normalizer.fit_transform(data)
            normalized_data = pd.Dataframe(data=normalized_data, columns=data.columns)
            return normalized_data
```        
### pca
This method reduces the dimension from scaled Data which enables quick for large data files.
* input      : Data which is Scaled, var_explained = 0.90(default value)
* Output     : It returns the scaled and reduced dimensions.

```python
    def pca(self, data, var_explained):
        self.data = data
        self.var_explained = var_explained
           n = len(data.keys())  # find out the no columns in the data
            mat_pca = PCA(n_components=n)
            mat_pca.fit(data)  # applying PCA model

            ##calculate variance ratios
            variance = mat_pca.explained_variance_ratio_
            cum_var = np.cumsum(np.round(mat_pca.explained_variance_ratio_, decimals=3) * 100)
```    
### calc_num_components
This function is used for calculating number of principal components to use:
```python
            def calc_num_components(cum_var, var_explained):
                for i in range(n):
                    if cum_var[i] >= var_explained:
                        return i + 1

            # call the function to calulate num_components:
            n_components = calc_num_components(cum_var, var_explained)
            # create the PCA instance
            pca = PCA(n_components=n_components)
            principal_components = pca.fit_transform(data)

            # Convert into dataframe
            pca_data = pd.DataFrame(data=principal_components,
                                    columns=['PC' + str(i) for i in range(1, n_components + 1)])
            return pca_data

            raise Exception()
```
### preprocess
This function is used to preprocess the data by calling the apis listed above
* input: dataset, target columns, unwanted columns
* output: preprocessed target and feature dataset

```python
    def preprocess(self, dataset, target_column,unwanted_cols):
        dataset = self.remove_columns(dataset, columns=['Unnamed: 0'])
        dataset = self.impute_missing_values(data=dataset, mv_flag=True, target=target_column)
        # dataset = self.remove_columns(dataset, unwanted_cols)
        dataset = self.remove_imbalance(dataset, target_column, threshold=10.0, oversample=True, smote=False)
        dataset, self.y = self.separate_label_feature(dataset, target_column)
        self.x = self.remove_columns_with_minimal_variance(data=dataset, threshold=0.1)
        return self.x, self.y
```