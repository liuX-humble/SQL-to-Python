# SQL-to-Python
SQL to Python Quickstart Guide

Quick reference for translating SQL queries to Pandas operations.

## Live Preview

[View Guide](https://htmlpreview.github.io/?https://raw.githubusercontent.com/YOUR-USERNAME/REPO-NAME/main/sql-to-python.html)

## Contents

| Operation | SQL | Python (Pandas) |
|-----------|-----|-----------------|
| Filtering rows | `SELECT * FROM table WHERE column = 'value'` | `df[df['column'] == 'value']` |
| Sorting data | `SELECT * FROM table ORDER BY column ASC` | `df.sort_values(by='column', ascending=True)` |
| Removing duplicates | `SELECT DISTINCT col1, col2 FROM table` | `df.drop_duplicates(subset=['col1', 'col2'])` |
| Filling missing values | `SELECT COALESCE(col, 'xxx') FROM table` | `df['column'].fillna('xxx')` |
| Changing data types | `SELECT CAST(col AS INTEGER) FROM table` | `df['column'].astype(int)` |
| Renaming columns | `SELECT col AS new_col FROM table` | `df.rename(columns={'col': 'new_col'})` |
| Summing values | `SELECT SUM(column) FROM table` | `df['column'].sum()` |
| Calculating average | `SELECT AVG(column) FROM table` | `df['column'].mean()` |
| Finding min/max | `SELECT MIN(column) FROM table` | `df['column'].min()` / `df['column'].max()` |
| Counting rows | `SELECT COUNT(column) FROM table` | `df['column'].count()` |
| Calculating percentiles | `SELECT PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY col) FROM table` | `df['column'].quantile(0.5)` |
| Aggregating by groups | `SELECT group_column, AVG(col) FROM table GROUP BY group_column` | `df.groupby('group_column')['col'].mean()` |
| Merging datasets | `SELECT * FROM table1 JOIN table2 ON table1.key = table2.key` | `pd.merge(table1, table2, on='key')` |
| Appending datasets | `SELECT * FROM table1 UNION ALL SELECT * FROM table2` | `pd.concat([table1, table2])` |

## Key Differences

| SQL | Pandas |
|-----|--------|
| Tables | DataFrames (`df`) |
| Columns | `df['column']` with quotes |
| Rows | Index |
| NULL | `NaN` |

## Usage

1. Open the [live preview](https://htmlpreview.github.io/?https://raw.githubusercontent.com/YOUR-USERNAME/REPO-NAME/main/sql-to-python.html)
2. Find your SQL operation in the table
3. Copy the equivalent Pandas code
4. Print → Save as PDF for offline reference

## Note

This guide assumes:
- `import pandas as pd` is executed
- Data is loaded into a DataFrame called `df`

## Credits

Based on common SQL-to-Pandas translation patterns.

## License

Reference material for educational purposes.
