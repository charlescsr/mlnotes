---
title: "Bigrams Function"
author: "Charles"
date: 2020-08-22
description: "-"
type: technical_note
draft: false
---

```python
def bigram(doc):
    '''Create list for result'''
    result = list()
    '''Create list containing no punctuations'''
    sentence = list()

    '''Parse throught the list and add the tokens that are words'''
    for token in doc:
        if token.is_alpha:
            sentence.append(token)

    for word in range(len(sentence) - 1):
        firstword = sentence[word]
        secondword = sentence[word + 1]
        element = [firstword, secondword]
        result.append(element)
    
    return result 
```


```python

```
