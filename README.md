# DEND-Data-Modeling-with-Cassandra

(1) Process original event csv data files to create the data file csv that will be used for Apache Casssandra tables:
    Name of the file: event_datafile_new.csv
    Columns of the file: []
    Total Number of Rows: 8056
    Event data row sample:['Stephen Lynch', 'Logged In', 'Jayden', 'M', '0', 'Bell', '182.85669', 'free', 'Dallas-Fort Worth-Arlington, TX', 'PUT', 'NextSong', '1.54099E+12', '829', "Jim
                           Henson's Dead", '200', '1.54354E+12', '91']

(2) columns of event_datafile_new.csv
    artist
    firstName of user
    gender of user
    item number in session
    last name of user
    length of the song
    level (paid or free song)
    location of the user
    sessionId
    song title
    userId