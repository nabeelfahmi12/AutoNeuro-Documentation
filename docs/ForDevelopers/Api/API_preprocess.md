

## Preprocessor():
This class shall be used to include all Data Pre-processing techniques to be fed to the Machine Learning Models

###   get_data_profile

<script src="https://gist.github.com/nabeelfahmi12/17ccd79ce9fb88485003cb3ad149dd40.js"></script>

### separatete Label features
This is used to seperate the target and feature as X and Y

<script src="https://gist.github.com/nabeelfahmi12/dcbab22bf7a9a8e9f50b05307003f924.js"></script>

### remove_columns
This method removes the given columns from a pandas dataframe.

<script src="https://gist.github.com/nabeelfahmi12/23e9e1e6304f58607ff730dacc7d789c.js"></script>   

###  impute_missing_values
This method will be used to impute missing values in the dataframe

<script src="https://gist.github.com/nabeelfahmi12/a6be5d74a76a1c743f8fd6962a37579e.js"></script>

### type_conversion
This method will be used to convert column datatype from numerical to categorical or vice-versa, if possible.

<script src="https://gist.github.com/nabeelfahmi12/e3c453e783d01b947f1e28e2d74a4e75.js"></script>

### remove_imbalance
* Used to handle unbalanced datasets(rare classes) through oversampling/ undersampling techniques
* Input Description: data: the input dataframe with target column.
                     threshold: the threshold of mismatch between the target values to perform balancing.
* Output: A balanced dataframe.

<script src="https://gist.github.com/nabeelfahmi12/3bb4e1188d98ba57918f09c7b2738877.js"></script>


### remove_columns_with_minimal_variance
This method drops any numerical column with standard deviation below specified threshold
Input : data: input DataFrame in which we need to check std deviations
      : threshold : the threshold for std deviation below which we need to drop the columns
Output: A DataFrame with numerical columns with low std dev dropped.

<script src="https://gist.github.com/nabeelfahmi12/9579af5801359e2b723f37e3e8318d42.js"></script>

### standardize_data
This method will be used to standardize al the numeric variables. Where mean = 0, std dev = 1.
* Input : the input dataframe with numeric columns.
* Output: Standardized data where mean of each column will be 0 and standard deviation will be 1.

<script src="https://gist.github.com/nabeelfahmi12/1955b227fb2bca574d353d6c27dfcf10.js"></script>

###  normalize_data
This method will be used to normalize all the numeric variables. Where min value = 0 and max value = 1.
* Input : the input dataframe with numeric columns.
* Output: Normalized data where minimum value of each column will be 0 and maximum value of each column will be 1.

<script src="https://gist.github.com/nabeelfahmi12/b950c9b5c1cec69daf2a7eb9f940c867.js"></script>
       
### pca
This method reduces the dimension from scaled Data which enables quick for large data files.
* input      : Data which is Scaled, var_explained = 0.90(default value)
* Output     : It returns the scaled and reduced dimensions.

<script src="https://gist.github.com/nabeelfahmi12/98e54cdffb58cbea6af47c0de1673474.js"></script>
    
### calc_num_components
This function is used for calculating number of principal components to use:

<script src="https://gist.github.com/nabeelfahmi12/58b1dd32eb313fa46f4c03e89ced899d.js"></script>

### preprocess
This function is used to preprocess the data by calling the apis listed above
* input: dataset, target columns, unwanted columns
* output: preprocessed target and feature dataset

<script src="https://gist.github.com/nabeelfahmi12/01eaaf56da722cb8ebc66811694fd319.js"></script>