# DATA ACQUISITION

# 1. Identify Data Sources
# Define the sources of your data. 
# This could be files (e.g., CSV, Excel), databases (e.g., SQL, NoSQL), APIs, web scraping, etc.

# 2. Access the Data
# If your data source is an API:
'''
import requests
response = requests.get('API_endpoint')
data = response.json()
'''
# If your data source is a SQL database:
'''
import psycopg2
connection = psycopg2.connect(database='dbname', user='username', password='password', host='hostname', port='portnumber')
cursor = connection.cursor()
cursor.execute('SQL query')
data = cursor.fetchall()
'''
# If your data source is a NoSQL database like MongoDB:
'''
from pymongo import MongoClient
client = MongoClient('mongodb_uri')
db = client['db_name']
collection = db['collection_name']
data = collection.find(query)
'''
# If your data source is a CSV file:
'''
import pandas as pd
data = pd.read_csv('filename.csv')
'''
# 3. Download and Import the Data
# Depending on the size and format of the data, you might need to download it and import it into your local system or cloud storage.

# 4. Store the Data in an Appropriate Format/Database
# Depending on the nature of your project and the volume of data, you might want to store your data in a particular format or database for easy access and processing. This could be a SQL database, a NoSQL database, a CSV file, a JSON file, etc.
'''
# Saving data to a CSV file
data.to_csv('filename.csv', index=False)

# Saving data to a SQL database
from sqlalchemy import create_engine
engine = create_engine('postgresql://username:password@localhost:5432/dbname')
data.to_sql('tablename', engine, if_exists='replace')

# Saving data to a NoSQL database like MongoDB
collection.insert_many(data.to_dict('records'))
'''
