# USER DEFINED FUNCTIONS IN PYTHON

A function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing. Besides Python built-in functions, we can also define our own functions. These are called user-defined functions.

We defined 3 functions in this sample to make our code more modular. We also passed the number of
records, that we want to get, as a parameter to the function to make the function reusable for different
number of records.

### How to create a function
In Python a function is defined using the def keyword:
```python
def function_name(arguments):
  statement1
  statement2
  ...
  return [expression]
```
### Calling a function
To call a function, use the function name followed by parenthesis. Arguments are specified after the function name, inside the parentheses.
```python
result = function_name(arg1)
```
## Getting Started

### Prerequisites
* Python 3.9
* Pandas
* sqlalchemy
* pymysql
* matplotlib
* MySQL Database

### Installing

For Anaconda installation refer to [Anaconda web page](https://www.anaconda.com/).
The Anaconda distribution of Python comes with Matplotlib and Pandas pre-installed and no further installation steps are necessary.

Install sqlalchemy
```
pip install SQLAlchemy
```
Install pymysql
```
pip install PyMySQL
```

## Running the Tests

TEST section shows that top 1000 records are saved into topresults.csv and imported into database youtube table.

### Get content of topresults.csv in order to see if it is loaded

topresults.csv file is read and information about the data is displayed. Result should be (1000,20)

### Connect to database and select data from youtube table

Connection to MySql database is established and youtube table data is queried in this test. As a result number of records and columns will be displayed. Result should be "Number of records and columns in youtube table  (1000, 20)" and top 5 rows of db table.

## Deployment

Set the database user, password, host and schema fields.

## Built With
* Jupyter Notebook

## Author 
Aysegul Yalcinkaya
