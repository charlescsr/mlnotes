---
title: "Complete Toolbox for ML"
author: "Charles"
date: 2020-10-17
description: "-"
type: technical_note
draft: false
---
# ML Toolbox


```python
import numpy as np
import pandas as pd
import missingno as msno
import seaborn as sns
import plotly.graph_objects as go
import plotly.express as px
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import cross_val_score
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.model_selection import train_test_split
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
from sklearn.metrics import accuracy_score, f1_score, confusion_matrix, classification_report
%matplotlib inline
```

# NLP Toolbox


```python
import numpy as np
import pandas as pd
import missingno as msno
import seaborn as sns
import plotly.graph_objects as go
import plotly.express as px #Might not work with ktrain
import matplotlib.pyplot as plt
import spacy

import tensorflow as tf
from wordcloud import WordCloud, STOPWORDS 
import ktrain
from ktrain import text

from collections import Counter
```
