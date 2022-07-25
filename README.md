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
## User Defined Functions
top_n function takes 2 arguments, dataframe and an integer value. This function gets the first N number of
rows from the given dataframe (df) and returns the Top N rows.

```python
def top_n(df,n):
  df_top_n=df.iloc[:n,:]
  return df_top_n
```
channeltype_distribution function takes 1 argument, dataframe and returns the channeltype distribution.
```python
def channeltype_distibution(df_top_n):
  distribution=df_top_n["channeltype"].value_counts()
  return distribution
```
load_top_n function takes 1 argument, dataframe. This function loads the records into "topresults.csv" file
with headers. In the next step it loads the data into "youtube" table. If "youtube" table
already exists, it is replaced.
```python
def load_top_n(df_top_n):
  # write top x data into csv file
  df_top_n.to_csv("topresults.csv",index=False)
  # load Top N rows into database
  try:
    engine=create_engine('mysql+pymysql://<user>:<password>@<host>/<schema>')
    df_top_n.to_sql("youtube",engine,if_exists='replace',index=False)
  except:
    print("Could not load data into database")
```
## User Defined Function Calls
First read data from youtube.csv
```python
df=pd.read_csv("youtube_dataset.csv")
```
### Call channeltype_distribution to calculate distribution for all records
```python
distribution_all=channeltype_distibution(df)
```
### Call top_n function with parameters df and 1000. (Top 1000 rows will be returned)
```python
df_top_1000=top_n(df,1000)
```
### Call channeltype_distribution function with parameter df_top_1000. (Distribution of top 1000 rows will be returned)
```python
distribution=channeltype_distibution(df_top_1000)
```
### Call load_top_X function with parameters df and 1000. (Top 1000 rows will be saved into csv file and imported into database)
```python
load_top_n(df_top_1000)
```
