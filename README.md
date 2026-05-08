# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import required libraries.
2. Load the dataset using read_csv().
3. Remove unwanted column (salary).
4. Convert categorical data into numerical form using get_dummies().
5. Separate input features (X) and output (y).
6. Split dataset into training and testing data.
7. Create Logistic Regression model.
8. Train the model using training data.
9. Find and print model accuracy.
10. Select one feature for visualization.
11. Plot scatter graph of data points.
12. Predict probabilities using logistic regression.
13. Draw logistic regression curve.
14. Add labels and title to graph.
15. Display the graph.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: cholimgapuram sai likitha
RegisterNumber:  212224230046
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
df = pd.read_csv("Placement_Data (1).csv")
df = pd.get_dummies(df.drop("salary", axis=1), drop_first=True)
X = df.drop("status_Placed", axis=1)
y = df["status_Placed"]
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)
print("Accuracy:", model.score(X_test, y_test))
X1 = X.iloc[:, 0].values.reshape(-1,1)
model.fit(X1, y)
plt.scatter(X1, y, color='blue')
x = np.linspace(X1.min(), X1.max(), 100).reshape(-1,1)
y_prob = model.predict_proba(x)[:,1]
plt.plot(x, y_prob, color='red')
plt.xlabel("Feature")
plt.ylabel("Probability")
plt.title("Logistic Regression")
plt.show() 
*/
```

## Output:
<img width="1137" height="845" alt="Screenshot 2026-05-08 171238" src="https://github.com/user-attachments/assets/afb471ac-27d9-46ab-bb3d-38e42e49c7d3" />


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
