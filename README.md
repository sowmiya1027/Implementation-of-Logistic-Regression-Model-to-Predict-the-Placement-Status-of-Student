# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1. Load the dataset, preprocess the data, and define the feature variables (X) and target variable (y).
2.Split the dataset into training and testing sets and apply feature scaling using StandardScaler.
3.Train the Logistic Regression model using the training data and make predictions on the test data.
4.Evaluate the model using confusion matrix, accuracy score, and classification report, and predict the placement status for new student data.
```

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: Sowmiya R
RegisterNumber:  212225040420
*/

import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import confusion_matrix, accuracy_score, classification_report

data = pd.read_csv("Placement_Data.csv")

X = df[['Hours_Studied', 'Previous_Score', 'Internship']]
y = df['Placement']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)

scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
model = LogisticRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)

print("Confusion Matrix:\n", confusion_matrix(y_test, y_pred))
print("\nAccuracy Score:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred))

new_student = np.array([[6, 68, 1]])  # Example: 6 hours studied, 68 prev score, Internship yes
new_student_scaled = scaler.transform(new_student)
placement_pred = model.predict(new_student_scaled)
placement_prob = model.predict_proba(new_student_scaled)

print(f"\nPredicted Placement Status: {'Placed' if placement_pred[0]==1 else 'Not Placed'}")
print(f"Probability of Placement: {placement_prob[0][1]:.2f}")

```

## Output:
![the Logistic Regression Model to Predict the Placement Status of Student](sam.png)
<img width="1288" height="450" alt="image" src="https://github.com/user-attachments/assets/8bd7237d-7364-4dd2-be9e-db817b268425" />



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
