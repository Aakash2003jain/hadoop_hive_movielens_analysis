# Hive Movie Ratings Analysis

This project demonstrates a simple **Big Data Analysis** using **Hadoop** and **Hive** to analyze movie ratings. The dataset is based on the MovieLens dataset, and the analysis includes queries for identifying popular movies, active users, and rating distributions.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Data Loading and Queries](#data-loading-and-queries)
- [Features](#features)
- [Report](#Report)

---

## Project Overview

The purpose of this project is to demonstrate the power of Hive and Hadoop for analyzing large datasets. It includes:
- Loading a **MovieLens** dataset into HDFS.
- Creating a Hive **External Table** to link the dataset.
- Running SQL-like queries to perform data analysis, such as:
  - Top-rated movies.
  - Movies rated by the most unique users.
  - Active users and their rating counts.
  - Distribution of ratings over time.

---

## Prerequisites

Ensure you have the following installed on your system:
- **Hadoop** (configured and running)
- **Hive** (configured with Hive Metastore)
- **HDFS** (Hadoop Distributed File System)
- **Java JDK** (required by Hadoop)
- Basic knowledge of HiveQL.

---

## Setup Instructions

Follow these steps to run the project on your local Hadoop-Hive setup:

### Step 1: Clone the Repository
```bash
git clone https://github.com/Aakash2003jain/hadoop_hive_movielens_analysis.git
cd hadoop_hive_movielens_analysis
```

### Step 2: Run Hadoop Daemons
a) Start Hadoop daemons:
```bash  
  start-all.cmd
```
b) Check if daemons are running:
```bash
  jps
```

### Step 3: Run Derby Server
a) Start the Derby Network Server:
```bash
  StartNetworkServer -h 0.0.0.0
```
### Step 4: Initialize Hive Schema
a) Navigate to C:\hive\bin and run the following command:
```bash
  hive --service schematool -dbType derby -initSchema
```

### Step 5: Start Hive
a) Start Hive by running:
```bash
hive
```

### Step 6. Success!
You will now be prompted with the Hive command line, ready to run SQL commands.

## Data Loading and Queries

To load the dataset into Hadoop's HDFS and Hive, follow these steps:

### Step 1: Download the Dataset:
   - Download the movie ratings dataset from the following link:
     - [MovieLens 20M Dataset](https://files.grouplens.org/datasets/movielens/ml-20m.zip)
   - Extract the zip file. You will find multiple CSV files, including `ratings.csv`.

### Step 2: Upload the Dataset to HDFS
Use the following command to upload the dataset into HDFS. This command will create a directory `/user/movieratings` in HDFS and place the dataset there.

```bash
hdfs dfs -mkdir /user/movieratings
hdfs dfs -put data/movielens.csv /user/movieratings
```
### Step 3: Verify the Dataset in HDFS
After uploading the dataset, you can verify that it has been successfully placed in HDFS using the following command:

```bash
hdfs dfs -ls /user/movieratings
```
This command will list the contents of the /user/movieratings directory in HDFS, ensuring the dataset is present.


### Step 4: Create Hive External Table
Once the dataset is uploaded to HDFS, you need to create an external table in Hive to link the data. This step will allow you to query the dataset directly using HiveQL.

In Hive CLI, run the following command to create the table:
```bash
CREATE EXTERNAL TABLE movie_ratings (
    userId INT,
    movieId INT,
    rating FLOAT,
    timestamp STRING
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE
LOCATION '/user/movieratings/';

```
### Step 5: Verify Data Loading
After creating the table, you can run a simple query to ensure that the data is loaded correctly:
```bash
SELECT * FROM movie_ratings LIMIT 10;
```
This query will return the first 10 rows from the movie_ratings table.

## Features

This project provides an end-to-end solution for processing and querying movie rating data using **Hadoop** and **Hive**. The key features of this project include:

1. **Data Loading and Integration**:
   - The project enables the loading of large datasets from local systems to Hadoop Distributed File System (HDFS).
   - It uses Hive to manage the data, allowing for external table creation that references data stored in HDFS.
   - Supports CSV file format for easy integration with various data sources.

2. **Hive Queries**:
   - Perform data analysis and querying using HiveQL (Hive's query language).
   - The project includes sample queries to calculate average ratings, the most popular movies, and other key metrics from the movie rating dataset.

3. **Data Storage in HDFS**:
   - Efficiently store large datasets in HDFS, enabling fault tolerance and high availability.
   - Organize data under a specific directory (`/user/movieratings`) in HDFS.

4. **Scalability**:
   - The project is designed to handle large volumes of data, making it scalable for production-grade datasets.
   - Uses the power of Hadoop’s distributed system to manage and process data.

5. **External Table Management with Hive**:
   - External tables in Hive are used to map the data stored in HDFS without importing it into the Hive warehouse, making it easier to work with external data sources.
   - Supports the creation of tables with various column types, such as INT, FLOAT, and STRING, and defines delimiters for data files.

6. **Simple Data Analysis**:
   - Query the data to gain insights into the movie ratings, including:
     - Calculating the average rating per movie.
     - Identifying the most popular movies based on the number of ratings.
     - Retrieving top-rated movies for a specific user or set of users.

7. **Integration with Hadoop Ecosystem**:
   - Leverages the full Hadoop ecosystem for data storage (HDFS), processing (MapReduce or Spark), and querying (Hive).

8. **Command-Line Execution**:
   - Supports the execution of commands directly from the Hadoop and Hive command line interfaces for easy automation and integration into larger data pipelines.

These features ensure that this project is efficient, scalable, and ready for real-world applications in big data analytics and data processing.

## Report
A detailed report that includes the following is also available:

### Hive Queries: 
The report contains a list of all the Hive queries used in this project.
### Query Outputs: 
Screenshots of the output of each query are included in the report for easy reference and validation of the results.
