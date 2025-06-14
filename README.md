# Implementation-of-SVM-For-Spam-Mail-Detection
## Date : 12/05/25
## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the Program.
 
2.Import the necessary packages.

3.Read the given csv file and display the few contents of the data.

4.Assign the features for x and y respectively.

5.Split the x and y sets into train and test sets.

6.Convert the Alphabetical data to numeric using CountVectorizer.

7.Predict the number of spam in the data using SVC (C-Support Vector Classification) method of SVM (Support vector machine) in sklearn library.

8.Find the accuracy of the model.

9.End the Program.
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: ALLAM SESANK
RegisterNumber: 212223240006 
*/
```
```
import pandas as pd

data=pd.read_csv("spam.csv",encoding="Windows-1252")

data.head()

data.info()

data.isnull().sum()

x=data["v1"].values
y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```


## Output:
![image](https://github.com/user-attachments/assets/9b15973f-2e2b-4f08-8974-df96facaa46c)
![image](https://github.com/user-attachments/assets/ab0676c8-6016-48ef-b2c7-ced67ea2c1fe)
![image](https://github.com/user-attachments/assets/64955215-2c76-47a8-871f-8db62dac0117)
![Image-4](https://github.com/user-attachments/assets/8aafe725-8dc0-4803-88c1-a823bfcf5ee9)

![Image-5](https://github.com/user-attachments/assets/8ff7db68-1e63-4994-a01c-83c35ee2d4d3)





## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
