#                         SKILL ASSESSMENT
###                      GENDER-CLASSIFIER
## Algorithm
1.Import the necessary packages.
2.Read the input values like height,weight,shoe_size.
3.After that assign the values according to the gender.
4.Get the test data as well as test_labels for the sake of gender classification.
5.Implement it using Random forest,Logistic Regression and Support vector classifier.
6.Finally the classifier shows the gender classification on the basis of the inputs which is been given in test analysis.

## Program:
```
/*
Program to implement 
Developed by   :  BONAMSETTI NAGA NARENDRA
RegisterNumber :  212219040016
*/
import numpy as np
from sklearn import tree
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# [height, weight, shoe_size]
X = [[181, 80, 44], [177, 70, 43], [160, 60, 38], [154, 54, 37], [166, 65, 40],
     [190, 90, 47], [175, 64, 39],
     [177, 70, 40], [159, 55, 37], [171, 75, 42], [181, 85, 43], [168, 75, 41], [168, 77, 41]]

Y = ['male', 'male', 'female', 'female', 'male', 'male', 'female', 'female',
     'female', 'male', 'male', 'female', 'female']

test_data = [[190, 70, 43],[154, 75, 42],[181,65,40]]
test_labels = ['male','male','male']


#DecisionTreeClassifier
dtc_clf = tree.DecisionTreeClassifier()
dtc_clf = dtc_clf.fit(X,Y)
dtc_prediction = dtc_clf.predict(test_data)
print(dtc_prediction)

#RandomForestClassifier
rfc_clf = RandomForestClassifier()
rfc_clf.fit(X,Y)
rfc_prediction = rfc_clf.predict(test_data)
print(rfc_prediction)

#Support Vector Classifier
s_clf = SVC()
s_clf.fit(X,Y)
s_prediction = s_clf.predict(test_data)
print(s_prediction)


#LogisticRegression
l_clf = LogisticRegression()
l_clf.fit(X,Y)
l_prediction = l_clf.predict(test_data)
print(l_prediction)

#accuracy scores
dtc_tree_acc = accuracy_score(dtc_prediction,test_labels)
rfc_acc = accuracy_score(rfc_prediction,test_labels)
l_acc = accuracy_score(l_prediction,test_labels)
s_acc = accuracy_score(s_prediction,test_labels)

classifiers = ['Decision Tree', 'Random Forest', 'Logistic Regression' , 'SVC']
accuracy = np.array([dtc_tree_acc, rfc_acc, l_acc, s_acc])
max_acc = np.argmax(accuracy)
print(classifiers[max_acc] + ' is the best classifier for this problem')


```

## OUTPUT:

![image](https://user-images.githubusercontent.com/78774336/173183322-f3dbef81-786f-4e41-abba-717e7296c0d8.png)


