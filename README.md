# SQL Credential Manager

Built as part of hands-on practice with database design and data handling workflows. 

## Overview

> A SQLite-based project that models how credential data can be structured, stored, and queried using SQL.
> This project focuses on schema design, CSV data ingestion, and practical query workflows used to interact with stored data. 

## Implementation

* Designed a table to store credential entries (site, username, password)
* Imported structured data from a CSV file into a SQLite database
* Wrote queries to retrieve, filter, and analyze stored data

## Project Structure

* schema.sql – defines the database structure
* credentials.csv – sample dataset used for import
* queries.sql – queries for interacting with the data

## How to run
1. Open SQLite:
```
   sqlite3 credentials.db
```
3. Create the table:
```
   .read schema.sql
```
5. Import data:
```   
   .mode csv
   .import credentials.csv credentials
```
4. Verify data integrity:
```
   SELECT COUNT(*) FROM credentials;
```
      If the count is higher than expected, this may indicate the CSV header was imported as a row.
6. Clean the dataset:
```
   DELETE FROM credentials WHERE site = 'site';
```
7. Run queries:
```   
   .read queries.sql
```
## Key Concepts Demonstrated

* Table design and schema creation
* Data import using .import
* Querying with SELECT, WHERE, LIKE, and COUNT
* Data validation and cleanup (identified and removed an unintended header row during import)

## Notes

Passwords are stored in plaintext in this version for demonstration purposes.

In a real-world system, sensitive data should be encrypted before storage.
