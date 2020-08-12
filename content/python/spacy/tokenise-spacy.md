---
title: "Tokenise characters in SpaCy"
author: "Charles"
date: 2020-08-08
description: "-"
type: technical_note
draft: false
---

```python
import spacy
```


```python
nlp = spacy.load('en_core_web_md')
```


```python
def tokenise(words):
    res = []
    
    for word in words:
        doc = nlp(word)
        
        for token in doc:
            res.append(token.text)
    return res
```


```python
sample_words = ["hi and hello", "thank you and goodnight"]
```


```python
result = tokenise(sample_words)

print(result)
```

    ['hi', 'and', 'hello', 'thank', 'you', 'and', 'goodnight']



```python

```
