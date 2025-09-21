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
```


print(pd.__version__)			# Show pandas version
```
