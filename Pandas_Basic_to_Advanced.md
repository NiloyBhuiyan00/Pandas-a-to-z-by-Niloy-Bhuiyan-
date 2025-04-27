```markdown
# Pandas basic to advance by Niloy Bhuiyan

### 1. **Creating Data Structures**

#### Creating a Series
import pandas as pd

# Creating a Series
s = pd.Series([10, 20, 30, 40])
print(s)
```
- A **Series** is a one-dimensional labeled array in Pandas.
- It can hold any data type (integers, strings, etc.).

#### Creating a DataFrame
```python
# Creating a DataFrame
df = pd.DataFrame({
    'Name': ['Niloy', 'Rifat', 'Sami'],
    'Age': [23, 25, 22]
})
print(df)
```
- A **DataFrame** is a two-dimensional table (like a database table) in Pandas.
- It can hold data of different types across columns.

---

### 2. **Data Read/Write**

#### Reading a CSV file
```python
# Reading a CSV file
df = pd.read_csv('data.csv')
print(df)
```
- **`read_csv()`** loads data from a CSV file into a DataFrame.

#### Writing to a CSV file
```python
# Writing data to a CSV file
df.to_csv('output.csv', index=False)
```
- **`to_csv()`** saves the DataFrame to a CSV file.

---

### 3. **Data Selection & Indexing**

#### Selecting a Column
```python
# Selecting a column
print(df['Name'])
```
- Accessing a column by its name.

#### Using `loc` for Label-based Indexing
```python
# Using loc for label-based indexing
print(df.loc[0])
```
- **`loc[]`** selects data by label (row index).

#### Using `iloc` for Position-based Indexing
```python
# Using iloc for position-based indexing
print(df.iloc[1])
```
- **`iloc[]`** selects data by integer position (row index).

---

### 4. **Data Filtering**

#### Simple Filtering
```python
# Filter rows based on a condition
adults = df[df['Age'] > 23]
print(adults)
```
- Filters rows where the `Age` column is greater than 23.

#### Complex Filtering
```python
# Filter with multiple conditions
filtered = df[(df['Age'] > 20) & (df['Name'] == 'Niloy')]
print(filtered)
```
- Filters rows with multiple conditions using `&` (AND) or `|` (OR).

---

### 5. **Data Cleaning**

#### Checking for Null Values
```python
# Checking for null values
print(df.isnull())
```
- **`isnull()`** checks for null (missing) values in the DataFrame.

#### Dropping Null Values
```python
# Dropping rows with missing values
cleaned_df = df.dropna()
print(cleaned_df)
```
- **`dropna()`** removes rows with null values.

#### Filling Null Values
```python
# Filling missing values with a default value
filled_df = df.fillna('Unknown')
print(filled_df)
```
- **`fillna()`** replaces null values with a specified value.

#### Dropping Duplicate Rows
```python
# Dropping duplicate rows
df = df.drop_duplicates()
print(df)
```
- **`drop_duplicates()`** removes duplicate rows.

#### Changing Data Types
```python
# Changing the data type of a column
df['Age'] = df['Age'].astype(float)
print(df.dtypes)
```
- **`astype()`** changes the data type of a column.

---

### 6. **Data Manipulation**

#### Adding a New Column
```python
# Adding a new column to the DataFrame
df['Country'] = ['Bangladesh', 'Bangladesh', 'Bangladesh']
print(df)
```
- Adds a new column called `Country`.

#### Dropping a Column
```python
# Dropping a column
df = df.drop('Country', axis=1)
print(df)
```
- **`drop()`** removes a specified column (`axis=1` refers to columns).

#### Merging DataFrames
```python
# Merging two DataFrames
df1 = pd.DataFrame({'ID': [1, 2], 'Name': ['Niloy', 'Rifat']})
df2 = pd.DataFrame({'ID': [1, 2], 'Age': [23, 25]})
merged = pd.merge(df1, df2, on='ID')
print(merged)
```
- **`merge()`** combines two DataFrames based on a common column (here, `ID`).

#### Concatenating DataFrames
```python
# Concatenating two DataFrames along columns
df3 = pd.concat([df1, df2], axis=1)
print(df3)
```
- **`concat()`** combines DataFrames along a specified axis.

#### Grouping Data
```python
# Grouping data and calculating mean of the 'Age' column
grouped = df.groupby('Name')['Age'].mean()
print(grouped)
```
- **`groupby()`** groups the data by the `Name` column and calculates the mean of the `Age`.

#### Pivot Table
```python
# Creating a pivot table
pivoted = df.pivot_table(values='Age', index='Name')
print(pivoted)
```
- **`pivot_table()`** creates a pivot table with the specified values and index.

---

### 7. **Data Aggregation**

#### Aggregate Functions
```python
# Using aggregate functions on the 'Age' column
print(df['Age'].sum())   # Sum
print(df['Age'].mean())  # Mean
print(df['Age'].min())   # Minimum
print(df['Age'].max())   # Maximum
```
- Aggregate functions like **sum()**, **mean()**, **min()**, and **max()** provide summary statistics.

---

### 8. **Data Visualization (Pandas)**

#### Line Plot
```python
# Plotting a line graph of the 'Age' column
df['Age'].plot(kind='line')
```
- **`plot(kind='line')`** creates a line plot.

#### Histogram
```python
# Plotting a histogram of the 'Age' column
df['Age'].hist()
```
- **`hist()`** creates a histogram to visualize the distribution of data.

#### Boxplot
```python
# Creating a boxplot for the 'Age' column
df.boxplot(column=['Age'])
```
- **`boxplot()`** generates a box plot for visualizing the distribution and outliers.

---

This is a comprehensive overview of the core functionality of Pandas, which is an essential library for data analysis in Python.
```
