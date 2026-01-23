# Pandas Reference

## Introduction

Pandas is the fundamental Python package for **data manipulation and analysis**. It provides powerful data structures such as **Series** and **DataFrame** objects for working with **tabular, time-series, and heterogeneous data**. This guide serves as a quick reference to the main features, processes, and functions of the Pandas package. As this is a quick reference guide, more in-depth information can be found on the official [Pandas Documentation](https://pandas.pydata.org/docs/) page.

### Guide Sections
- [Introduction](#introduction)
- [Installing Pandas](#installing-pandas)
- [Importing Pandas](#importing-pandas)

---

## Installing Pandas

You can install Pandas in your Python environment using the following command in a command line:

```bash
pip install pandas <optional_version>
```

To check the current version use

```bash
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

# DataFrame and Series Information
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