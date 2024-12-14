# Hive Movie Ratings Analysis

This project demonstrates a simple **Big Data Analysis** using **Hadoop** and **Hive** to analyze movie ratings. The dataset is based on the MovieLens dataset, and the analysis includes queries for identifying popular movies, active users, and rating distributions.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Data Loading and Queries](#data-loading-and-queries)
- [Features](#features)

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


