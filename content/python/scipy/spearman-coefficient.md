---
title: "Spearman Coefficient"
author: "Charles"
date: 2020-08-15
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
from scipy.stats import spearmanr
```


```python
df = pd.read_csv('train.csv')
```


```python
labels = []
values = []

for col in df.columns:
    if col not in ["ID", "target"]:
        labels.append(col)
        values.append(spearmanr(df[col.values], df['target'].values)[0])

correlation_df = pd.DataFrame({'column_label':labels, 'correlation_val':vals})        
correlation_df = correlation_df.sort_values(by='correlation_val')

correlation_df = correlation_df[(correlation_df['correlation_val'])]
```

IN PROGRESS
