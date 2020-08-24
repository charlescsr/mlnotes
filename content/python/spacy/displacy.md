---
title: "Displacy for Custom NER"
author: "Charles"
date: 2020-08-23
description: "-"
type: technical_note
draft: false
---

```python
import spacy
nlp = spacy.load('en')
```


```python
from spacy import displacy
def explain_text_entities(text):
    doc = nlp(text)
    for ent in doc.ents:
        print(f'Entity: {ent}, Label: {ent.label_}, {spacy.explain(ent.label_)}')
    displacy.render(doc, style='ent', jupyter=True)
```


```python
t = 'No different than Apple ORG . To play a specific list of music you must have an Amazon of Spotify PRODUCT “plus/prime/etc” account. So you must pay to play “your” music. 3 CARDINAL stars for that reason. Everything else is great .'
```


```python
explain_text_entities(t)
```

    Entity: Apple ORG, Label: ORG, Companies, agencies, institutions, etc.
    Entity: 3, Label: CARDINAL, Numerals that do not fall under another type



<span class="tex2jax_ignore"><div class="entities" style="line-height: 2.5; direction: ltr">No different than 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Apple ORG
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; text-transform: uppercase; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
 . To play a specific list of music you must have an Amazon of Spotify PRODUCT “plus/prime/etc” account. So you must pay to play “your” music. 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    3
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; text-transform: uppercase; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 CARDINAL stars for that reason. Everything else is great .</div></span>



```python

```
