# Pandas
Learning pandas: Loading data, cleaning data and performing basic functions. You can find different functions and sttributes used in pandas in the intro.ipynb file attached with the respective output they will give if performed on the given data.

(THE WORKING FOR EACH FUNCTION IS MENTIONED ALONGSIDE IT IN THE RESPECTIVE BLOCK) 

Dataset is taken form stack overflow
link for the used data set: https://survey.stackoverflow.co/2019

# To Read and Write data from different types of files

1. CSV format - To read data from a CSV file use method pd.read_csv('< loction of file >')
                To write data to CSV file use method < dataframe name >.to_csv('< Name the file >')
                Note: For a file for tab 'seperated values' change the extention to .tsv and add attribute  sep = '\t'
                (also for reading file)

2. Excel file - Install package using 'pip install xlwt openpyxl xlrd' (To read and write in Excel file)
                To read data from a Excel file use method pd.read_excel('< loction of file >')
                To write data to Excel file use method < dataframe name >.to_excel('< Name the file >')

3. JSON file -  To read data from a JSON file use method pd.read_json('< loction of file >')
                To write data to CSV file use method < dataframe name >.to_json('< Name the file >')
                Note: Include attribute orient = 'records', lines = True for proper format while writing to json files
                while reading from json files change the attributes as per the required values

4. SQL database - Install package using 'pip install SQLALchemy' (If you are working on SQLite then this is enough)
                  For POstgreSQL: install package 'pip install psycopg2-binary' also with the above mentioned one
                  For MySQL: Install package 'pip install mysqlconnector'also with the above mentioned one


### Proper implemnetation:

from sqlalchemy import create_engine  (for SQLite, PostgreSQL and MySQL)
import psycopg2                       (for PostgreSQL)
import mysqlconnector                 (for MySQL)


Now we will crete a connection string 
Note: Method to create connection d=string for different databases is different

### For MySQL

mysql_connection_string = 'mysql+mysqlconnector://username:password@host:port/database'
Note: Replace the values of username, pasword, port and database respective 

engine = create_engine(mysql_connection_string)


### For SQLite

sqlite_connection_string = 'sqlite:///path/to/database.db'
Note: Replace the values of path and database

engine = create_engine(sqlite_connection_string)

### For PostgreSQL

postgresql_connection_string = 'postgresql+psycopg2://username:password@host:port/database'
Note: Replace the values of username, pasword, port and database respective

engine = create_engine(postgresql_connection_string)

## Reading and Writing data to a SQL database

sql_df = pd.read_sql('table to which you want to read data from', engine)

sql_df = pd.read_sql_query('SQL query you want to run', engine)

'dataframe'.to_sql('table to which you want to add data', engine)
Note: If you want to rewrite, apppend or replace the data in /to the existing table use attribute if_exists='value'