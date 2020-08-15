---
title: "Find Uniqueness in a column without null values"
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
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>target</th>
      <th>48df886f9</th>
      <th>0deb4b6a8</th>
      <th>34b15f335</th>
      <th>a8cb14b00</th>
      <th>2f0771a37</th>
      <th>30347e683</th>
      <th>d08d1fbe3</th>
      <th>6ee66e115</th>
      <th>...</th>
      <th>3ecc09859</th>
      <th>9281abeea</th>
      <th>8675bec0b</th>
      <th>3a13ed79a</th>
      <th>f677d4d13</th>
      <th>71b203550</th>
      <th>137efaa80</th>
      <th>fb36b89d9</th>
      <th>7e293fbaf</th>
      <th>9fc776466</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>000d6aaf2</td>
      <td>38000000.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>000fbd867</td>
      <td>600000.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0027d6b71</td>
      <td>10000000.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0028cbf45</td>
      <td>2000000.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>002a68644</td>
      <td>14400000.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 4993 columns</p>
</div>




```python
unique_vals = df.nunique().reset_index() #Doesn't count null values by default
unique_vals.columns = ["Column Name", "Uniqueness"]
unique_vals.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Column Name</th>
      <th>Uniqueness</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>ID</td>
      <td>4459</td>
    </tr>
    <tr>
      <th>1</th>
      <td>target</td>
      <td>1413</td>
    </tr>
    <tr>
      <th>2</th>
      <td>48df886f9</td>
      <td>32</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0deb4b6a8</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>34b15f335</td>
      <td>29</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
