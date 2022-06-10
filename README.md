# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import pandas as pd and import the required dataset.

2.Calculate the null values in the dataset.

3.Import the LabelEncoder from sklearn.preprocessing

4.Convert the string values to numeric values.

5.Import train_test_split from sklearn.model_selection.

6.Assign the train and test dataset.

7.Import DecisionTreeRegressor from sklearn.tree.

8.Import metrics from sklearn.metrics.

9.Calculate the MeanSquareError.

10.Apply the metrics to the dataset.

11.Predict the output for the required values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: P.SYAM TEJ
RegisterNumber:  212221240056
*/
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x= data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2,random_state = 2)

from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)

from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse

r2= metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
![6 1](https://user-images.githubusercontent.com/93427224/172997050-df7f6a89-6d9a-470b-817f-9b90d03bceac.png)

![6 2](https://user-images.githubusercontent.com/93427224/172997071-51396181-6042-432c-a7af-7c2eb401661f.png)

![6 3](https://user-images.githubusercontent.com/93427224/172997085-a112357d-9552-4cbb-9bd1-849007947b2a.png)

![6 4](https://user-images.githubusercontent.com/93427224/172997103-881d7947-b929-40c6-b465-70e4e3b36021.png)

![6 5](https://user-images.githubusercontent.com/93427224/172997117-b058d13c-e227-4c0b-9f92-1f5cdcf31a7c.png)

![6 6](https://user-images.githubusercontent.com/93427224/172997149-b97803e5-f555-4fe4-8b6e-d6b3ea2f7499.png)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
