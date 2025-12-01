Sparkify Data Warehouse Project

Udacity Data Engineering Nanodegree — Data Warehouse (AWS Redshift & S3)

This project builds a cloud data warehouse for Sparkify, a music streaming startup.
Their data lives as JSON logs in Amazon S3, and the goal is to build an ETL pipeline in Python that loads this data into Amazon Redshift using a star schema optimized for analytics.

📌 Project Overview

Sparkify wants to understand what songs users listen to and analyze user behavior over time.
However, their raw data is stored in S3 as JSON files:

Log data: user activity logs

Song data: song and artist metadata

This project builds:

Two staging tables to temporarily store raw JSON from S3

A star schema with one fact table and four dimension tables

A complete ETL pipeline to automate loading and transforming the data
Data Warehouse Schema (Star Schema)
⭐ Fact Table

songplays
Contains all user song play events.

Column	Description
songplay_id	Primary key
start_time	Timestamp of song play
user_id	User who played the song
level	Free/Paid
song_id	Song identifier
artist_id	Artist identifier
session_id	Session number
location	User location
user_agent	Browser / device info
⭐ Dimension Tables
users

User information (user_id, first_name, last_name, gender, level)

songs

Song metadata (song_id, title, artist_id, year, duration)

artists

Artist metadata (artist_id, name, location, latitude, longitude)

time

Timestamp breakdown (hour, day, week, month, year, weekday)

🧰 Files in This Repository
File	Description
create_tables.py	Drops and creates all tables in Redshift
sql_queries.py	Contains all SQL queries used for DROP, CREATE, COPY, and INSERT
etl.py	Main ETL pipeline that loads data from S3 to Redshift
dwh.cfg	Configuration file containing Redshift endpoint, DB details, and IAM role
README.md	This file
