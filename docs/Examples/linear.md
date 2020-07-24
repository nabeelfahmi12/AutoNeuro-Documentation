##Linear Regression
**Linear regression is probably one of the most important and widely used regression techniques.
It’s among the simplest regression methods.
One of its main advantages is the ease of interpreting results.**
<hr>

``` Python
import matplotlib.pyplot as plt
import numpy as np
from sklearn import datasets, linear_model
from sklearn.metrics import mean_squared_error, r2_score
```

**Load the diabetes dataset**
``` Python
diabetes_X, diabetes_y = datasets.load_diabetes(return_X_y=True)
```
**Use only one feature**<br>
``` Python
diabetes_X = diabetes_X[:, np.newaxis, 2]</i>
```
**Split the data into training/testing sets**<br>
``` Python
diabetes_X_train = diabetes_X[:-20]<br>
diabetes_X_test = diabetes_X[-20:]
```
**Split the targets into training/testing sets**<br>
``` python
diabetes_y_train = diabetes_y[:-20]<br>
diabetes_y_test = diabetes_y[-20:]
```
**Create linear regression object**<br>
```python
regr = linear_model.LinearRegression()
```

**Train the model using the training sets**<br>
```python
regr.fit(diabetes_X_train, diabetes_y_train)
```

**Make predictions using the testing set**<br>
```python
diabetes_y_pred = regr.predict(diabetes_X_test)
```

**The coefficients**<br>
```python
print('Coefficients: \n', regr.coef_)
```
**The mean squared error**
```python
print('Mean squared error: %.2f'
      % mean_squared_error(diabetes_y_test, diabetes_y_pred))
```
**The coefficient of determination: 1 is perfect prediction**
```python
print('Coefficient of determination: %.2f'
      % r2_score(diabetes_y_test, diabetes_y_pred))
```


**Plot outputs**<br>
```python
plt.scatter(diabetes_X_test, diabetes_y_test,  color='black')
plt.plot(diabetes_X_test, diabetes_y_pred, color='blue', linewidth=3)
plt.xticks()
plt.yticks()
plt.show()
```