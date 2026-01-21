# NumPy Reference

## Introduction

NumPy is the fundamental package for numerical computing in Python. It provides support for **arrays, matrices, mathematical functions, linear algebra, and more**.

As this is a quick reference guide, more in depth information on the package can be found on the offical [NumPy Documentation](https://numpy.org/doc/) page.

---

## Installing NumPy

You can install NumPy in your Python environment using the following command in a command line:

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
# Standard data creation
arr = np.arange(<start>, <stop>, <step>)            # Creates a 1 dimensional array with values in a given range
arr = np.linspace(<start>, <stop>, <num_values>)    # Creates a 1 dimensional array with evenly spaced values
arr = np.ones(<shape>)                              # Creates an array filled with ones of shape (rows, columns)
arr = np.zeros(<shape>)                             # Creates an array filled with zeros of shape (rows, columns)
arr = np.empty(<shape>)                             # Creates an array without setting initial values of shape (rows, columns)
arr = np.full(<shape>, <fill_value>)                # Creates an array filled with a specific value of shape (rows, columns)
arr = np.identity(<square_size>)                    # Creates an identity matrix of square shape
arr = np.diag(<array>)                              # Create square matrix with <array> on diagonal
arr = np.triu(<array>)                              # Keeps the upper triangular part of a matrix
arr = np.tril(<array>)                              # Keeps the lower triangular part of a matrix

# Random data creation
np.random.seed(<seed_value>)                                            # Set random seed for reproducibility
arr_uniform = np.random.uniform(low=<min>, high=<max>, size=<size>)     # Creates an array of samples from an uniform distributions
arr_integers = np.random.randint(low=<min>, high=<max>, size=<size>)    # Creates an array of samples from an integer uniform distributions
arr_std_norm = np.random.standard_normal(size=<size>)                   # Creates an array of samples from a standard normal distribution
arr_normal = np.random.normal(loc=<mean>, scale=<std>, size=<size>)     # Creates an array of samples from a custom normal distribution
arr_binomial = np.random.binomial(n=<trials>, p=<prob>, size=<size>)    # Creates an array of samples from a binomial distribution
arr_beta = np.random.beta(a=<alpha>, b=<beta>, size=<size>)             # Creates an array of samples from a beta distribution
arr_chisq = np.random.chisquare(df=<degrees_of_freedom>, size=<size>)   # Creates an array of samples from a chi-square distribution
arr_gamma = np.random.gamma(shape=<shape>, scale=<scale>, size=<size>)  # Creates an array of samples from a gamma distribution

```

### Saving and Loading Arrays
```python
# Saving
np.save(<file_name>, arr)                                                   # Saves array to a .npy file
np.savez(<file_name>, <key_1>=<arr_1>, ..., <key_n>=<arr_n>)                # Saves multiple arrays to a .npy file
np.savez_compressed(<file_name>, <key_1>=<arr_1>, ..., <key_n>=<arr_n>)     # Saves multiple arrays to a compresesed .npy file

# Loading
arr = np.load(<file_path>)                                                  # load a single array from a .npy file
arr_1, ..., arr_n = np.load(<file_path=>)                                   # load multiple arrays from a .npy file

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
```python
# Basic indexing
elem = arr[<index>]                                                 # Access element in a 1D array
elem = arr[<row_index>, <col_index>]                                # Access element in a 2D array
elem = arr[<row_index>, <col_index>, <axis_3>]                      # Access element in a 3D array

# Slicing
slice_1d = arr[<start>:<stop>:<step>]                               # Slice 1D array
slice_row = arr[<row_index>, <start>:<stop>]                        # Slice columns of a specific row
slice_col = arr[<start>:<stop>, <col_index>]                        # Slice rows of a specific column
slice_2d = arr[<row_start>:<row_stop>, <col_start>:<col_stop>]      # Slice a 2D block

# Boolean / conditional indexing
bool_idx = arr[<array_conditional_expression>]                      # Array of elements meeting condition
arr[<array_conditional_expression>] = <new_value>                   # Modify elements conditionally

# Special indexs
last_elem = arr[-1]                                                 # Accewss last element in an array
reverse_arr = arr[::-1]                                             # Returns reversed array

```

---

## Universal Functions (Operations)

### Array / Matix Manipulation
```python 
# Reshape / Flatten
arr_reshaped = arr.reshape(<new_shape>)                                 # Change shape; total elements must match
arr_flat = arr.flatten()                                                # Flattens higher dimension array into a 1D array 

# Transpose
arr_T = arr.T                                                           # Transpose 2D array (swap rows and columns)
arr_swapaxes = arr.swapaxes(<axis1>, <axis2>)                           # Swap two axes of array

# Add / Remove dimensions
arr_expand = np.expand_dims(arr, axis=<axis>)                           # Add a new axis at specified position
arr_squeeze = np.squeeze(arr, axis=<axis>)                              # Removes axies of length 1 (Optionally removes specified axis)

# Stack / Concatenate Arrays
arr_vstack = np.vstack([<array1>, <array2>, ...])                       # Stack arrays vertically (row-wise)
arr_hstack = np.hstack([<array1>, <array2>, ...])                       # Stack arrays horizontally (column-wise)
arr_stack = np.stack([<array1>, <array2>, ...], axis=<axis>)            # Stack along a new axis
arr_concat = np.concatenate([<array1>, <array2>, ...], axis=<axis>)     # Join along existing axis

# Split Arrays
arr_split = np.split(<array>, <num_or_indices>, axis=<axis>)            # Split array into equal or specified parts
arr_hsplit = np.hsplit(<array>, <num_or_indices>)                       # Split horizontally (columns)
arr_vsplit = np.vsplit(<array>, <num_or_indices>)                       # Split vertically (rows)
```

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

### Statistical Methods
```python
arr_sum = np.sum(arr)                 # Calculates sum of elements
arr_mean = np.mean(arr)               # Calculates arithmetic mean
arr_std = np.std(arr)                 # Calculates standard deviation
arr_var = np.var(arr)                 # Calculates variance
arr_min = np.min(arr)                 # Calculates minimum value
arr_max = np.max(arr)                 # Calculates maximum value
arr_argmin = np.argmin(arr)           # Calculates index of minimum value
arr_argmax = np.argmax(arr)           # Calculates index of maximum value
arr_cumsum = np.cumsum(arr)           # Calculates cumulative sum (starts from 0)
arr_cumprod = np.cumprod(arr)         # Calculates cumulative product (starts from 1)

# Note: Functions accept axis argumement to perform function along either the columns (axis = 0) or rows (axis = 1)
```

### Sorting
```python
arr_sorted = np.sort(arr)              # Sorts array (accepts axis argumement to perform function along either the columns (axis = 0) or rows (axis = 1))
```

### Unique and Set Logic
```python
arr_intersect = np.intersect1d(<array1>, <array2>)      # Elements common to array 1 and array 2
arr_union = np.union1d(<array1>, <array2>)              # Sorted union of elements in array 1 and array 2
arr_in = np.in1d(<array1>, <array2>)                    # Boolean array: True if element of array 1 is in array 2
arr_diff = np.setdiff1d(<array1>, <array2>)             # Elements in array 1 that are not in array 2
arr_symdiff = np.setxor1d(<array1>, <array2>)           # Elements in either array 1 or array 2 but not both
```

### Linear Algebra
```python
# Basic Operations
diag_arr = np.diag(A)                                               # Extract diagonal of matrix as 1D array
dot_product = np.dot(A, B)                                          # Calculates the dot product of two matrices (Alternative using @ operator)
trace_val = np.trace(A)                                             # Calculates the trace of a matrix (sum of diagonal elements)
det_val = np.linalg.det(A)                                          # Calculates the determinant of a matrix
rank_A = np.linalg.matrix_rank(A)                                   # Calculates the Rank of a matrix
norm_A = np.linalg.norm(A)                                          # Calculates the Frobenius (default) or L2 norm
eig_vals, eig_vecs = np.linalg.eig(A)                               # Calculates the eigenvalues and eigenvectors of a matrix 
inv_A = np.linalg.inv(A)                                            # Calculates the exact inverse of square matrix
pinv_A = np.linalg.pinv(A)                                          # Calculates the Moore-Penrose pseudoinverse
Q, R = np.linalg.qr(A)                                              # Calculates the QR decomposition: A = Q @ R
U, S, Vh = np.linalg.svd(A)                                         # Calculates the Singular Value Decomposition: A = U @ diag(S) @ Vh
x = np.linalg.solve(A, B)                                           # Solves the linear equation Ax = B exactly
x_lstsq, residuals, rank, s = np.linalg.lstsq(A, B, rcond=None)     # Solves the Least-squares solution
```