# credit-exploratory-data-analysis


Applying EDA to understand  risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers.


[![MATPLOTLIB](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge)](https://img.shields.io/badge/-MATPLOTLIB-007aa6?style=for-the-badge) [![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue) [![Jupyter](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge)](https://img.shields.io/badge/-Jupyter-f5841f?style=for-the-badge) [![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white) [![Numpy](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white)](https://img.shields.io/badge/Numpy-777BB4?style=for-the-badge&logo=numpy&logoColor=white) <a href="https://www.microsoft.com/en-in/microsoft-365/excel" rel="nofollow"><img alt="Excel" src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" data-canonical-src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" style="max-width: 100%;"/></a>

## Visualization

### Clients income amount vs education (Target 0 are non defaulter & Target 1 are defaulter).
[![Architecure Diagram](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182550.png?raw=true)](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182550.png?raw=true)
- Based on there avgerage income of different occupation we can provide loan to the new clients as per as there income and occupation.



### Clients income amount vs income type based on family status (Target 0 are non defaulter & Target 1 are defaulter).
[![Architecure Diagram](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182720.png?raw=true)](https://github.com/Monishlalani/credit-exploratory-data-analysis/blob/main/Screenshot_20221231_182720.png?raw=true)
- Business man and commercial associate are likely to apply more for loan and are Non-defaulters
- Married Business man have more income compared to others and are non defaulters.
- While pensioner, student and unemployed have high risk of defaulters due to low income.


## Final conclusion
- Person with Higher education , Academic degree should be preferred.
- Applicant with income type of Business and commercial associate are likely to be non default.
- Person with House as an asset can be preferred as a asset collateral and can we given loan.
- Based on there avgerage income of different occupation we can provide loan to the new clients as per as there income and occupation.
- Applicants who are employed and are married have lesser chance to be defaulter.
- Male clients with Incomplete Education having very low salaries have a high risk of default.
- 30% of people of loan purpose Refusal to name the goal were defaulters.
- Hobby,Money for a third person,Payments on other loans,Gasification / water supply ,Car repairs may have high chance to be defaulters
- 9.57% people with income type Unemployed have high chance to be defaulters.


## Author

Monish Lalani

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/monish-lalani/) 
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:monishlalani12@gmail.com)  





from sklearn.ensemble import GradientBoostingRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# Assuming you have already loaded and preprocessed your data

# Splitting data into features and target variable
X = ...  # Features
y = ...  # Target variable (TV ownership)

# Splitting data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Building and training the Gradient Boosting Regression model
gb_regressor = GradientBoostingRegressor()
gb_regressor.fit(X_train, y_train)

# Making predictions
predictions = gb_regressor.predict(X_test)

# Evaluating the model
mse = mean_squared_error(y_test, predictions)
print("Mean Squared Error on Test Set:", mse)

# You can use these predictions for further analysis or visualization




from sklearn.tree import DecisionTreeRegressor
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# Assuming you have already loaded and preprocessed your data

# Splitting data into features and target variable
X = ...  # Features
y = ...  # Target variable (TV ownership)

# Splitting data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Building and training the Decision Tree Regression model
dt_regressor = DecisionTreeRegressor()
dt_regressor.fit(X_train, y_train)

# Making predictions
predictions = dt_regressor.predict(X_test)

# Evaluating the model
mse = mean_squared_error(y_test, predictions)
print("Mean Squared Error on Test Set:", mse)

# You can use these predictions for further analysis or visualization


