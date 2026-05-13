# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import required libraries.
2. Load the dataset using pandas.
3. Create a copy of the dataset.
4. Remove unnecessary columns (sl_no, salary).
5. Check for null values and duplicates.
6. Convert categorical data into numerical data using Label Encoding.
7. Separate input features (x) and target variable (y).
8. Split the dataset into training and testing data.
9. Create the Logistic Regression model.
10.Train the model using training data.
11. Predict output using test data.
12. Calculate accuracy of the model.
13. Generate classification report.
14. Predict placement status for new student data.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: cholimgapuram sai likitha
RegisterNumber:  212224230046
import pandas as pd
data = pd.read_csv("Placement_Data (1).csv")
print(data.head())
data1 = data.copy()
data1 = data1.drop(["sl_no", "salary"], axis=1)
print(data1.head())
print(data1.isnull().sum())
print(data1.duplicated().sum())
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data1["gender"] = le.fit_transform(data1["gender"])
data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
data1["degree_t"] = le.fit_transform(data1["degree_t"])
data1["workex"] = le.fit_transform(data1["workex"])
data1["specialisation"] = le.fit_transform(data1["specialisation"])
data1["status"] = le.fit_transform(data1["status"])
x = data1.iloc[:, :-1]
y = data1["status"]
print(x.head())
print(y.head())
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(
    x, y, test_size=0.2, random_state=0
)
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver="liblinear")
lr.fit(x_train, y_train)
y_pred = lr.predict(x_test)
print("Predicted Values:")
print(y_pred)
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)
from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test, y_pred)
print(classification_report1)
prediction = lr.predict([[1, 80, 1, 90, 1, 1, 90, 1, 0, 85, 1, 85]])
print("Prediction:", prediction)
if prediction[0] == 1:
    print("Student is Placed")
else:
    print("Student is Not Placed")
*/
```

## Output:
<img width="728" height="796" alt="image" src="https://github.com/user-attachments/assets/c2f7b140-42d3-4e69-af69-24935d7e6d20" />

Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
