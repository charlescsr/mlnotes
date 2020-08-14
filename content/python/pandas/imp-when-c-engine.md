---
title: "When using C engine remember this"
author: "Charles"
date: 2020-08-14
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
df = pd.read_csv('test.csv', sep=',', engine='c') #C engine requires separator else use python engine
```
