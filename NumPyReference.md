# Numpy Reference
informaaiton on numpy

---

## Installing and Importing NumPy
The NumPy package can be installed and/or added to a python envirionment using the following command in the command line: `pip install numpy`.  
Additonally, if a specific verison of NumPy would like to be installed the command `pip install numpy <version>` will do so.

importing by 

```python 
import numpy as np
```

---

## Creating arrays from exisitng data

```python
data1 = [<data>]
arr1 = np.array(data1)      # Establish 1 dimensional array from list

data2 - [[<data>],[<data>]]
arr2 = np.array(data2)      # Establish 2 dimensional array from list

data2 - [[[<data>],[<data>]],[[<data>],[<data>]]]
arr2 = np.array(data2)      # Establish 3 dimensional array from list
```