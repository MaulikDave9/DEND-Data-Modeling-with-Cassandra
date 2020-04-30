# DEND-Data-Modeling-with-Cassandra

Sparkify startup aims to analyze the song and user activity data on their new music streaming app.
Apache Cassandra database is created to support that goal where data modeling is done using Apache Cassandra based on given queries and ETL pipeline using Python.

## Dataset

Dataset is in the directory event_data, it has CSV files partitioned by date.
Example of files in the dataset:

    event_data/2018-11-01-events.csv
    event_data/2018-11-02-events.csv

## New CSV file for Apache Cassandra Tables
Processing the CSV files from the event_data directory, new CSV file was created as event_datafile_new.csv. This will be used
for Apache Cassandra tables.
   ![event datafile new Image](images/image_event_datafile_new.jpg)

## Tables

## To Run
1. Project_1B_Project_Template.ipynb - Jupyter notebook to execute the code