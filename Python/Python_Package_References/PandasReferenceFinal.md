# Pandas Reference

## Introduction

Pandas is the fundamental Python package for **data manipulation and analysis**. It provides powerful data structures such as **Series** and **DataFrame** objects for working with **tabular, time-series, and heterogeneous data**. This guide serves as a quick reference to the main features, processes, and functions of the Pandas package. As this is a quick reference guide, more in-depth information can be found on the official [Pandas Documentation](https://pandas.pydata.org/docs/) page.

### Guide Sections
- [Introduction](#introduction)
- [Installing Pandas](#installing-pandas)
- [Importing Pandas](#importing-pandas)
- [Pandas Objects and Their Creation](#pandas-objects-and-their-creation)
- [Importing and Exporting Data](#importing-and-exporting-data)
- [DataFrame and Series Information](#dataframe-and-series-information)
- [Selection, Indexing and Filtering](#selection-indexing-and-filtering)
- [Modifying Series or DataFrame](#modifying-series-or-dataframe)
- [Data Cleaning](#data-cleaniing)
- [Statistics, Aggregation and Grouping](#statistics-aggregation-and-grouping)
- [Categorial Data](#categorial-data)
- [Time Series Analysis](#time-series-analysis)

---

## Installing Pandas

You can install Pandas in your Python environment using the following command in a command line:

```bash
pip install pandas <optional_version>
```

To check the current version use

```bashupa
pip show pandas
```

---

## Importing Pandas

The standard convention to import Pandas into a python file is:

```python
import pandas as pd
```

---

## Pandas Objects and Their Creation

### Series
A Series is a one-dimensional labeled array capable of holding any single data type (numbers, strings, etc.). It has an index to label each element, which can be numeric, string, or date/time. Creating a Series:
```python
data = [<data_1>, ..., <data_n>]     # Initialize data
index = [<index_1>, ..., <index_n>]  # Initialize indices
s = pd.Series(data, index=index)     # Initialize Series
```

### Dataframe
A DataFrame is a two-dimensional labeled data structure with rows and columns, like a table or spreadsheet. Columns can have different data types. Creating a DataFrame:
```python 
data = {
    <column_name_1>: [<column_1_data>],     # Initialize data
    ...,
    <column_name_n>: [<column_n_data>]
}

index = [<row_1>, ..., <row_n>]             # Initialize indices

df = pd.DataFrame(data, index=index)        # Initialize DataFrame
```
---

## Importing and Exporting Data

### Importing Data

```python
df = pd.read_csv(<file.csv>)                # Import data from a CSV file: Additional argument sep=<delimiter> to specify special delimiter
df = pd.read_excel(<file.xlsx>)             # Import data from an Excel file: Additional argument sheet_name=<sheet_name> to specify sheet
df = pd.read_sql(<query>, <connection>)     # Import data from a SQL query
df = pd.read_json(<file.json>)              # Import data from a JSON file
```

### Exporting Data
```python
df.to_csv(<file.csv>, index=False)              # Export DataFrame to a csv file: Argument index=False does not write the index to the file
df.to_excel(<file.xlsx>, index=False)           # Export DataFrame to a excel file: Argument index=False does not write the index to the file
df.to_sql(<table>, <connection>, index=False)   # Export DataFrame to a sql file: Argument index=False does not write the index to the file
df.to_json(<file.json>)                         # Export DataFrame to a JSON file
```
---

## DataFrame and Series Information
```python
df.head()       # View first 5 rows
df.tail()       # View last 5 rows
df.shape        # Get (rows, columns)
df.info()       # View data types and non-null counts
df.describe()   # Get summary statistics for numeric columns
df.columns      # Get column names
df.index        # Get row indices
```

---

## Selection, Indexing and Filtering

### Standard Selection and Indexing
```python
# Selecting columns
column = df[<column_name>]                      # Select single column as Series
columns = df[[<column_1>, <column_2>]]          # Select multiple columns as DataFrame

# Select rows
row = df.loc[<row_label>]                       # Select row by label/index
cell = df.loc[<row_label>, <column_name>]       # Select specific cell by label

# Interger indexing
row_pos = df.iloc[<row_index>]                  # Select row by integer position
cell_pos = df.iloc[<row_index>, <col_index>]    # Select specific cell by position
```

### Filtering and Conditional Selection
```python
filtered_df = df[<conditional_expression>]      # Filter rows based on condition(s), e.g. df[<column_name>] <value>, & (and), | (or)
```

---

## Modifying Series or DataFrame

### Single Series or DataFrame Manipulation
```python
# Adding new columns
modified_df = df[<new_column>] = <expression_or_value_or_list>   # Create a new column based on an expression, single value, or list
modified_df = df[<new_column>].apply(f)                          # Create a new column based on an defined function on existing data columns
modified_df = df[<new_column>].apply(lambda x: <function>)       # Create a new column based on an lambda function on exisiting data columns

# Modifying existing columns
modified_df = df[<column_name>] = <expression_or_value_or_list>  # Updates an existing column based on an expression, single value, or list
modified_df = df[<column_name>].apply(f)                         # Updates a new column based on an defined function on existing data columns
modified_df = df[<column_name>].apply(lambda x: <function>)      # Updates a new column based on an lambda function on existing data columns

# Modifying a specific value
modified_df = df.loc[<row_label>, <column_name>] = <new_value>   # Change value at specific row (label) and column
modified_df = df.iloc[<row_index>, <col_index>] = <new_value>    # Change value by integer positions

# Dropping rows or columns
modified_df = df.drop(<column_or_row>, axis=<0_or_1>)             # Drop a row (axis=0) or column (axis=1)

# Renaming columns or index
modified_df = df.rename(columns={<old>: <new>})                  # Rename columns
modified_df = df.rename(index={<old>: <new>})                    # Rename row labels

# Sorting data
modified_df = df.sort_values(by=<column_name>, ascending=<True_or_False>)    # Sort by column
modified_df = df.sort_index(ascending=<True_or_False>)                       # Sort by index

# Note: Assigning to a variable returns a new DataFrame; df itself is unchanged unless inplace=True is used which then variable can be removed
```

### Combining DataFrames
```python
# Concatenation
df_combined = pd.concat([df1, df2], axis=<0_or_1>)                      # Combine DataFrames vertically (axis=0) or horizontally (axis=1)

# Merging / Joining
df_merged = pd.merge(df1, df2, on=<column_name>, how=<inner_or_outer>)  # Merge on column with inner/outer join
```

---

## Data Cleaniing
```python
# Detect missing values
missing_df = df.isnull()                        # Returns a DataFrame of True/False indicating missing values
not_missing_df = df.notnull()                   # Returns a DataFrame of True/False indicating filled values

# Drop missing values
clean_df = df.dropna()                          # Drop any row with at least one missing value (drops samples with missing data variables)
clean_df = df.dropna(axis=1)                    # Drop columns with at least one missing value (drops a data variable)
clean_df = df.dropna(subset=[<col1>, <col2>])   # Drop rows if specific columns are missing (drops samples if specific data variables are missing)

# Fill missing values
filled_df = df.fillna(<value>)                  # Replace all missing values with a specified value: df can be replaced with df[<column>] to specify columns
filled_df = df.fillna(method='ffill')           # Forward fill: fill missing with previous row value: df can be replaced with df[<column>] to specify columns
filled_df = df.fillna(method='bfill')           # Backward fill: fill missing with next row value: df can be replaced with df[<column>] to specify columns

# Replace values
replaced_df = df.replace(<old_value>, <new_value>)                  # Replace specific values: df can be replaced with df[<column>] to specify columns
replaced_df = df.replace({<col1>: <new_val1>, <col2>: <new_val2>})  # Replace values in specific columns

# Removing duplicates
unique_df = df.drop_duplicates()                                       # Remove rows that are exact duplicates (drops duplicate samples)
unique_df = df.drop_duplicates(subset=[<col1>, <col2>], keep='first')  # Remove duplicates based on specific columns (drops duplicates if a specific data variable is the sawe)

# Note: Assigning to a variable returns a new DataFrame; df itself is unchanged unless inplace=True is used, in which case the variable can be omitted.
```
---

## Statistics, Aggregation and Grouping

### Summary Statistics
```python
mean_val = df[<column>].mean()               # Mean of a column
median_val = df[<column>].median()           # Median of a column
std_val = df[<column>].std()                 # Standard deviation of a column
var_val = df[<column>].var()                 # Variance of a column
min_val = df[<column>].min()                 # Minimum value of a column
max_val = df[<column>].max()                 # Maximum value of a column
sum_val = df[<column>].sum()                 # Sum of values of a column
count_val = df[<column>].count()             # Number of non-missing entries (can use on .isnull to get number of missing values)
```

### Cumulative operations
```python
cumsum_val = df[<column>].cumsum()          # Cumulative sum of the column
cumprod_val = df[<column>].cumprod()        # Cumulative product of the column
cummax_val = df[<column>].cummax()          # Cumulative maximum
cummin_val = df[<column>].cummin()          # Cumulative minimum

#Note: Returns a Series of the same length as the original column
```
### Correlation and covariance
```python
corr_df = df.corr()                          # Pairwise correlation of numeric columns
cov_df = df.cov()                            # Pairwise covariance of numeric columns
```

### Aggregation
```python
agg_df = df.agg({<column1>: ['sum','mean'], <column2>: ['min','max']})      # Aggregate with multiple functions for multiple columns
```

### Grouping
```python
grouped = df.groupby(<column>)                                              # Group by a column
group_summary = grouped[<column_to_aggregate>].agg(['sum','mean','count'])  # Apply aggregation after grouping
```
---

## Categorial Data
```python
### Categorical Data

# Creating categorical columns
df['Category'] = pd.Categorical(['High', 'Medium', 'Low', 'Medium', 'High'])
# You can also specify the category order
df['Category'] = pd.Categorical(df['Category'], categories=['Low','Medium','High'], ordered=True)

# Converting existing columns to categorical
df['Category'] = df['Category'].astype('category')

# Viewing category information
df['Category'].cat.categories        # Get the list of categories
df['Category'].cat.ordered           # Check if the categories are ordered
df['Category'].cat.codes             # Get integer codes for the categories

# Changing categories
df['Category'] = df['Category'].cat.rename_categories({'Low':'L', 'Medium':'M', 'High':'H'})  # Rename categories
df['Category'] = df['Category'].cat.add_categories(['Very High'])   # Add new category
df['Category'] = df['Category'].cat.remove_categories(['M'])       # Remove a category

# Reordering categories
df['Category'] = df['Category'].cat.reorder_categories(['L','M','H','Very High'], ordered=True)

# Sorting by categorical column
df_sorted = df.sort_values('Category')  # Uses the order if ordered=True

# Aggregating by categorical data
df.groupby('Category')['SomeNumericColumn'].mean()   # Mean of numeric values per category

# Converting categories to dummy/indicator variables (for ML)
dummies = pd.get_dummies(df['Category'], prefix='Cat')  # One-hot encoding
df = pd.concat([df, dummies], axis=1)

```

---

### Time Series Analysis