# Movies-ETL

## Overview of Project
In preparation for a hackathon, Britta, an Amazing Prime employee is required to gather data from both Wikipedia and Kaggle, combine them, and save them into a SQL database using the ETL process so that the hackathon participants have a nice, clean dataset to use. Data for this project were sourced from Wikipedia and Kaggle stored as JSON and CSV respectively. The below line of actions were executed to acheieve this:
- Loaded the JSON file for wiki_movies using the json.load() and read in the raw wiki data as a Pandas Dataframe.  
- Read the ratings.csv into Pandas Dataframe. 
- Inspected Wiki_movies Data for characteristics, errors, unwanted data etc. 
- Filtered data using list comprehension to cut down bad data. 
- Defined a function to clean the Data (combine alternate titles into one list, merge column names)
- Removed duplicate rows with regex
- Identified null columns using list comprehension and removed
- Converted and Parsed Box office, Budget, Release date and Running time Datas using regex (lamba was introduced to convert numeric data types into a string since regex only works on strings. Romoved dollar signs, spaces, commas, and converted strings to float using regex)
- Reviewed and cleaned up the Kaggle metadata
- Compared similar columns in both datasets to determine the more accurate dataset to retain and subsequently merge Wiki & Kaggle datasets
- Created a database on pgAdmin using to_sql where the merged data were imported into.


### Purpose
To help Britta create an automated pipeline that takes in new data, performs the appropriate transformations (ETL), and loads the data into existing tables on a daily basis.

## Results
A database named movie_data is created in pgAdmin. The schema of this database shows two tables namely movies and ratings. Further query of the tables show the movies table has 6,052 rows while the ratings table has 26,024,289 rows.