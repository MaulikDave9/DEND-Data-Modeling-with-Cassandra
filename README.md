# Data Modeling with Apache Cassandra

Sparkify startup aims to analyze the song and user activity data on their new music streaming app.
Apache Cassandra database is created to support that goal where data modeling is done using Apache Cassandra based on given queries and ETL pipeline using Python.

## Dataset

Dataset is in the directory *event_data*. It consists of CSV files partitioned by date.
Example of files in the dataset:

    event_data/2018-11-01-events.csv
    event_data/2018-11-02-events.csv

## New CSV file for Apache Cassandra Tables

Processing the CSV files from the *event_data* directory, new CSV file is created within the workspace directory: *event_datafile_new.csv*  
This new CSV file will be used for Apache Cassandra tables.  

The image below is how denormalized data should appear.  

   ![event datafile new Image](images/image_event_datafile_new.jpg)

## Tables based on given queries

Apache Cassandra the database tables are modeled based on the queries.

1. *Query Question*: Give the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4

   *Table*: artist_song_item_sessionid
   
        Column | Datatype
        -------|---------
        sessionId | int, 
        itemInSession | int, 
        artist | text, 
        song | text, 
        length | float
 
    *Primary Key*: (sessionId, itemInSession)
    
        sessionId is partition key and itemInSession cluster key.
        sessionId determines rows with particular id and itemInSession further sorts those rows for retrieval. 

2. *Query Question*: Give only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182

    *Table*: artist_song_for_user_by_session

        Column | Datatype
        -------|---------
        userId | int
        sessionId | int
        itemInSession | int
        artist | text
        song | text
        firstName | text
        lastName | text
        
     *Primary Key*:  ((userId, sessionId), itemInSession))
     
        (userId, sessionId) is partition key to find artists/song/user for given user id and session id 
        itemInSession is a Cluster key to sort those rows
 
3. *Query Question*: Give every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'

    *Table*: users_listened_song
    
        Column | Datatype
        -------|---------
        song | text
        userId | int
        firstName | text
        lastName | text
        
     *Primary Key*: song, userID
     
        song is partition key to find all rows with song title
        userID is clustering key to sort those rows by userID for retrieval

## To Run
1. Project_1B_Project_Template.ipynb - Jupyter notebook to execute the code