# NumPy Notes

## NumPy and Why It Is Faster Than Python Lists
- **NumPy** stands for *"Numerical Python"* and is an open-source library written in C language for numerical computing and data analysis.  
- It provides a powerful n-dimensional array object called **ndarray**.  
- NumPy was created in **2005** by **Travis Oliphant**.  
- NumPy arrays are up to **50x faster** than regular Python lists for numerical operations.  
- Efficient memory usage and fast performance due to underlying implementations in **C and C++** for core operations.  
- Essential for fields like **data science**, where large amounts of data must be processed quickly.  
### Creating Arrays

```python
import numpy as np

a = np.array([1, 2, 3])         # 1D Array
print(a)                        # [1 2 3]

b = np.array([[1, 2, 3], [4, 5, 6]])  # 2D Array
```
### Array Attributes
  - a.shape returns the dimensions of the array.
  - a.dtype returns the data type of elements.

## Key Features of NumPy
- **N-Dimensional Arrays (ndarray):** Core data structure that supports homogeneous arrays (all elements of the same type) with any number of dimensions.  
- **High Performance:** Arrays are stored in contiguous memory locations (next to each other), enabling fast computation and low memory overhead compared to Python lists. 
- **Broadcasting:** Enables element-wise operations on arrays of different shapes by expanding smaller arrays to match larger ones.  
- **Vectorization:** Allows applying operations to entire arrays without explicit loops, boosting performance.  
- **Indexing & Slicing:** Supports slicing, array indexing, and boolean masking to access and manipulate array elements flexibly.

## Installation & Import
```python
pip install numpy
import numpy as np
```

## Creating NumPy Arrays
```python
	np.array([1, 2, 3])       # from list
	np.array((4, 5, 6))       # from tuple
	np.array(range(1, 5))     # from range
	print(np.arange(6))		  # Generates integers from 0 to 5
	
	
	np.zeros((3, 4))               # 3x4 array of zeros
	np.ones((2, 3), dtype=int)     # 2x3 array of ones
	np.empty((2, 2))               # Empty (uninitialized)
	np.arange(0, 10, 2)            # Even numbers in array: [0, 2, 4, 6, 8]
	np.linspace(0, 1, 5)           # [ 0.  2.5  5.  7.5 10.] evenly spaced
```

## NumPy Array Attributes
```python
	arr.shape       # (rows, columns)
	arr.ndim        # number of dimensions
	arr.size        # total elements
	arr.dtype       # data type
	arr.itemsize    # size of each element (bytes)
	arr.arange
	
	arr = np.array([[1, 2], [3, 4]])
	print(arr.shape)  # (2, 2)
	print(arr.size)   # 4
	print(arr.dtype)  # int64 (may vary)
```
## Difference between `ndarray` and `array`
- **ndarray:** The core array object class in NumPy.  
- **np.array():** A function used to create an `ndarray`.
  
## Shape of Array
- **Shape** is an attribute of an array that tells you the dimensions (rows, columns, etc.).  
- It returns the size along each axis:  
  - **1D array** → `(length,)`  
  - **2D array** → `(rows, columns)`  
  - **3D array** → `(depth, rows, columns)`, and so on.  
### Examples
```python
import numpy as np

# 1D array
a = np.array([1, 2, 3])
print(a.shape)   # (3,)

# 2D array
b = np.array([[1, 2, 3],
              [4, 5, 6]])
print(b.shape)   # (2, 3)

# 3D array
c = np.array([[[1, 2],
               [3, 4]],
              [[5, 6],
               [7, 8]]])
print(c.shape)   # (2, 2, 2)
```
- Also we can Reshape an 1D array to multi-dimension array.
  ```python
	arr = np.arange(6)			# [0, 1, 2, 3, 4, 5]
	print(arr.reshape(2, 3))	# Reshape to 2D array - 2 rows, 3 columns
								# [[0 1 2] [3 4 5]]
  ```
- Setting shape of existing array
  ```python
	x = np.array([1, 2, 3, 4, 5, 6])
	x.shape = (2, 3)
	print(x)
	# [[1 2 3]
	#  [4 5 6]]
  ```

## Broadcasting
- **Broadcasting** allows operations on arrays of different shapes.  
- It works by expanding the smaller array along missing dimensions so that the shapes match according to specific rules.  
### Broadcasting Rules
1. Same dimension size → compatible.  
2. One of them is `1` → stretch (broadcast) that dimension.  
3. If neither matches → incompatible (error).  
### Example 1: Simple Broadcasting
```python
import numpy as np

a = np.array([1, 2, 3])       # Shape: (3,)
b = np.array([[10], [20]])    # Shape: (2,1)

# Broadcasting b along columns, a along rows
result = a + b
print(result)
# [[11 12 13]
#  [21 22 23]]
```
### Output & Shapes during Broadcasting
```python
a: (1, 3)    → [[1, 2, 3]]
b: (2, 1)    → [[10],
                 [20]]

# Result shape: (2, 3)
# Output:
[[11 12 13]
 [21 22 23]]
```
### Example 2: Broadcasting with Scalars
```python
import numpy as np

arr = np.array([1, 2, 3])
print(arr + 10)   # Adds 10 to every element

# Output
# [11 12 13]
```
### Example 3: Incompatible Shapes
```python
import numpy as np

x = np.ones((3, 2))
y = np.ones((4, 2))

x + y			# ❌ ValueError: operands could not be broadcast together
# Reason: trailing dimensions (2) match, but (3) and (4) do not.
```

## Vectorization Operations
- **Vectorization** is performing operations on entire arrays without explicit loops.  
- It improves **speed** and **readability**.  
### Examples
```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)       # [5  7  9]
print(a - b)       # [-3 -3 -3]
print(a * b)       # [ 4 10 18]
print(a / b)       # [0.25 0.4  0.5 ]

print(np.sqrt(a))  		# [1.   1.41 1.73]
print(np.exp(a))   		# [ 2.72  7.39 20.09]
print(np.log(a))   		# [0.    0.69  1.10]
```

## Data Types (dtypes)
- A standard NumPy array (`ndarray`) is **homogeneous**, meaning all elements must have the same data type (`dtype`) internally.  
- However, there are a couple of exceptions and workarounds:  
### 1. Normal Behavior – Homogeneous Data
When we create a NumPy array with mixed types, NumPy automatically **upcasts** them to a common type that can hold all values.  
```python
import numpy as np

arr = np.array([1, 2.5, True, "hello"])
print(arr)         # ['1' '2.5' 'True' 'hello']
print(arr.dtype)   # <U32 (string type)
# Here int, float & boolean are upcasted into string
```
### 2. Using `dtype=object`
- We can store different Python objects in one array if we explicitly set `dtype=object`.  
```python
import numpy as np

arr = np.array([1, 2.5, "hello", True], dtype=object)
print(arr)         			# [1 2.5 'hello' True]
print(arr.dtype)   			# object
```
- This become array of Python object with some drawbacks like slower operation as loses NumPy vectorized feature and can't use C loops & behave as python list.
- Checking & converting datatype
```python
arr.dtype                       		# Check dtype
np.issubdtype(arr.dtype, np.floating)  	# Check if floating type
arr.astype(np.int32)             		# Convert type
```
#### Creating an Array with a Specific dtype
```python
import numpy as np

np.array([1, 2, 3], dtype=np.int32)            # INT type
np.array([1.5, 2.3], dtype=np.float32)         # Float type
np.array([1+2j, 3+4j], dtype=np.complex64)     # Complex type
np.array([True, False, True], dtype=np.bool_)  # Boolean type
np.array([1, "text", [1, 2, 3]], dtype=object) # Object type
```
