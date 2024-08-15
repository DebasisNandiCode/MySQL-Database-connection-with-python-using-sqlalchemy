# MySQL-Database-connection-with-python-using-sqlalchemy

import pandas as pd
import pymysql
from sqlalchemy import create_engine
import urllib.parse

username = 'xxxxxxxxx'
password = 'xxxxxxxxx'
password_encoded = urllib.parse.quote(password)
server = 'XX.XX.XX.XX'
port = xxxx
database = ''

conn_string = f'mysql+pymysql://{username}:{password_encoded}@{server}:{port}/{database}'

sql_query = ('select *'
            ' from Phone_cloud.call_files_New'
            ' limit 100;'
            )

engine = create_engine(conn_string)

df = pd.read_sql(sql_query, con=engine)

df
