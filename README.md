# SQL Credential Manager

## Overview

This project demonstrates how to design and interact with a structured database for storing credential data using SQL and SQLite.

## What I Built

* Designed a table to store credential entries (site, username, password)
* Imported structured data from a CSV file into a SQLite database
* Wrote queries to retrieve, filter, and analyze stored data

## Files

* schema.sql – defines the database structure
* credentials.csv – sample dataset used for import
* queries.sql – queries for interacting with the data

## Key Concepts Demonstrated

* Table design and schema creation
* Data import using .import
* Querying with SELECT, WHERE, LIKE, and COUNT
* Data validation and cleanup (identified and removed an unintended header row during import)

## Notes

Passwords are stored in plaintext in this version for demonstration purposes.

In a real-world system, sensitive data should be encrypted before storage.
