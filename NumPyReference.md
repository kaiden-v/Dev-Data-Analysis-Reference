# NumPy Reference

## Introduction

NumPy is the fundamental package for numerical computing in Python. It provides support for **arrays, matrices, mathematical functions, linear algebra, and more**.

As this is a quick reference guide, more in depth information on the package can be found on the offical [NumPy Documentation](https://numpy.org/doc/).

---

## Installing NumPy

You can install NumPy in your Python environment using **pip**:

```bash
pip install numpy <optional_version>
```

---

## Importing NumPy

The standard convention to import NumPy into a python file is:

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
type_arr = arr.astype(np.<type>)                    # Converts elements in an array to specific data type
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
# Basic arithmetic
arr_add = arr + <value>             # Add a scalar to each element
arr_sub = arr - <value>             # Subtract a scalar from each element
arr_mul = arr * <value>             # Multiply each element by a scalar
arr_div = arr / <value>             # Divide each element by a scalar
arr_floordiv = arr // <value>       # Floor division of each element by a scalar

# Mathematical functions
arr_abs = np.abs(arr)               # Absolute value (same as arr.abs())
arr_fabs = np.fabs(arr)             # Absolute value for floats/complex
arr_sqrt = np.sqrt(arr)             # Square root (arr ** 0.5)
arr_square = np.square(arr)         # Square of each element (arr ** 2)
arr_exp = np.exp(arr)               # Exponent e^x of each element

# Logarithms
arr_log = np.log(arr)               # Natural log (base e)
arr_log10 = np.log10(arr)           # Log base 10
arr_log2 = np.log2(arr)             # Log base 2
arr_log1p = np.log1p(arr)           # log(1 + x)

# Sign and rounding
arr_sign = np.sign(arr)             # Sign of each element: 1, 0, -1
arr_ceil = np.ceil(arr)             # Ceiling (smallest integer ≥ element)
arr_floor = np.floor(arr)           # Floor (largest integer ≤ element)
arr_rint = np.rint(arr)             # Round to nearest integer

# Fractional and special checks
arr_frac, arr_int = np.modf(arr)    # Fractional and integer parts separately
arr_isnan = np.isnan(arr)           # Boolean array: True if element is NaN
arr_isfinite = np.isfinite(arr)     # Boolean: True if element is finite
arr_isinf = np.isinf(arr)           # Boolean: True if element is infinite

# Trigonometric functions
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

# Logical operations
arr_not = np.logical_not(arr) # Element-wise NOT (equivalent to ~arr for booleans)

```

### Binary Functions (Matrix-Wise Operations)
```python

# Arithmetic operations
arr_add = np.add(arr1, arr2)                # Add corresponding elements in arrays
arr_sub = np.subtract(arr1, arr2)           # Subtract elements in second array from first array
arr_mul = np.multiply(arr1, arr2)           # Multiply array elements
arr_div = np.divide(arr1, arr2)             # Divide elements
arr_floordiv = np.floor_divide(arr1, arr2)  # Floor division (truncates remainder)
arr_pow = np.power(arr1, arr2)              # Raise elements in first array to powers indicated in second array
arr_mod = np.mod(arr1, arr2)                # Element-wise modulus (remainder of division)
arr_copysign = np.copysign(arr1, arr2)      # Copy sign of values in second array to first array

# Element-wise max / min
arr_max = np.maximum(arr1, arr2)            # Element-wise maximum
arr_fmax = np.fmax(arr1, arr2)              # Element-wise maximum ignoring NaN
arr_min = np.minimum(arr1, arr2)            # Element-wise minimum
arr_fmin = np.fmin(arr1, arr2)              # Element-wise minimum ignoring NaN

# Comparison operators → return Boolean arrays
arr_gt = np.greater(arr1, arr2)             # arr1 > arr2
arr_ge = np.greater_equal(arr1, arr2)       # arr1 >= arr2
arr_lt = np.less(arr1, arr2)                # arr1 < arr2
arr_le = np.less_equal(arr1, arr2)          # arr1 <= arr2
arr_eq = np.equal(arr1, arr2)               # arr1 == arr2
arr_ne = np.not_equal(arr1, arr2)           # arr1 != arr2

# Logical operations → Boolean arrays
arr_and = np.logical_and(arr1, arr2)        # Element-wise AND (&)
arr_or = np.logical_or(arr1, arr2)          # Element-wise OR (|)
arr_xor = np.logical_xor(arr1, arr2)        # Element-wise XOR (^)
```
### Conditional Selection

```python
result_arr = np.where(<condition>, <value_or_array_if_true>, <value_or_array_if_false>)
# Creates a new array where:
# - Each element is taken from the second argument if the condition is True
# - Each element is taken from the third argument if the condition is False

indices_where = np.where(<array_expression>)        # Indices where condition is True
```
---
