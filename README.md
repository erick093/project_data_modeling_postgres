# Data Engineering - Data Modeling with PostgreSQL

## Contents
1. [**Introduction**](#introduction)
2. [**Data Model**](#data-model)
3. [**ETL Processes**](#etl-processes)
4. [**Execution**](#execution)
5. [**Conclusion**](#conclusion)
6. [**References**](#references)
7. [**Acknowledgements**](#acknowledgements)
8. [**License**](#license)
9. [**Author**](#author)

## Introduction
This is the project for the course of data modeling with PostgreSQL. 
The course is designed to teach the fundamentals of data modeling with PostgreSQL. 
The goal of the project is to construct a data model and ETL processes for a fictional company called 
[**Sparkify**](https://www.udacity.com/).

## Data Model
The data model for Sparkify is as follows: 
* **Factual tables**: 
  * **Songplays**: A table that contains information about the song plays.
* **Dimension Tables**:
  * **Songs**: A table that contains information about the songs.
  * **Artists**: A table that contains information about the artists.
  * **Users**: A table that contains information about the users.
  * **Time**: A table that contains information about the time.

Below is the data model for the Sparkify database.
  

    +------------------+
    | Artists          |
    +------------------+
    | artist_id        | varchar(255) | NOT NULL | PRIMARY KEY | 
    | artist_latitude  | float        | 
    | artist_location  | varchar(255) | 
    | artist_longitude | float        | 
    | artist_name      | varchar(255) | NOT NULL | 
    +------------------+

    +------------------+
    | Songs            |
    +------------------+
    | song_id          | varchar(255) | NOT NULL | PRIMARY KEY | 
    | title            | varchar(500) | NOT NULL | 
    | duration         | float        | 
    | year             | int          | 
    | artist_id        | varchar(255) | NOT NULL | 
    +------------------+

    +------------------+
    | Users            |
    +------------------+
    | user_id          | int          | NOT NULL | PRIMARY KEY | 
    | first_name       | varchar(255) |
    | last_name        | varchar(255) | 
    | gender           | varchar(50)  |
    | level            | varchar(50)  |
    +------------------+

    +------------------+
    | Time             |
    +------------------+
    | start_time       | timestamp   | NOT NULL | PRIMARY KEY | 
    | hour             | int         |            
    | day              | int         |                             
    | week             | int         |                                              
    | month            | int         |
    | year             | int         |
    | weekday          | int         |
    +------------------+

    +------------------+
    | Songplays        |    
    +------------------+
    | songplay_id      | serial       | NOT NULL | PRIMARY KEY | 
    | start_time       | timestamp    | NOT NULL | 
    | user_id          | int          | NOT NULL | 
    | level            | varchar(50)  | 
    | song_id          | varchar(255) | 
    | artist_id        | varchar(255) |
    | session_id       | int          | 
    | location         | varchar(255) | 
    | user_agent       | varchar(255) | 
    +------------------+
 

## ETL Processes
The following are the ETL processes for the Sparkify database.
1. **Read and process the _song_data json files**. This process populates the songs and artists dimension tables.
   1. **Write the songs and artists dimension tables to the database**. 
2. **Read and process the log_data json files**. This process populates the songplays fact table, 
the user dimension table and the time dimension table.
   1. **Write the songplays fact table to the database**. 
   2. **Write the user dimension table to the database**. 
   3. **Write the time dimension table to the database**. 
## Execution
The first step is to run the following command to create the database and the tables.

    $ python create_database.py

Once the database and the tables are created, we proceed to populate the tables with the data
by executing the ETL pipeline.

    $ python etl.py

## Conclusion
This project is a good example of how to use the PostgreSQL database. 
The data model is well-defined and easy to understand. 
The ETL processes are well-defined and easy to understand. 
The data model and ETL processes are well-defined and easy to understand.
## References
* [PostgreSQL](https://www.postgresql.org/)
* [Udacity Data Engineering Course](https://www.udacity.com/course/data-engineer-nanodegree--nd027)

## Acknoledgements
This project is based on the Udacity Data Engineering Course.

## License
This project is licensed under the MIT License.

## Author
**Erick Escobar**
* [LinkedIn](https://www.linkedin.com/in/erick-escobar-892b20103/)



