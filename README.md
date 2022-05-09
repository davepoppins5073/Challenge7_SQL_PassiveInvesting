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
