---
title: "Combining Data Sets with Python"
date: "2020-11-24T00:00:00Z"
---
This post describes how to combine datasets vertically with Python. It closely mirrors the post *Combining Data Sets with SAS*. 

The two main types of joins are vertical joins and horizontal joins.


__I.	Vertical Joins__

First, we have to import the libraries that we need for the task.

```python
import numpy as np
import pandas as pd
```

Let’s create three datasets in Python and then experiment with vertical joins. <!--more-->

```python
dsone={'VarA': ['a1', 'a2','a3'], 'VarB':['b1', 'b2', 'b3'], 'VarC': ['c1', 'c2', 'c3'] }
one=pd.DataFrame(dsone)
print(one)
```
### Here is the output from print(one)


![dataset_one](/image/p_dataset_one.png "Is it working?")

### Python code to create dataset two:

```python
dstwo={'VarA' : ['a2', 'a3', 'a4'], 'VarB': ['b2', 'b3', 'b4'], 'VarC': ['c2', 'c3', 'c4']}
two=pd.DataFrame(dstwo)
print(two)
```

### Output for dataset two:

![dataset_two](/image/p_dataset_two.png)

### Python code to create dataset three:

```python
dsthree={'VarA': ['a1', 'a2', 'a3'], 'VarB': ['b1', 'b2', 'b3'], 'VarD': [21,13,15]}
three=pd.DataFrame(dsthree)
print(three)
```

### Output for dataset three:

![dataset_three](/image/p_dataset_three.png)

### Combining dataset one and dataset two

```python
one_two=pd.concat([one, two])
print(one_two)
```

### Output table for dataset one_two:

![dataset_one_two](/image/p_dataset_one_two.png)

### Combining dataset one and dataset three:

```python
one_three=pd.concat([one,three])
print(one_three)
```

### Output table one_three:

![dataset_one_three](/image/p_dataset_one_three.png)



