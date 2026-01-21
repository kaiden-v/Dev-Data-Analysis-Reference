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

### Converting existing data sets (lists) into arrays

```python

data1 = [<data>]                                    # Will create 1 a dimensional array from list
data2 = [[<data>],[<data>]]                         # Will create 2 a dimensional array from list
data3 - [[[<data>],[<data>]],[[<data>],[<data>]]]   # Will create 3 a dimensional array from list

arr = np.array(<data>)                              # Converts data in list to ndarray object
```

### Creating array and initialising the data

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

```python
arr.shape                                           # Returns the shape of the array (rows, columns)
arr.ndim                                            # Returns the number of dimensions
arr.size                                            # Returns the total number of elements
arr.dtype                                           # Returns the data type of elements
arr.itemsize                                        # Returns the size (in bytes) of each element
arr.nbytes                                          # Returns the tota memory used by the array (bytes)
```

### Array Data Types
```python
type_arr = arr.astype(np.<type>)
```

| Type           | Code     | Description                                           |
|----------------|---------|-------------------------------------------------------|
| int8           | i1      | 8-bit signed integer                                  |
| uint8          | u1      | 8-bit unsigned integer                                |
| int16          | i2      | 16-bit signed integer                                 |
| int32          | i4      | 32-bit signed integer                                 |
| int64          | i8      | 64-bit signed integer                                 |
| float16        | f2      | Half-precision floating point                         |
| float32        | f4 / f  | Standard single-precision floating point             |
| float64        | f8 / d  | Standard double-precision floating point             |
| float128       | f16 / g | Extended-precision floating point (rare / platform dependent) |
| complex64      | c8      | Complex number (2×32-bit floats)                     |
| complex128     | c16     | Complex number (2×64-bit floats)                     |
| complex256     | c32     | Complex number (2×128-bit floats, rare / platform dependent) |
| bool           | ?       | Boolean (True / False)                                |
| object         | O       | Any Python object                                     |
| string_        | S       | Fixed-length ASCII string (e.g., 'S10')              |
| unicode_       | U       | Fixed-length Unicode string (e.g., 'U10')            |

---


