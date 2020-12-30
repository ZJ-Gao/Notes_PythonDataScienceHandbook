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

#### `loc` indexing and slicing refer to the *explicit* index
