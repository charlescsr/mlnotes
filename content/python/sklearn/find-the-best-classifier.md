---
title: "Method to find best classifier"
author: "Charles"
date: 2020-08-08
description: "-"
type: technical_note
draft: false
---

```python
from sklearn.naive_bayes import MultinomialNB
from sklearn.naive_bayes import GaussianNB
from sklearn.naive_bayes import BernoulliNB
from sklearn.svm import SVC
from sklearn.neural_network import MLPClassifier
from sklearn.ensemble import AdaBoostClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import f1_score, confusion_matrix, accuracy_score
```


```python
classifiers = {
    'Multinomial NB': MultinomialNB(),
    'Gaussian NB': GaussianNB(),
    'Linear SVM': SVC(kernel='linear'),
    'RBF SVM': SVC(kernel='rbf'),
    'Sigmoid SVM': SVC(kernel='sigmoid'),
    #FOR SVM USE HYPERPARAMETER TUNING TO BETTER UNDERSTAND WHAT TO TAKE
    'MLP Classifier': MLPClassifier(),
    'MLP Hidden Layer': MLPClassifier(hidden_layer_sizes=[100,100]),
    'Ada Boost': AdaBoostClassifier(),
    'Decision Tree': DecisionTreeClassifier(),
    'Random Forest': RandomForestClassifier(),
    'Gradient Boosting': GradientBoostingClassifier(),
    'Logistic Regression': LogisticRegression()
}
```


```python
f1_scores = dict()

for classifier in classifiers:
    
    clf = classifiers[classifier]
    clf.fit(train_x,test_x)
    y_pred = clf.predict(train_y)
    f1_scores[classifier] = f1_score(y_pred, test_y)
    print(classifier, f1_scores[classifier])
```


```python
acc_scores = dict()

for classifier in classifiers:
    
    clf = classifiers[classifier]
    clf.fit(train_x,train_y)
    y_pred = clf.predict(test_x)
    acc_scores[classifier] = accuracy_score(y_pred, y_test)
    print(classifier, acc_scores[classifier])
```
