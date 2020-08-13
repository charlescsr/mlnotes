---
title: "Different Engines in read_csv"
author: "Charles"
date: 2020-08-13
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
FILEPATH = 'california_housing_train.csv'
```


```python
%%timeit
df = pd.read_csv(FILEPATH, engine='c') #C engine offers speed
```

    24.8 ms ± 6.24 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)



```python
%%timeit
df = pd.read_csv(FILEPATH, engine='python') #Python engine is more feature rich but slower
```

    139 ms ± 25.4 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)



```python

```
