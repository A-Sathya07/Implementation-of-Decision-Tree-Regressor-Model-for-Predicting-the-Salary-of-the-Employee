Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: SUDHARSAN U

RegisterNumber: 212225040433

import pandas as pd
from sklearn.tree import DecisionTreeRegressor
import matplotlib.pyplot as plt
import numpy as np

# Step 1: Load dataset

# Step 2: Select features and target
X = data[['Level']]  # Independent variable
y = data['Salary']   # Dependent variable

# Step 3: Train Decision Tree Regressor
model = DecisionTreeRegressor(random_state=0)
model.fit(X, y)

# Step 4: Predict Salary for a specific Level
level_to_predict = 6.5  # example
predicted_salary = model.predict([[level_to_predict]])
print(f"Predicted Salary for Level {level_to_predict}: {predicted_salary[0]}")

# Step 5: Visualize results
X_grid = np.arange(min(X.Level), max(X.Level), 0.01).reshape(-1,1)
plt.scatter(X, y, color='red', label='Actual Salary')
plt.plot(X_grid, model.predict(X_grid), color='blue', label='Predicted Salary')
plt.title('Decision Tree Regression Model')
plt.xlabel('Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
