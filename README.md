# Challenge7_SQL_PassiveInvesting


## Requirements/ Installations
The requirement.txt file in this repository contain all the packages you'll need in your conding env. Please make sure to install if you do not have them already. While you could use the package manager [pip](https://pip.pypa.io/en/stable/) to install these individually please make use of the requirement text in the repo.

### pip install for Requirements
```bash
python -m pip install -r requirements.txt
```

### Imports
```python
# Importing the required libraries and dependencies
import numpy as np
import pandas as pd
import hvplot.pandas
import sqlalchemy
from sqlalchemy import inspect
```

## FUNCTIONS
```python
def query_to_dataframe(query=str,table=str):
    
    """
    This function takes query strings and keeps all the SQL Hidden away from the end user.
    it should return the dataframes necessary
    """
```

```python
def about_this_dataframe(df=pd.DataFrame()):
    
    """
    This function give some information about a dataframe that is passed in
    """
    
    row_cols = df.shape
```

```python
def daily_returns(df=pd.DataFrame()):
    
    # Daily Returns
    # Formatting: 
    #     1. DateTime to Date, 2. Column Rename, 3. Setting Date as an Index, 4.Dropping Unnecessary columns, 
    #     5. Multiplying the daily Return by 100. Better and more visually appealing I feel to look at percentages than small numbers
```

```python
def daily_returns(df=pd.DataFrame()):
    
    # Daily Returns
    # Formatting: 
    #     1. DateTime to Date, 2. Column Rename, 3. Setting Date as an Index, 4.Dropping Unnecessary columns, 
    #     5. Multiplying the daily Return by 100. Better and more visually appealing I feel to look at percentages than small numbers
```

```python
def cumulative_returns(df=pd.DataFrame()):
    
    
    # Cumulative Returns
    df["cmltv_rtrns"] =(1 + df["daily_returns"]).cumprod()

```

## Code
Ive gone to lengths to comment the code, as well as layout why i created the functions I did. So far throughout this repo I havea. collections of function I may pull together into an operation package. The idea behind each of those function is to hve function  ready in case I need to for example calculate the cumulative returns, or the daily returns I can call it. There are many nuance cases so as I continue onwards working on this and building it out the functions will grow in complexity. 

One thing I tried to focus on was the use of f-strings and parameters. This ios very powerful as it allows  a function to take parameters in order to execute a SQL Statement from many places. 

For Example:
```python
# Write a SQL query to SELECT all of the data from the PYPL table
# Variables: 1) the table we will query 2) the query
table = "PYPL"
query = f"""
SELECT * from {table}
"""

# Function call 1: (query_to_dataframe) to get me my df
# Function call 2: (about_this_dataframe) to get me info about my df
pypl_dataframe = query_to_dataframe(query,table)
```
I enjoying using f-strings, as they allow dynamic and complex queries to be built.

## Coding Philosophy w/ SQL and Python
While I can code some complex structures like cursors in sequel and leverage a lot of clunky  methods and techniques to work with the data housed within a database, it has always been my opinion that there are more tools for data manipulation in python.  I tend to craft a query that isnt a `SELECT *` for performance issues and because the DBA's tend to be high strung with a propensity towards yelling and passive aggressiveness. Then I use python to manipulate the data set how I need it to be. Depending on the data I might after saving to an ionitial dataframe save it to a pickle file so I can always get back to the original data set if need be. Just my two cents though
