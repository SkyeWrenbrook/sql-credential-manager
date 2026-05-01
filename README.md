# SQL Credential Database (SQLite) 

## Overview

This project is part of a larger system exploring how credential data is stored, validated, and analyzed.
It focuses on the database layer, where structured credential data is imported into SQLite and queried using SQL.

[Related application project](https://github.com/SkyeWrenbrook/credential-manager-cpp)

## System Flow
User Input → C++ Application → Structured Data → SQLite Database → SQL Queries → Analysis

This project represents the storage and query layer, where data is persisted and analyzed.

## Implementation

* Designed a schema to store credential data (site, username, password)
* Imported structured data from a CSV file into a SQLite
* Queried and analyzed stored data using SQL
* Identified and corrected a data integrity issue during import (header row treated as data)

## What I Learned

- how database schemas define and constrain stored data
- how data ingestion (CSV import) can introduce integrity issues
- how SQL queries can be used to validate and analyze stored information
- how improperly stored credentials create security risks

These observations highlight how data handling and storage decisions directly impact system reliabilty and security.

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

<img width="342" height="33" alt="csv-import-count-mismatch" src="https://github.com/user-attachments/assets/aaa6e768-f5f4-4a39-84a8-6489b5477d96" />
      The count returned 71, which was higher than expected.
      This indicated that the CSV header may have been imported as a row.

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
* Data ingestion using `.import`
* Querying with SELECT, WHERE, LIKE, and COUNT
* Data validation and cleanup (identified and removed an unintended header row during import)

## Security Note

Credentials are stored in plaintext in this version.

In a real system, this would introduce significant risk and would require:

- hashing or encryption
- access controls
- secure database handling practices

This highlights how storage decisions directly impact system security.
