# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

step1. Start

step2 .Import pandas module and import the required data set.

step 3.Find the null values and count them.

step 4.Count number of left values.

step 5.From sklearn import LabelEncoder to convert string values to numerical values.

step 6.From sklearn.model_selection import train_test_split.

step 7.Assign the train dataset and test dataset.

step 8.From sklearn.tree import DecisionTreeClassifier.

step 9.Use criteria as entropy.

step 10.From sklearn import metrics.

step 11.Find the accuracy of our model and predict the require values.

## Program:
```
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Navee kumar V
RegisterNumber: 212223230140

import pandas as pd
data = pd.read_csv("Employee.csv")
data
data.head()
data.info()
data.isnull().sum()
data["left"].value_counts
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)
from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])

```
## Output:
Data:
![Screenshot 2024-09-13 142258](https://github.com/user-attachments/assets/23e43e13-5487-4d23-8500-bc16448a493a)

 Accuray:
 
 ![image](https://github.com/user-attachments/assets/6bfaae2a-fe34-4383-9682-4b339365c15f)

Predict:

![image](https://github.com/user-attachments/assets/8d42ee5f-f62f-4c32-96c8-03a3148aeda8)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
