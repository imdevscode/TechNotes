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
