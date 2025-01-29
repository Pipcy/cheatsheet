# Python Cheatsheet for Programmers

This cheat sheet covers basic Python concepts relevant to data science and machine learning, as presented in the notebook.

[python official doc](https://docs.python.org/3/tutorial/index.html)

[MarkDown CheatSheet](https://www.markdownguide.org/extended-syntax/)

[More Markdown Stuff](https://www.markdownguide.org/extended-syntax/)

[Specific Python Examples](https://drive.google.com/file/d/1YEyE3o1yyZtMSB9Xb6gEdy7e1o4u38vt/view?usp=sharing)
## 1. Basic Data Structures

- **Lists**: Ordered, mutable collections of items.
   - Declaration: `my_list = [1, 2, 3]`
   - Append: `my_list.append(4)`
   - Remove: `my_list.remove(2)`
   - Indexing/Slicing: `my_list[0]`, `my_list[1:3]`, `my_list[-1]`
- **Dictionaries**: Unordered collections of key-value pairs. Keys are unique and immutable.
  - Declaration: `my_dict = {'key1': 'value1', 'key2': 'value2'}`
  - Accessing values: `my_dict['key1']`
  - Adding/Modifying: `my_dict['key3'] = 'value3'`
  - Deleting: `del my_dict['key2']`
  - Getting keys/values: `my_dict.keys()`, `my_dict.values()`
  
## 2. Loops
- **While loop**: Repeats a block of code as long as a condition is true.
  
```python
i = 0
    while i < 5:
        print(i)
        i += 1
```

- **For loop**: Iterates over a sequence (list, tuple, string, etc.).

```python
my_list = [1, 2, 3]
    for item in my_list:
        print(item)
```

- <mark>**Enumerate**</mark>: Get both index and value during iteration.
```python
for index, item in enumerate(my_list):
        print(index, item)
```

## 3. List Comprehension

Concise way to create lists.
```python
#Create a list of squares from 0 to 9
squares = [x**2 for x in range(10)]

#Create a list of even numbers from 0 to 9
evens = [x for x in range(10) if x % 2 == 0]
```

## 4. Modules/Libraries

- **Importing**: import module_name or import module_name as alias
- <mark>**Deep Copying**</mark>: Use deepcopy from the copy module to create independent copies of objects, preventing unintended changes to the original.
```python
from copy import deepcopy
    list2 = deepcopy(list1)
```


- **Numpy**: For numerical operations.
  - Creating arrays: `np.array([1, 2, 3])`, `np.zeros(5)`, `np.ones((2, 3))`
  - **Array operations**: `np.add()`, `np.subtract()`, `np.multiply()`, `np.divide()`, `np.matmul()`
  - Array attributes: `shape`, `ndim`, `size`
  - Indexing/Slicing: Similar to lists
  - Stacking: `np.vstack()`, `np.hstack()`
- **Pandas**: For data manipulation and analysis.
  - Reading data: `pd.read_csv('file.csv')`
  - Dataframe operations: `head()`, `tail()`, `describe()`, `groupby()`
- **Matplotlib**: For data visualization.
  - Creating plots: `plt.plot()`, `plt.scatter()`, `plt.bar()`
  - Customizing plots: `plt.xlabel()`, `plt.ylabel()`, `plt.title()`, `plt.legend()`
  
## 5. Markdown
- Use Markdown cells in Jupyter notebooks for text, headings, lists, and equations.
- In-line math: `$equation$`
- Displayed math: `$$equation$$` or using LaTeX environments.


