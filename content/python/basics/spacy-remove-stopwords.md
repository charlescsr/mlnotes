---
title: "Remove stopwords using SpaCy"
author: "Charles"
date: 2020-08-10
description: "-"
type: technical_note
draft: false
---

```python
#Remove stop words
import spacy
from spacy.lang.en.stop_words import STOP_WORDS
#from string import punctuations
```


```python
nlp = spacy.load('en_core_web_md')
```


```python
def normalize(msg):
    
    doc = nlp(msg)
    res=[]
    
    for token in doc:
        if(token.is_stop or token.is_digit or token.is_punct or not(token.is_oov)):
            pass
        else:
            res.append(token.lemma_.lower())
    
    return res
```


```python

```
