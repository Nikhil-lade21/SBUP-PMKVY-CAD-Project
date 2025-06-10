# SBUP-PMKVY-CAD-Project

Customer Data Cleaning and Standardization Project
This project focuses on building an Extract, Transform, Load (ETL) pipeline using AWS Glue to cleanse and standardize raw customer data. The goal is to transform messy, inconsistent customer records into a clean, unified dataset suitable for downstream analytics, reporting, and operational use.

Project Overview
Raw customer data often suffers from inconsistencies, missing values, and duplicates, which can significantly hinder data analysis and lead to inaccurate insights. This ETL job addresses these common data quality issues by implementing a series of transformations:

Duplicate Removal: Eliminates redundant customer entries.
Missing Value Imputation: Fills in gaps in critical customer fields.
Format Standardization: Ensures consistency for phone numbers and email addresses.
Text Normalization: Applies proper casing to names and addresses for uniformity.
The transformed data is then ready for use in various business intelligence tools, CRM systems, or data warehousing solutions.

Project Files
This repository contains the following key files:

1. customers_raw_500.csv
Description: This file represents the raw input data for the ETL pipeline. It contains details for approximately 500 customer records.
Characteristics: As is common with real-world data, this file intentionally includes various data quality issues such as:
Missing values: Some rows may have empty fields for attributes like email, phone, or address.
Duplicate entries: Redundant customer records may be present.
Inconsistent formatting: Phone numbers, email addresses, and text fields might not adhere to a uniform standard (e.g., varying phone number formats, mixed casing in names).
Purpose: Serves as the source dataset to demonstrate the effectiveness of the data cleaning and standardization process.
2. data cleaning.docx
Description: This document provides the detailed script and logic used for the ETL job. It outlines the specific PySpark transformations applied within the AWS Glue environment.
Content: The document covers the implementation of the following data cleaning and standardization steps:
Reading data from the source (S3).
PySpark code for identifying and removing duplicate customer records.
Strategies and code for filling in missing values (e.g., replacing null with default placeholders like "Unknown" or "No Address Provided").
Regular expressions and string manipulation functions used for standardizing phone number formats (e.g., (XXX) XXX-XXXX) and converting email addresses to lowercase.
Functions for normalizing text fields (e.g., initcap for proper casing of names and addresses).
Writing the transformed data to the target (S3).
Purpose: This document acts as the technical blueprint for the Glue ETL job, allowing for easy understanding, replication, and modification of the data cleaning logic.
3. run-1749543965342-part-r-00000.csv
Description: This file is the output of the ETL job after processing customers_raw_500.csv. It represents the cleaned and standardized customer data.
Characteristics: Compared to the raw input, this file is expected to have:
No duplicate rows.
Fewer or no missing values in key fields (depending on the imputation strategy).
Consistent formats for phone numbers and email addresses.
Uniform proper casing for names and addresses.
Purpose: This file demonstrates the successful execution of the data cleaning pipeline and provides a ready-to-use dataset for analytics and other business applications. The timestamp in the filename is indicative of a specific Glue job run.
