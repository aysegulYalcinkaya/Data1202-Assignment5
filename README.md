# DATA 1202-DATA ANALYSIS TOOLS ANALYTICS
## Assignment #4
Main objective of the assignment is creating functions to make the code modular in python.

In this assignment we defined 3 functions to make our code more modular. We also passed the number of
records, that we want to get, as a parameter to the function to make the function reusable for different
number of records.

For the first question, we got top 1000 records from the dataframe after reading youtube.csv file. Then we
calculated the channeltype distribution both for all records and top 1000 records. At the end we plot the
values in a bar chart.

For the second question, we saved the top 1000 rows into topresults.csv file. Then we imported this csv into
youtube table in data1202 schema.

In the Test section of the assignment we displayed the number of rows and columns of youtube.csv file
In addition, we displayed the number of rows and columns in youtube table and the first 5 rows of table data

## How to create a function
In Python a function is defined using the def keyword:
```python
def function_name(arguments):
  statement1
  statement2
  ...
  return [expression]
```
## Calling a function
To call a function, use the function name followed by parenthesis. Arguments are specified after the function name, inside the parentheses.
```python
result = function_name(arg1)
```
