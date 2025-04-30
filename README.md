# goit-rdb-fp
Related Data Bases (MySQL Workbench)

Final Project: Relational Data Analysis and Normalization in MySQL

This project demonstrates practical skills in SQL data modeling, normalization, and analysis using real-world epidemiological data. The tasks were performed using MySQL and include schema creation, data import, data cleaning, normalization to 3NF, aggregation queries, and the creation of a custom SQL function.
1. Data Import and Initial Setup
- Created a new schema called pandemic via SQL.
- Set the schema as the default working environment.
- Imported raw data into a table named infectious_cases using the MySQL Import Wizard.
- Conducted an initial review of the dataset to understand its structure.
- Observed repeated values in the Entity and Code columns and prepared the data for normalization.
2. Normalization to 3rd Normal Form
  Decomposed the original infectious_cases table into two normalized tables:
- countries — a reference table containing unique combinations of Entity and Code.
- disease_cases — a fact table containing disease case records linked by country_id, year, and disease_id.
- Populated the new structure using INSERT ... SELECT with transformations and JOINs.
- Executed SELECT COUNT(*) FROM infectious_cases to verify the number of successfully imported records.
3. Data Aggregation and Analysis
- Calculated the AVG, MIN, MAX, and SUM of number_rabies per country.
- Filtered out null or empty string values to ensure clean numeric aggregation.
- Grouped by Entity and Code, sorted the result by average value in descending order.
- Displayed the Top 10 countries by average rabies cases.
4. Year-Based Date Transformation
Added computed columns to generate:
- The date January 1st of each year using MAKEDATE().
- The current date using CURDATE().
- The difference in years between those two dates using TIMESTAMPDIFF().
- This transformation helps analyze the relative age of each record without referencing external timestamps.
5. Custom SQL Function
Developed a custom SQL function named YearDifferenceFromNow() that:
- Accepts an integer year as input.
- Returns the number of full years between 01-01-{year} and the current date.
- Applied the function directly in queries for reusable year-based calculations.
