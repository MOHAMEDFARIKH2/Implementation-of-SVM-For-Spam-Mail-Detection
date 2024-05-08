# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import neccessary libraries required.
2. Load the dataset using pd.read_csv.
3. Use CountVectorizer to convert text data into a matrix of token counts.
4. Create an SVM model with a linear kernel.
5. print the accuracy and classification report.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: H MOHAMED FARIKH
RegisterNumber: 212223080032
*/
import chardet 
file="spam.csv"
with open(file, "rb") as rawdata:
  result=chardet.detect(rawdata.read(100000))
result
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
accuracy=metric.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
data.head():

![Screenshot 2024-05-08 105822](https://github.com/MOHAMEDFARIKH2/Implementation-of-SVM-For-Spam-Mail-Detection/assets/168570140/ffc6dfc3-f4eb-4934-a3e2-078926a59f59)

data.info():

![Screenshot 2024-05-08 105838](https://github.com/MOHAMEDFARIKH2/Implementation-of-SVM-For-Spam-Mail-Detection/assets/168570140/3cbb2ceb-ae6c-4c57-b328-e1be09d7c864)

data.isnull().sum():

![Screenshot 2024-05-08 105902](https://github.com/MOHAMEDFARIKH2/Implementation-of-SVM-For-Spam-Mail-Detection/assets/168570140/d67697a0-2975-4a8f-98a6-34c0d859a90a)

accuracy:

![Screenshot 2024-05-08 111602](https://github.com/MOHAMEDFARIKH2/Implementation-of-SVM-For-Spam-Mail-Detection/assets/168570140/63209ba8-3cbd-45b8-b855-bd5f89be3e92)






## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
