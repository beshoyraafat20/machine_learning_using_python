# Interactive Regression Cheat Sheet

Welcome! This interactive cheat sheet provides a quick overview of common regression models and associated Python functions.

---

### Comparing Regression Types

This section details various regression models, including their purpose, pros, cons, modeling equations, and Python code syntax using scikit-learn.

| Model Name | Description | Code Syntax |
|---|---|---|
| Simple Linear Regression | **Purpose:** To predict a dependent variable based on one independent variable.<br>**Pros:** Easy to implement, interpret, and efficient for small datasets.<br>**Cons:** Not suitable for complex relationships; prone to underfitting.<br>**Modeling equation:** y = b₀ + b₁x | 
```python
1 from sklearn.linear_model import LinearRegression
2 model = LinearRegression()
3 model.fit(X, y) |
| Polynomial Regression | **Purpose:** To capture nonlinear relationships between variables.<br>**Pros:** Better at fitting nonlinear data compared to linear regression.<br>**Cons:** Prone to overfitting with high-degree polynomials.<br>**Modeling equation:** y = b₀ + b₁x + b₂x² + ... | ```python<br>1 from sklearn.preprocessing import PolynomialFeatures<br>2 from sklearn.linear_model import LinearRegression<br>3 poly = PolynomialFeatures(degree=2)<br>4 X_poly = poly.fit_transform(X)<br>5 model = LinearRegression().fit(X_poly, y)``` |
| Multiple Linear Regression | **Purpose:** To predict a dependent variable based on multiple independent variables.<br>**Pros:** Accounts for multiple factors influencing the outcome.<br>**Cons:** Assumes a linear relationship between predictors and target.<br>**Modeling equation:** y = b₀ + b₁x₁ + b₂x₂ + ... | ```python<br>1 from sklearn.linear_model import LinearRegression<br>2 model = LinearRegression()<br>3 model.fit(X, y)``` |
| Logistic Regression | **Purpose:** To predict probabilities of categorical outcomes.<br>**Pros:** Efficient for binary classification problems.<br>**Cons:** Assumes a linear relationship between independent variables and log-odds.<br>**Modeling equation:** log(p/(1-p)) = b₀ + b₁x₁ + ... | ```python<br>1 from sklearn.linear_model import LogisticRegression<br>2 model = LogisticRegression()<br>3 model.fit(X, y)``` |

---

### Associated Functions Commonly Used

This section lists common scikit-learn functions used in regression tasks, along with their descriptions and Python code syntax.

| Function/Method Name | Brief Description | Code Syntax |
|---|---|---|
| `train_test_split` | Splits the dataset into training and testing subsets to evaluate the model's performance. | ```python<br>1 from sklearn.model_selection import train_test_split<br>2 X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)``` |
| `StandardScaler` | Standardizes features by removing the mean and scaling to unit variance. | ```python<br>1 from sklearn.preprocessing import StandardScaler<br>2 scaler = StandardScaler()<br>3 X_scaled = scaler.fit_transform(X)``` |
| `log_loss` | Calculates the logarithmic loss, a performance metric for classification models. | ```python<br>1 from sklearn.metrics import log_loss<br>2 loss = log_loss(y_true, y_pred_proba)``` |
| `mean_absolute_error` | Calculates the mean absolute error between actual and predicted values. | ```python<br>1 from sklearn.metrics import mean_absolute_error<br>2 mae = mean_absolute_error(y_true, y_pred)``` |
| `mean_squared_error` | Computes the mean squared error between actual and predicted values. | ```python<br>1 from sklearn.metrics import mean_squared_error<br>2 mse = mean_squared_error(y_true, y_pred)``` |
| `root_mean_squared_error` | Calculates the root mean squared error (RMSE), a commonly used metric for regression tasks. | ```python<br>1 from sklearn.metrics import mean_squared_error<br>2 import numpy as np<br>3 rmse = np.sqrt(mean_squared_error(y_true, y_pred))``` |
| `r2_score` | Computes the R-squared value, indicating how well the model explains the variability of the target variable. | ```python<br>1 from sklearn.metrics import r2_score<br>2 r2 = r2_score(y_true, y_pred)``` |

---
