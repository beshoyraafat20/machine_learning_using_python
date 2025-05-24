# Cheat Sheet: Linear and Logistic Regression

## Comparing Different Regression Types

| Model Name                  | Description                                                                 | Modeling Equation                   | Example Code |
|-----------------------------|-----------------------------------------------------------------------------|-------------------------------------|--------------|
| **Simple Linear Regression** | Predicts a dependent variable based on one independent variable.<br>**Pros:** Easy to implement and interpret, efficient for small datasets.<br>**Cons:** Not suitable for complex relationships; may underfit. | y = b0 + b1x | ```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X, y)
``` |
| **Polynomial Regression**    | Captures nonlinear relationships between variables.<br>**Pros:** Fits nonlinear data better.<br>**Cons:** Can overfit with high-degree polynomials. | y = b0 + b1x + b2x² + ... | ```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)
model = LinearRegression().fit(X_poly, y)
``` |
| **Multiple Linear Regression** | Predicts a dependent variable based on multiple independent variables.<br>**Pros:** Considers multiple factors.<br>**Cons:** Assumes linear relationship between predictors and target. | y = b0 + b1x1 + b2x2 + ... | ```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X, y)
``` |
| **Logistic Regression**      | Predicts probabilities of categorical outcomes.<br>**Pros:** Efficient for binary classification.<br>**Cons:** Assumes a linear relationship between independent variables and log-odds. | log(p/(1-p)) = b0 + b1x1 + ... | ```python
from sklearn.linear_model import LogisticRegression
model = LogisticRegression()
model.fit(X, y)
``` |

---

## Commonly Used Functions

| Function/Method Name      | Brief Description | Example Code |
|--------------------------|-------------------|--------------|
| **train_test_split**      | Splits the dataset into training and testing subsets. | ```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
``` |
| **StandardScaler**        | Standardizes features by removing the mean and scaling to unit variance. | ```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
``` |
| **log_loss**              | Calculates the logarithmic loss for classification models. | ```python
from sklearn.metrics import log_loss
loss = log_loss(y_true, y_pred_proba)
``` |
| **mean_absolute_error**   | Calculates the mean absolute error between actual and predicted values. | ```python
from sklearn.metrics import mean_absolute_error
mae = mean_absolute_error(y_true, y_pred)
``` |
| **mean_squared_error**    | Computes the mean squared error between actual and predicted values. | ```python
from sklearn.metrics import mean_squared_error
mse = mean_squared_error(y_true, y_pred)
``` |
| **root_mean_squared_error** | Calculates the root mean squared error (RMSE). | ```python
from sklearn.metrics import mean_squared_error
import numpy as np
rmse = np.sqrt(mean_squared_error(y_true, y_pred))
``` |
| **r2_score**              | Computes the R-squared value, indicating how well the model explains the variability of the target variable. | ```python
from sklearn.metrics import r2_score
r2 = r2_score(y_true, y_pred)
``` |

---

> **Note:**  
> - `X` refers to the feature data (independent variables), and `y` refers to the target variable (dependent variable).
> - Use these code snippets as a quick reference when building regression or classification models with scikit-learn.