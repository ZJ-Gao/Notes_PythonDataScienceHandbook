# Introduction of Pandas
- Pandas build on top of NumPy
- Implementation of DataFrame
- DataFrame: <font color=red>**Multidimensional arrays** </font>
- More flexiable than NumPy
	1. Label
	2. work with missing data
- Data Structure: Series and DataFrame objects
# Data Indexing and Selection
## Data Selection in `Series`
Analogies: One-dimensional NumPy array; standard Python dictionary (mapping from a collection of keys to a collection of values)
### Series as one-dimentional arrary 
1. Slicing by explicit index
```
data['a':'c']
```
2. Slicing by implicit integer index
```
data[0:2]
```
3. masking
```
data[(data > 0.3) & (data < 0.8)]
```
4. fancy indexing
```
data[['a', 'e']]
```

### Indexers: loc, iloc, and ix
Slicing and indexing conventions can be a source of confusion

data[explicit index] % indexing

data[implicit index <font color=red>: </font> implicit index]  %slicing

1. `loc` indexing and slicing refer to the *explicit* index
2. `iloc` indexing and slicing refer to the *implicit* index

# Data Selection in DataFrame
Analogies:
1. Two dimensional array
2. A dictionary of `Series` structures sharing the same index

## DataFrame as a dictionary
```Python
area = pd.Series({'California': 423967, 'Texas':695662,'New York':141297, 'Florida':170312,'Illinois':149995})

pop = pd.Series({'California': 38332521, 'Texas': 26448193,'New York': 19651127,'Florida': 19552860,'Illinois': 12882135})

data = pd.DataFrame({'area':area, 'pop':pop})
```
The individual `Series` making up the **columns** of the `DataFrame` can be accessed via *dictionary-style* indexing of the **column name*

*Attribute-style column access* actually accesses the exact same object as the *dictionary-style access*:

```python
data.area is data['area']
```
PS: This is based on the column name won't be conflicted with methods of the `DataFrame`

This dictionary -style syntax can also be used to modify the object, like adding a new column:

```Python
data['density'] = data['pop'] / data['area']
```
## DataFrame as two-dimensianal array
`values` attribute
