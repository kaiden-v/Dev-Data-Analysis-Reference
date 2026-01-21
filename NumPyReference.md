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


## Indexing and Slicing


---

## Universal Functions (Operations)

### Unary Functions (Elements-Wise Operations)
``` python 
arr_add = arr + <value>             # Add a scalar to each element
arr_sub = arr - <value>             # Subtract a scalar from each element
arr_mul = arr * <value>             # Multiply each element by a scalar
arr_div = arr / <value>             # Divide each element by a scalar
arr_floordiv = arr // <value>       # Floor division of each element by a scalar

arr_abs = np.abs(arr)               # Absolute value (same as arr.abs())
arr_fabs = np.fabs(arr)             # Absolute value for floats/complex
arr_sqrt = np.sqrt(arr)             # Square root (arr ** 0.5)
arr_square = np.square(arr)         # Square of each element (arr ** 2)
arr_exp = np.exp(arr)               # Exponent e^x of each element

arr_log = np.log(arr)               # Natural log (base e)
arr_log10 = np.log10(arr)           # Log base 10
arr_log2 = np.log2(arr)             # Log base 2
arr_log1p = np.log1p(arr)           # log(1 + x)

arr_sign = np.sign(arr)             # Sign of each element: 1, 0, -1
arr_ceil = np.ceil(arr)             # Ceiling (smallest integer ≥ element)
arr_floor = np.floor(arr)           # Floor (largest integer ≤ element)
arr_rint = np.rint(arr)             # Round to nearest integer

arr_frac, arr_int = np.modf(arr)    # Fractional and integer parts separately
arr_isnan = np.isnan(arr)           # Boolean array: True if element is NaN
arr_isfinite = np.isfinite(arr)     # Boolean: True if element is finite
arr_isinf = np.isinf(arr)           # Boolean: True if element is infinite

arr_cos = np.cos(arr)               # Take each element as arugument for cos
arr_sin = np.sin(arr)               # Take each element as arugument for sin
arr_tan = np.tan(arr)               # Take each element as arugument for tan

arr_cosh = np.cosh(arr)             # Take each element as arugument for cosh
arr_sinh = np.sinh(arr)             # Take each element as arugument for sinh
arr_tanh = np.tanh(arr)             # Take each element as arugument for tanh

arr_arccos = np.arccos(arr)         # Take each element as arugument for arccos
arr_arcsin = np.arcsin(arr)         # Take each element as arugument for arcsin
arr_arctan = np.arctan(arr)         # Take each element as arugument for arctan

arr_arccosh = np.arccosh(arr)       # Take each element as arugument for arccosh
arr_arcsinh = np.arcsinh(arr)       # Take each element as arugument for arcsinh
arr_arctanh = np.arctanh(arr)       # Take each element as arugument for arctanh

arr_not = np.logical_not(arr) # Element-wise NOT (equivalent to ~arr for booleans)

```

### Binary Functions (Matrix-Wise Operations)

---
