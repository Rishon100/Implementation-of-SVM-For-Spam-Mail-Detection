# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: V RISHON ANAND
RegisterNumber:  24900460
*/
```
import chardet
file='spam.csv'
with open(file,'rb') as rawdata:
    result=chardet.detect(rawdata.read(100000))
print(result)
import pandas as pd
data=pd.read_csv("spam.csv",encoding='Windows-1252')
print("The First five Data:\n")
print(data.head())
print("\nThe Information:\n")
print(data.info())
print("\nTo count the Number of null values in dataset:\n")
print(data.isnull().sum())
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
print("\nThe Y_prediction\n")
print(y_pred)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
print("\nAccuracy:\n")
print(accuracy)
```

## Output:
![SVM For Spam Mail Detection](sam.png)
![Screenshot 2024-12-25 194003](https://github.com/user-attachments/assets/7bd868b6-f0d9-4bfa-a769-9297d04212c1)
![Screenshot 2024-12-25 194009](https://github.com/user-attachments/assets/09e72a51-aad9-49cf-9c41-13c9b370dc64)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
