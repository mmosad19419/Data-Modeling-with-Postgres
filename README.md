# Music Streaming App ETL and Transactional Data Modeling using PostgreSQL with Docker
## ETL pipeline - Data Modeling with Postgres - Udacity Data Engineering Nanodegree

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

create a Postgres database with tables designed to optimize queries on song play analysis, my role is to create a database schema and ETL pipeline for this analysis.


## Project Description
In this project, I'll complete data modeling with Postgres and build an ETL pipeline using Python.

### Tasks
- Define fact and dimension tables for a star schema for a particular analytic focus
- Write an ETL pipeline that transfers data from files in two local directories into these analytical database tables in Postgres using Python and SQL.

## DataSets
### Song Dataset
The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are file paths to two files in this dataset.

#### Example of song data files
        `song_data/A/B/C/TRABCEI128F424C983.json`
        `song_data/A/A/B/TRAABJL12903CDCF1A.json`

And below is an example of what a single song file, TRAABJL12903CDCF1A.json, looks like.

`{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}`


### Log Dataset
The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations.
The log files in the dataset you'll be working with are partitioned by year and month.

#### Example of log data files
        `log_data/2018/11/2018-11-12-events.json
         log_data/2018/11/2018-11-13-events.json`


## Schema for Song Play Analysis

### Fact Table
1. songplays - records in log data associated with song plays i.e. records with page `NextSong`
    - songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
2. users - users in the app
  - user_id, first_name, last_name, gender, level
3. songs - songs in music database
  - song_id, title, artist_id, year, duration
4. artists - artists in music database
  - artist_id, name, location, latitude, longitude
5. time - timestamps of records in songplays broken down into specific units
  - start_time, hour, day, week, month, year, weekday

![sparkifydb_erd](https://user-images.githubusercontent.com/80867381/214580187-78bda55c-c1ed-4296-8614-0dab5892df16.png)


## Steps
1. Build SQL queries <br>
- Create Tables queries
- Insert data into tables queries
- Drop tables queries

2. Develop ETL processes for each file <br>
- `etl.ipynb` notebook to develop ETL processes for each table. At the end of each table section, or at the end of the notebook, run test.ipynb to confirm that records were successfully inserted into each table.

3. Build complete ETL pipeline

4. test the result aginst defined queries


## How to run the Project
1. install requirements
2. Run create_tables.py
3. Run etl.py
4. test.ipynb to view and test the results.
