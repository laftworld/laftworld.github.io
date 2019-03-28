---
title: linear regression
layout: post
date: 2019-03-28 10:41:00 +0800
category: blog
author: laftworld
---

```python
import matplotlib.pyplot as plt
import numpy as np
from sklearn import datasets, linear_model, metrics

diabetes = datasets.load_diabetes() # Load the diabetes dataset
diabetes_X = diabetes.data[:, np.newaxis, 2] # Use only one feature
diabetes_X_train, diabetes_y_train = diabetes_X[:-20], diabetes.target[:-20]
diabetes_X_test, diabetes_y_test = diabetes_X[-20:], diabetes.target[-20:]

regr = linear_model.LinearRegression() # Create linear regression object
regr.fit(diabetes_X_train, diabetes_y_train) # Train the model using the training sets
diabetes_y_pred = regr.predict(diabetes_X_test) # Make predictions using the testing set

print('Coefficients: \n', regr.coef_)
print("Mean squared error: %.2f" % metrics.mean_squared_error(diabetes_y_test, diabetes_y_pred))
print('Variance score: %.2f' % metrics.r2_score(diabetes_y_test, diabetes_y_pred))

plt.scatter(diabetes_X_test, diabetes_y_test,  color='black')
plt.plot(diabetes_X_test, diabetes_y_pred, color='blue', linewidth=3)
plt.show()
```

    Coefficients: 
     [938.23786125]
    Mean squared error: 2548.07
    Variance score: 0.47



![png](190328-linear-regression-sklearn_files/190328-linear-regression-sklearn_0_1.png)


Means squared error: $\text{MSE} (y, \hat{y}) = \frac{1}{n}\sum^n_{i=1}(y_i-\hat{y})^2$

$R^2$ score (Variance score): $R^2(y, \hat{y}) = 1-\frac{\sum^n_{i=1}(y_i-\hat{y})^2}{\sum^n_{i=1}(y_i-\bar{y})^2}$

Means squared error: $\text{MSE} (y, \hat{y}) = \frac{1}{n}\sum^n_{i=1}(y_i-\hat{y})^2$

$R^2$ score (Variance score): $R^2(y, \hat{y}) = 1-\frac{\sum^n_{i=1}(y_i-\hat{y})^2}{\sum^n_{i=1}(y_i-\bar{y})^2}$
