---
title: "Custom Lambda DataFrame"
author: "Charles"
date: 2020-08-10
description: "-"
type: technical_note
draft: false
---

```python
import pandas as pd
```


```python
data = ['Vachitaya aapuuuuuuuuu','Sing in the rain' ,'Great power comes wih great responsibility']  
df = pd.DataFrame(data, columns = ['Sent'])
df
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
      <th>Sent</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Vachitaya aapuuuuuuuuu</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sing in the rain</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Great power comes wih great responsibility</td>
    </tr>
  </tbody>
</table>
</div>




```python
def sent_length(message):
    
    return (len(message))
```


```python
df['len'] = df['Sent'].apply(sent_length)
```


```python
df
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
      <th>Sent</th>
      <th>len</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Vachitaya aapuuuuuuuuu</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sing in the rain</td>
      <td>16</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Great power comes wih great responsibility</td>
      <td>42</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
