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

## Creating arrays

### From existing data sets

```python
data1 = [<data>]
arr1 = np.array(data1)      # Establish 1 dimensional array from list

data2 = [[<data>],[<data>]]
arr2 = np.array(data2)      # Establish 2 dimensional array from list

data3 - [[[<data>],[<data>]],[[<data>],[<data>]]]
arr3 = np.array(data3)      # Establish 3 dimensional array from list
```

### Creating and establishing the data

```python
arr = np.arange(<start>, <stop>, <step>)            # Creates a 1 dimensional array with values in a given range
arr = np.linspace(<start>, <stop>, <num_values>)    # Creates a 1 dimensional array with evenly spaced values
arr = np.ones(<shape>)                              # Creates an array filled with ones of shape (rows, columns)
arr = np.zeros(<shape>)                             # Creates an array filled with zeros of shape (rows, columns)
arr = np.empty(<shape>)                             # Creates an array without setting initial values of shape (rows, columns)
arr = np.full(<shape>, <fill_value>)                # Creates an array filled with a specific value of shape (rows, columns)
arr = np.identity(<square_size>)                    # Creates an identity matrix of square shape 
arr = np.triu(<array>)                              # Keeps the upper triangular part of a matrix
arr = np.tril(<array>)                              # Keeps the lower triangular part of a matrix
```

---

## Array Information