Purpose of the project:
The major purpose of this project is to build a data model so that the company sparkify can analyze their data which is lying in their application. The data is present in json format with various information about the songs, users, artists. The firm does not have a database and tables from which it can query more information about songs. So, the purpose of this project is to build a database and create different tables and build a star schema with songplays as fact table and remaining tables as dimension table. The fact and dimension tables and their attributes as listed below. We need to create the tables first and then load data into these tables using scripts and make sure the data is being entered and is ready for reporting team to perform analytics and reporting features.

Fact Table
songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
Dimension Tables
users - users in the app
user_id, first_name, last_name, gender, level
songs - songs in music database
song_id, title, artist_id, year, duration
artists - artists in music database
artist_id, name, location, latitude, longitude
time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday
There are a total of 5 files in this project. They are sql_queries.py, create_tables.py, test.ipynb, etl.ipynb,etl.py.
The sql_queries.py contains statements to drop, create the tables and insert the values into these tables and the query which is required to build another table. The create_tables file contains code in the form of functions to create these respective tables. Always run sql_queries to create tables followed by create tables.py. The test file contains queries that we can use to check if the data is being inserted into the tables correctly. 
ETL process: The data in the tables songs and artists is taken from the song_data file. The required fields for the artists and songs table are selected and inserted. Similarly the remaining data required for other tables is extracted from the log_data file.
After All the data is extracted and inserted into the tables we run the etl.py and check the test.ipynb file to make sure all the records are executed correctly. 
3: Sample Queries with examples 
 
We can perform queries against this database to conduct data analysis and get the desired results
 
Sample query 1 : select distinct count(artist_id) as count, location from artists group by location order by count desc limit 3;
 
This query returns the top 3 locations from which the most number of artists belong to. There are 27 unknown location values and 2 artists from California, London.
 
Sample query 2: select distinct count(user_id) as count, location from songplays group by location order by count desc limit 5;
 
This query returns the top 5 locations from which the most number of users belongs to. There are 148 users from San Francisco, 77 from waterloo, 61 from Alabama.
 
 
 
 


References :

https://github.com/nareshk1290/Udacity-Data-Engineering/blob/master/Data-Modeling/Project%201/etl.ipynb