# Cheat Sheet: Linear and Logistic Regression

## Comparing Different Regression Types

| Model Name                  | Description                                                                 | Modeling Equation                   | Example Code |
|-----------------------------|-----------------------------------------------------------------------------|-------------------------------------|--------------|
| **Simple Linear Regression** | Predicts a dependent variable based on one independent variable.<br>**Pros:** Easy to implement and interpret, efficient for small datasets.<br>**Cons:** Not suitable for complex relationships; may underfit. | y = b0 + b1x | `python<br>from sklearn.linear_model import LinearRegression<br>model = LinearRegression()<br>model.fit(X, y)<br>` |
| **Polynomial Regression**    | Captures nonlinear relationships between variables.<br>**Pros:** Fits nonlinear data better.<br>**Cons:** Can overfit with high-degree polynomials. | y = b0 + b1x + b2x² + ... | ``` python<br>from sklearn.preprocessing import PolynomialFeatures<br>from sklearn.linear_model import LinearRegression<br>poly = PolynomialFeatures(degree=2)<br>X_poly = poly.fit_transform(X)<br>model = LinearRegression().fit(X_poly, y)<br> ``` |
| **Multiple Linear Regression** | Predicts a dependent variable based on multiple independent variables.<br>**Pros:** Considers multiple factors.<br>**Cons:** Assumes linear relationship between predictors and target. | y = b0 + b1x1 + b2x2 + ... | ```python<br>from sklearn.linear_model import LinearRegression<br>model = LinearRegression()<br>model.fit(X, y)<br>``` |
| **Logistic Regression**      | Predicts probabilities of categorical outcomes.<br>**Pros:** Efficient for binary classification.<br>**Cons:** Assumes a linear relationship between independent variables and log-odds. | log(p/(1-p)) = b0 + b1x1 + ... | ```python<br>from sklearn.linear_model import LogisticRegression<br>model = LogisticRegression()<br>model.fit(X, y)<br>``` |

---

## Commonly Used Functions

| Function/Method Name      | Brief Description | Example Code |
|--------------------------|-------------------|--------------|
| **train_test_split**      | Splits the dataset into training and testing subsets. | ```python<br>from sklearn.model_selection import train_test_split<br>X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)<br>``` |
| **StandardScaler**        | Standardizes features by removing the mean and scaling to unit variance. | ```python<br>from sklearn.preprocessing import StandardScaler<br>scaler = StandardScaler()<br>X_scaled = scaler.fit_transform(X)<br>``` |
| **log_loss**              | Calculates the logarithmic loss for classification models. | ```python<br>from sklearn.metrics import log_loss<br>loss = log_loss(y_true, y_pred_proba)<br>``` |
| **mean_absolute_error**   | Calculates the mean absolute error between actual and predicted values. | ```python<br>from sklearn.metrics import mean_absolute_error<br>mae = mean_absolute_error(y_true, y_pred)<br>``` |
| **mean_squared_error**    | Computes the mean squared error between actual and predicted values. | ```python<br>from sklearn.metrics import mean_squared_error<br>mse = mean_squared_error(y_true, y_pred)<br>``` |
| **root_mean_squared_error** | Calculates the root mean squared error (RMSE). | ```python<br>from sklearn.metrics import mean_squared_error<br>import numpy as np<br>rmse = np.sqrt(mean_squared_error(y_true, y_pred))<br>``` |
| **r2_score**              | Computes the R-squared value, indicating how well the model explains the variability of the target variable. | ```python<br>from sklearn.metrics import r2_score<br>r2 = r2_score(y_true, y_pred)<br>``` |

---

> **Note:**  
> - `X` refers to the feature data (independent variables), and `y` refers to the target variable (dependent variable).
> - Use these code snippets as a quick reference when building regression or classification models with scikit-learn.
