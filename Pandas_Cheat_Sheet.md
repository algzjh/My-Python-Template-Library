[TOC]

# Pandas Cheat Sheet

## Series

`s = pd.Series(data, index=index)`

`s = pd.Series([1, 3, 5, np.nan, 6, 8])`

### iterate

`for (i, v) in s.items():`

`for (i, v) in s.iteritems():`

i stand for index, v stand for value

### length

`Series.size`

Return the number of elements in the underlying data.

### Selection by position

`s.iloc()`

## DataFrame

`df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list('ABCD'))`

## Viewing data

`df.head()`

`df.tail(3)`

`df.index`

`df.describe()`

Transpose: `df.T`

Sort:

 `df.sort_index(axis=1, ascending=False)`

`df.sort_values(by='B')`

## Selection

### Getting

`df['A']`

`df[0:3]`

`df['20130102':'20130104']`

### Selection by label

`df.loc[dates[0]]`

`df.loc[:, ['A', 'B']]`

`df.loc['20130102':'20130104', ['A', 'B']]`

`df.loc['20130102', ['A', 'B']]`

`df.at[dates[0], 'A']`

### Selection by position

`df.iloc[3]`

`df.iloc[3:5, 0:2]`

`df.iloc[[1, 2, 4], [0, 2]]`

`df.iloc[1:3, :]`

` df.iloc[:, 1:3]`

`df.iat[1, 1]`

### Boolean indexing

`df[df.A > 0]`

`df[df > 0]`

Using the `isin()` method for filtering

```python
df2 = df.copy()
df2['E'] = ['one', 'one', 'two', 'three', 'four', 'three']
df2[df2['E'].isin(['two', 'four'])]
```

### Setting

Setting a new column automatically aligns the data by the indexes.

`s1 = pd.Series([1, 2, 3, 4, 5, 6], index=pd.date_range('20130102', periods=6))`

`df['F'] = s1`

Setting values by label:

`df.at[dates[0], 'A'] = 0`

Setting values by position:

`df.iat[0, 1] = 0`

Setting by assigning with a NumPy array:

`df.loc[:, 'D'] = np.array([5] * len(df))`

### Iteration

`for index, row in df2.iterrows()`

index is the first row (maybe). When print it out, it will form a column

row is a series(have index and value)

when print row to the console, it will also form a column.

`for column in df2`

## Missing data

Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.

`df1 = df.reindex(index=dates[0:4], columns=list(df.columns) + ['E'])`

To drop any rows that have missing data.

`df1.dropna(how='any')`

Filling missing data.

`df1.fillna(value=5)`

To get the boolean mask where values are `nan`.

`pd.isna(df1)`

## Operation

### Stats

`df.mean()`

`df.mean(1)`

## CSV

`pd.read_csv('data.csv')`

print a part of the csv file

`print(df.iloc[0:5, 0:5])`

## Copy

Shallow copy

`deep = s.copy(deep=False)`

Deep copy

`deep = s.copy()`

When copying an object containing Python objects, a deep copy will copy the data, but will not do so recursively. Updating a nested data object will be reflected in the deep copy.



