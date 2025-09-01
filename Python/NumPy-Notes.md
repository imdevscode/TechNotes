# NumPy Notes
## NumPy and Why It Is Faster Than Python Lists

- **NumPy** stands for *"Numerical Python"* and is an open-source library written in C language for numerical computing and data analysis.  
- It provides a powerful n-dimensional array object called **ndarray**.  
- NumPy was created in **2005** by **Travis Oliphant**.  
- NumPy arrays are up to **50x faster** than regular Python lists for numerical operations.  
- Efficient memory usage and fast performance due to underlying implementations in **C and C++** for core operations.  
- Essential for fields like **data science**, where large amounts of data must be processed quickly.  

---

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

- **Mathematical Functions:** Support element-wise operations and complex mathematical routines including linear algebra, Fourier transforms, and random number generation.  
