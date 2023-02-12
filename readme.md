# Databricks with Azure Data Factory

The goal of this project was to load a CSV file from a Landing folder located in a DataLake storage account container, validate the data using Databricks, and load the validated file into a Staging folder while pushing the rejected data into the Rejected folder.

Strategy Inspired by Udemy Course: 2 Real World Azure Data Engineer Project End to End

# Architecture Diagram
![Section 2_ Project 2_ AP Morgan Data Platform](https://user-images.githubusercontent.com/121827505/216208968-b52547b4-ef9e-468f-bc0e-d7711e2ebda3.jpg)

# Project Setup

- CSV files are placed into the landing folder which was then transfered into Databricks using Azure Data Factory Notebook Pipeline
- Databricks validate data and distributes the files into their appropriate folders
    - Validation Requirements:
        - No duplicate rows
        - Correct Data format for all data fiels
        - If validation succeeds move passed files into staging folder
- Passed files are writen as a Delta table in Azure Databricks
- Sequal Server Management Studio was used to connect SQL Database to manage the SQL infrastructure
- Azure Key Vault stored secrets and generated the SAS token used thoughout the project
- Project triggers when a CSV file is place into the landing folder
