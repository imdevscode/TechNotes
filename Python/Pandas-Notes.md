# Pandas
- **Pandas** is an open-source Python library used for data analysis, cleaning & manipulation.  
- The name *Pandas* is derived from **"Panel Data"** (multidimensional data) & **Data Analysis**.  
- Built on **NumPy**, hence supports its operations like vectorization.  
- Pandas programs can be written on any plain text editor like *Notepad, Notepad++*, etc., and saved with a **.py** extension.  

## Uses of Pandas
- Reading and writing data from various file formats like **CSV, Excel, and SQL databases**.  
- Merging multiple datasets, performing statistical analysis, cleaning data.  
- Visualizing data with plotting capabilities.  
---

## Installation
- To install **Pandas**, we just need Python and a package manager like **pip** (comes with Python):  
```bash
pip install pandas
```
- Once installed, we just need to import the Pandas library to start using it:
```python
import pandas as pd
```
---

## Data Structure
Pandas provides two main data structures:  
### 1) Series
- A **Series** is a 1D labelled array which can hold data of any type (integer, float, string, Python object, etc.).  
- It is similar to a **column** in Excel or a **table**.  
- It can have **integer** or **custom labels** as indexing for its elements.  
- A **Series** can be created from a **list, dictionary, or NumPy array**.  
#### Example:
```python
import pandas as pd
import numpy as np

# 1. Empy panda series
ser = pd.Series()
print(ser)
# output
Series([], dtype: float64)

# 2. From list
lst = [1, 3, np.nan, 6]
ser = pd.Series(lst)
print(ser)
# output
0	1
1	3
2	
3	6

# 3. Key/Value Objects as Series
daily_calories = {"day1": 300, "day2": 350, "day3": 400}
mySer1 = pd.Series(daily_calories)
mySer2 = pd.Series(calories, index = ["day1", "day2"])
print(mySer1)
print(mySer2)
# --Output mySer1	 ---output mySer2		
day1    300				day1    300
day2    350				day2	350
day3    400

# From Numpy array
arr = np.array(['a', 'b', 'c', 'd'])
ser1 = pd.Series(arr)				  # without custom index
ser2 = pd.Series(arr, index=[11, 12, 13, 14])	  # using custom index
print(ser1[2])		# Output: c
print(ser2[12])		# Output: b
print(ser2)
```
### 2) DataFrame
- A **DataFrame** is a **2D data structure**, similar to a table with **rows and columns**, used for handling large amounts of data.  
- **DataFrames** can be created from **lists, dictionaries, NumPy arrays, CSV, Excel, etc.**  
#### Example:
```python
# 1. Empty DataFrame
df = pd.DataFrame()
print(df)

# output
Empty DataFrame
Columns: []
Index: []

# ----------------
# 2. From lists
lst = ['A', 'B', 'C', 'D']
df = pd.DataFrame(lst)
print(df)

# Output
        0
0   	A
1     	B
2   	C
3      	D


# ----------------
# 3. From NumPy array
arr = np.array([[1,2,3],[4,5,6]])
df = pd.DataFrame(arr, columns=['X','Y','Z'])

# Output
   X  Y  Z
0  1  2  3
1  4  5  6


# ----------------
# 4. From dictionary
df = pd.DataFrame({'name':['aparna',85], 'marks':['dev',75]})
print(df)

# Output
   name	   marks
0  aparna  	85
1  dev		75

# ----------------
# 5. From list of dicts
df = pd.DataFrame([{'A':1,'B':2},{'A':5,'B':10}])

# ----------------
# 6. From CSV / Excel
df = pd.read_csv("data.csv")
df = pd.read_excel("data.xlsx", sheet_name="Sheet1")
Note- here "df" represent the DataFrame.
```
---
## Viewing Data in Pandas
```python
df.head(n) 		# Displays first n rows (default 5).

df.tail(n) 		# Displays last n rows (default 5).

df.shape 		# Returns dimension of DataFrame (rows, columns).

df.columns 		# Lists column names.

df.index 		# Shows index range.

df.info() 		# Summary of dataset (non-null count, datatypes, memory usage).

df.describe() 	# Statistical summary (mean, std, min, max, percentiles for numeric columns).

df.dtypes       # tells column datatypes
```
---
## Indexing & Selection
- **Indexing & Selection** are used to access, filter, or manipulate subsets of data.  
- There are two main types:  
  - **Label-based indexing (`.loc`)**  
  - **Index-based indexing (`.iloc`)**
### Example:
```python
# Column Selection
df['col']               # Select a single column
df[['col1','col2']]     # Select multiple columns (DataFrame).
colValue = df.col		# Attribute selection (not recommended if column name has spaces/special chars)

# Row Selection
df.iloc[0]				# First row by integer index.
df.iloc[0:5]			# First 5 rows (exclusive).

df.loc[2]               # Row with label/index = 2.
df.loc[2:5]             # Rows from label 2 to 5 (inclusive).
df.loc[[2,5,7]]			# Select multiple rows by label.

df.sample(5)			# Randomly select 5 rows.

# Conditional Filtering
df[df['Age'] > 20]

# Using query
df.query("col1 > 50 and col2 < 100")
df.query("city == 'Delhi'")
```
