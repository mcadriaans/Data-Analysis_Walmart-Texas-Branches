
![image](https://github.com/user-attachments/assets/bcf2bd1d-dbe2-4980-b443-eb80279089ee)

## About the Project
This project presents a comprehensive data analysis strategy designed to extract key business insights from Walmart's sales data spanning from January 1, 2019, to December 31, 2023. We employ Python to effectively load, understand, and clean the data. Additionally, we utilize advanced SQL querying to apply structured problem-solving techniques and address significant business challenges.

This Python code effectively cleans and prepares the "Walmart.csv" data for further analysis. The cleaned data is free of duplicates, missing values, and formatting inconsistencies, and includes a new column for 'total_revenue'. 

## Project Steps
Here are the concise project steps based on your code:

1. **Get dataset from Kaggle:**
   - Install Kaggle package.
   - Upload `kaggle.json` for authentication.
   - Download and unzip the dataset.

2. **Load dependencies:**
   - Import necessary libraries (`pandas`, `numpy`, `warnings`).

3. **Load data:**
   - Read the dataset into a DataFrame.

4. **Understand the data:**
   - Check data information and missing values.
   - Describe the dataset to understand the distribution and central tendency.
   - Check for duplicates.

5. **Data Cleaning:**
   - Remove duplicate records.
   - Drop rows with missing values.
   - Convert column names to lowercase.
   - Convert the `date` column to datetime.
   - Remove dollar signs and convert `unit_price` to float.
   - Create a `total_revenue` column.

6. **Export clean data:**
   - Save the cleaned DataFrame to a CSV file.

7. **Data imported to PostgreSQL:**
   - Set up table in PostgreSQL, define data types.
   - Import the cleaned data into PostgreSQL.
   - Execute basic queries to verify the import.

9. **Exploratory Data Analysis**
10. **Solving Business Problems**
    - This phase focuses on applying data insights to answer specific business questions and address critical challenges.

