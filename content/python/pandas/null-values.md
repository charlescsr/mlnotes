---
title: "Find Null values in DF"
author: "Charles"
date: 2020-08-15
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
df = pd.read_csv('train.csv')
```


```python
df.isnull().sum().any()
```




    False



If this value is True we need to find the columns that are null


```python
df.isnull().sum()
```




    ID           0
    target       0
    48df886f9    0
    0deb4b6a8    0
    34b15f335    0
                ..
    71b203550    0
    137efaa80    0
    fb36b89d9    0
    7e293fbaf    0
    9fc776466    0
    Length: 4993, dtype: int64



No values were null so the 4th cell was not needed
