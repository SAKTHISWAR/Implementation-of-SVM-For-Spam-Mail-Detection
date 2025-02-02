# Implementation-of-SVM-For-Spam-Mail-Detection

# AIM:
To write a program to implement the SVM For Spam Mail Detection.

# Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

# Algorithm
1. Import the packages.
2. Analyse the data.
3. Use modelselection and Countvectorizer to preditct the values.
4. Find the accuracy and display the result.

# Program:

Program to implement the SVM For Spam Mail Detection.

### Developed by: SAKTHISWAR S
### RegisterNumber:  212222230127


```python
import chardet
file = '/content/spam.csv'
with open(file,'rb') as rawdata:
  result = chardet.detect(rawdata.read(100000))
result

import pandas as pd 
data = pd.read_csv("/content/spam.csv",encoding='Windows-1252')

data.head()

data.info()

data.isnull().sum()

x=data["v1"].values

y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()

x_train = cv.fit_transform(x_train)
x_test = cv.transform(x_test)

from sklearn.svm import SVC
svc = SVC()
svc.fit(x_train,y_train)

y_pred = svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

```

# Output:
## RESULT
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m1.png)

## data.head()
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m2.png)


## data.info()
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m3.png)

## data.isnull().sum()
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m4.png)

## predicted values
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m5.png)

## Accuracy 
![image](https://github.com/SAKTHISWAR/Implementation-of-SVM-For-Spam-Mail-Detection/blob/main/m6.png)


# Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
