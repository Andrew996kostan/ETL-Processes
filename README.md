# postgres-data-modeling
### Udacity Data Engineer Nanodegree project
An imaginery startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis. The task is to create a star schema for Postgres and develop an ETL pipleine which will transfer the data from local files to the database.

### Requirements for running locally
- Python3 

### Project structure explanation
```
postgres-data-modeling
│   README.md                # Project description
│
└───data                     # The dataset
|   |               
│   └───log_data
│   |   │  ...
|   └───song_data
│       │  ...
│   
|                  
│   etl.ipynb        # ETL helper notebook
|   test.ipynb       # Psql queries notebook
│   create_tables.py # Schema creation script
|   etl.py           # ETL script
|   sql_queries.py   # Definition of all sql queries
```

### Instructions for running locally

Create python virtual environment
```
python3 -m venv venv             # create virtualenv
source venv/bin/activate         # activate virtualenv
pip install -r requirements.txt  # install requirements
```

Start postgres container
```
docker-compose up  # run this command in new terminal window or tab
```

Run scripts
```
cd src/
python scripts.create_tables  # create schema
python scripts.etl            # option 1: load data one file per commit
python scripts.etl_bulk       # option 2: bulk copy for each table
```

Check results

```
jupyter notebook  # launch jupyter notebook app

# The notebook interface will appear in a new browser window or tab.
# Navigate to src/notebooks/test.ipynb and run the code cells
```