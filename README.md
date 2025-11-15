# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the packages.
2.Analyse the data.
3.Use modelselection and Countvectorizer to preditct the values.
4.Find the accuracy and display the result.

## Program:
```python
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Deepak S
RegisterNumber: 212224230053
*/

import pandas as pd
data=pd.read_csv("spam.csv", encoding='Windows-1252')
data

data.shape

x=data['v2'].values
y=data['v1'].values
x.shape

y.shape

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2, random_state=0)
x_train

x_train.shape

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score,confusion_matrix,classification_report
acc=accuracy_score(y_test,y_pred)
acc

con=confusion_matrix(y_test,y_pred)
print(con)

cl=classification_report(y_test,y_pred)
print(cl)
```

## Output:

<img width="1452" height="572" alt="image" src="https://github.com/user-attachments/assets/f3f508de-a764-46ff-9aab-002c3ab1c440" />

<img width="1450" height="611" alt="image" src="https://github.com/user-attachments/assets/90927cf7-c017-4170-8756-0eb3f1bcfad2" />

<img width="1443" height="724" alt="image" src="https://github.com/user-attachments/assets/b5097c67-ada8-46c7-b7e0-543e8e60309a" />

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
