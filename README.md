# DolphinDB Python API

## Environment Setup
Before Running the scripts, please have python packages numpy and pandas installed.

### Method 1:
Please download the 64bit python 3.6 version of anaconda, which contains python and all packages we need to run xxdb api python scripts
https://www.continuum.io/downloads


### Method 2:
Download and install the latest python 3.6.*
```bash
sudo easy_install pip
pip install numpy pandas
```

Then, please go to our python api folder and install the package through the following command:

- To install for the first time: `python setup.py install`

- To update the existing install: `python setup.py install --force`


## Usage

Assuming you have dolphindb SERVER running on port 8848, you can run the following commands in python console

```python
import dolphindb as ddb

# start a DolphinDB session
s = ddb.session() 

# connect to DolphinDB server
success = s.connect('localhost', 8848)

# or connect with login info
success = s.connect('localhost', 8848, "admin", "123456") 


if success:
    obj = s.run("Your XXDB script") # run dolphinDB script
    print(obj)
```

For more examples, please refer to python api tutorial:

The jupter notebook tutorial [here](tutorial.ipynb)

or

https://github.com/dolphindb/Tutorials_EN/blob/master/python_api.md

## Package Introduction
`session.py`: DolphinDB api for querying DolphinDB server  
`settings.py`: contain the data form and type definitions, and other settings  
`data_factory.py`: python data building factory based on returned DolphinDB object  
`socket_util.py`: python socket protocols  
`date_util.py`: converting integer into python datetime object  
`table.py`: manipulate DolphinDB SQL query through python class "Table".

