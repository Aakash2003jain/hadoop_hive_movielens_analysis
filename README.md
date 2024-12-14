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

### Step 2: Start Hadoop Services
Run Command Prompt as Administrator:

Right-click on the Command Prompt and select Run as Administrator.
Navigate to the sbin directory:

Open Command Prompt as Administrator.
Navigate to the sbin directory:
```bash
cd C:\Hadoop\sbin
```
### Stop Hadoop Services:
```bash
 start-all
```


