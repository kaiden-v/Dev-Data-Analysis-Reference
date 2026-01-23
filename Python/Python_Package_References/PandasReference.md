

## 🎯 Accessing & Filtering Data

### 📎 Basic Access

```python
df['Age']                  # Single column
df[['Name', 'Age']]        # Multiple columns
df.iloc[0]                 # First row by position
df.loc[0]                  # First row by label
```

### 🧪 Conditional Filtering (Boolean masks)

```python
df[df['Age'] > 30]                          # Age over 30
df[df['Country'] == 'USA']                 # Country match
df[(df['Age'] > 25) & (df['Country'] == 'UK')]  # Multiple conditions
```

### 🎯 Advanced Filtering

```python
df[df['Name'].str.startswith('A')]         # Names starting with A
df[df['Country'].isin(['USA', 'UK'])]      # Match multiple values
df[~df['Country'].isin(['Canada'])]        # NOT condition
```

---

## 🔁 CRUD Operations in Pandas

### ✅ Create (Insert Rows)

```python
new_row = pd.DataFrame([{'Name': 'Diana', 'Age': 28, 'Country': 'Germany'}])
df = pd.concat([df, new_row], ignore_index=True)
```

### 🕵️ Read (Access Data)

```python
df.loc[df['Name'] == 'Alice']
df.iloc[2]
```

### ✏️ Update (Modify Values)

```python
df.loc[df['Name'] == 'Bob', 'Age'] = 31             # Update Bob's age
df['Country'] = df['Country'].str.upper()           # Convert all country names to uppercase
```

### ❌ Delete (Drop Data)

```python
df = df.drop(2, axis=0)                             # Drop row with index 2
df = df[df['Name'] != 'Alice']                      # Drop rows where name == Alice
df = df.drop('Age', axis=1)                         # Drop 'Age' column
```

---

## 🧹 Cleaning Data

```python
df.isnull().sum()                          # Count missing values
df.dropna(inplace=True)                   # Drop rows with missing values
df.fillna({'Age': 0}, inplace=True)       # Fill missing Age values with 0
df.rename(columns={'Age': 'Years'}, inplace=True)   # Rename column
df['Years'] = df['Years'].astype(float)   # Convert column to float
```

---

## 📊 Analyzing Data

```python
df['Country'].value_counts()                       # Count occurrences
df.groupby('Country')['Age'].mean()                # Average age per country
df.sort_values(by='Age', ascending=False)          # Sort by Age descending
```

---

## 💾 Saving Data

```python
df.to_csv('cleaned_data.csv', index=False)
df.to_excel('output.xlsx', index=False)
```