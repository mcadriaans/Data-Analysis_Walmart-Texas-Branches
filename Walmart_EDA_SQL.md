
## Data imported to PSQL
```sql
SELECT * FROM walmart;
```
![image](https://github.com/user-attachments/assets/c3c7488e-b4d1-4ff7-a0e8-f5e37ba27e6d)

## Exploratory Data Analysis

<b> How many transactions are there?</b>
```sql
SELECT 
 COUNT(*) AS nr_of_transactions
FROM walmart;
```
![image](https://github.com/user-attachments/assets/55571d53-5397-429b-8a9f-1e0a812a7d17)

<b> How many transaction were made for each payment method?</b>
```sql
SELECT 
 payment_method,
 COUNT(*) AS nr_of_transactions
FROM walmart
GROUP BY 1;
```
![image](https://github.com/user-attachments/assets/199c8f82-e98d-4433-a2cb-a4b5dcd774b7)


<b> How many store branches do we have?</b>
```sql
SELECT 
 COUNT(DISTINCT branch) AS total_branches
FROM walmart;
```
![image](https://github.com/user-attachments/assets/8d6a5401-f3ce-474a-9b00-1305cfcbadfd)

<b> What is the minimum and maximum quantity of items sold?</b>
```sql
SELECT 
 MIN(quantity) AS min_quantity_sold,
 MAX(quantity) AS max_quantity_sold
FROM walmart;
```
![image](https://github.com/user-attachments/assets/cc88f953-2500-4a9d-8f9b-7cfd83789d50)


## Business Problems

1. Find the different payment methods their total number of transactions and total quantities sold.
```sql
SELECT 
 payment_method,
 COUNT(*) AS nr_of_transactions,
 SUM(quantity) AS quantity_sold
FROM walmart
GROUP BY 1;
```
![image](https://github.com/user-attachments/assets/788bd8ba-2c3e-4327-b27c-1974dda4562c)

2. Identify the highest-rated category in each branch. Display the branch , category and average rating.
```sql
SELECT
    branch,
    category,
    ROUND(avg_rating::NUMERIC, 2)
FROM (
    SELECT
        branch,
        category,
        AVG(rating) AS avg_rating,
        RANK() OVER (
            PARTITION BY branch
            ORDER BY AVG(rating) DESC
        ) AS rnk
    FROM walmart
    GROUP BY branch, category
) AS subquery
WHERE rnk = 1;
```
3. 

