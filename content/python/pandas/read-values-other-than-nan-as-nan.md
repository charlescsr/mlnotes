---
title: "Read Values other than NaN as NaN"
author: "Charles"
date: 2020-09-11
description: "-"
type: technical_note
draft: false
---
**Not all null values have NaN in them some may have other substitutes like '_' or '?' To mitigate that we have na_values in read_csv**


```python
import pandas as pd
```


```python
d = {'id':[0, 1, 2], 'Name':['Ben', 'Max', '?']}
df = pd.DataFrame(d)
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
      <th>id</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Ben</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Max</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>?</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.isnull().sum().any()
```




    False



'?' is interpreted as not a null value here


```python
df.to_csv('test.csv')
```


```python
df_real = pd.read_csv('test.csv', na_values=['?']) # Reads '?' as NaN value
df_real.head()
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
      <th>Unnamed: 0</th>
      <th>id</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0</td>
      <td>Ben</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>Max</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_real.isnull().sum().any()
```




    True


