# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas library to read csv or excel file.
2. Import LabelEncoder using sklearn.preprocessing library.
3. Transform the data's using LabelEncoder.
4. Import decision tree classifier from sklearn.tree library to predict the values.
5. Find accuracy.
6. Predict the values.
7. End of the program.
 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Sai sonica CH
RegisterNumber: 212219040130 
*/
import pandas as pd
data=pd.read_csv("Employee.csv")
data.head()
data.info()
data.isnull().sum()
data["left"].value_counts()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics 
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
## HEAD:
![image](https://user-images.githubusercontent.com/79306169/174667871-d395683a-3a91-4be4-986b-9d8e54493d70.png)
## INFO:
![image](https://user-images.githubusercontent.com/79306169/174667909-cbfca455-367d-4873-b59c-9b8b928812e1.png)
## ISNULL:
![image](https://user-images.githubusercontent.com/79306169/174667952-67c6203b-ddfe-40dd-872b-830949fd117d.png)
## LEFT:
![image](https://user-images.githubusercontent.com/79306169/174668017-4a90a4e3-5b87-4b1c-990f-a69d527b6bd3.png)
## HEAD USING LABELENCODER:
![image](https://user-images.githubusercontent.com/79306169/174668069-d32ade93-f97c-424d-8840-9e95b67db343.png)
## ACCURACY:
![image](https://user-images.githubusercontent.com/79306169/174668119-53aa669e-7686-4b4a-9d51-569e6300a450.png)
## PREDICT:
![image](https://user-images.githubusercontent.com/79306169/174668160-6ed70f61-9504-4473-a9dd-bc4de2b08849.png)



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
