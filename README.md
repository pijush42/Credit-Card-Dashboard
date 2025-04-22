# 💳 Credit Card Transaction Dashboard

A dynamic business intelligence dashboard built using **Power BI** and **PostgreSQL** to analyze customer credit card usage, revenue trends, and transaction behavior.

---

## 🧠 Project Overview

This project visualizes and explores transaction data to uncover patterns across different customer groups. Designed to support marketing and risk teams with insights into:

- Revenue distribution by card type and customer profile
- Trends in transaction volumes over time
- High-value and low-engagement customer segments

---

## 🛠️ Tools & Technologies

| Tool          | Purpose                        |
|---------------|--------------------------------|
| Power BI      | Data modeling, visualization   |
| PostgreSQL    | Backend data extraction        |
| DAX           | Calculated measures & filters  |
| SQL           | Data transformation & joins    |

---

## 📊 Key Features

- **Dashboard Tabs**: Overview, Revenue, Customers, Transactions
- **Interactive Filters**: 
  - Time filters by **quarter**
  - Customer filters by **income group**, **gender**, **education**, **transaction mode**
- **Visualizations**:
  - Donut and bar charts for card usage and income segments
  - Time-series revenue and transaction trends
  - Customer segmentation with DAX logic
- **Advanced Analysis**:
  - Cohort analysis
  - Behavioral patterns by age group and card category

---

## 📁 File Contents
![cc_transaction](https://github.com/user-attachments/assets/10eb7b91-b838-4f50-b60d-323c9ba582c1)

![cc_cust](https://github.com/user-attachments/assets/f6228294-fd69-479e-b94d-bd1ffe567295)

- `CC_DASHBOARD.pbix` –
- `README.md` – Project summary and explanation
- 
[Uploading SQL Q-- SQL Query to create and import data from csv files:

-- 0. Create a database 
CREATE DATABASE ccdb;

-- 1. Create cc_detail table

CREATE TABLE cc_detail (
    Client_Num INT,
    Card_Category VARCHAR(20),
    Annual_Fees INT,
    Activation_30_Days INT,
    Customer_Acq_Cost INT,
    Week_Start_Date DATE,
    Week_Num VARCHAR(20),
    Qtr VARCHAR(10),
    current_year INT,
    Credit_Limit DECIMAL(10,2),
    Total_Revolving_Bal INT,
    Total_Trans_Amt INT,
    Total_Trans_Ct INT,
    Avg_Utilization_Ratio DECIMAL(10,3),
    Use_Chip VARCHAR(10),
    Exp_Type VARCHAR(50),
    Interest_Earned DECIMAL(10,3),
    Delinquent_Acc VARCHAR(5)
);


-- 2. Create cc_detail table

CREATE TABLE cust_detail (
    Client_Num INT,
    Customer_Age INT,
    Gender VARCHAR(5),
    Dependent_Count INT,
    Education_Level VARCHAR(50),
    Marital_Status VARCHAR(20),
    State_cd VARCHAR(50),
    Zipcode VARCHAR(20),
    Car_Owner VARCHAR(5),
    House_Owner VARCHAR(5),
    Personal_Loan VARCHAR(5),
    Contact VARCHAR(50),
    Customer_Job VARCHAR(50),
    Income INT,
    Cust_Satisfaction_Score INT
);


-- 3. Copy csv data into SQL (remember to update the file name and file location in below query)

-- copy cc_detail table

COPY cc_detail
FROM 'D:\credit_card.csv' 
DELIMITER ',' 
CSV HEADER;


-- copy cust_detail table

COPY cust_detail
FROM 'D:\customer.csv' 
DELIMITER ',' 
CSV HEADER;



-- If you are getting below error, then use the below point:  
   -- ERROR:  date/time field value out of range: "0"
   -- HINT:  Perhaps you need a different "datestyle" setting.

-- Check the Data in Your CSV File: Ensure date column values are formatted correctly and are in a valid format that PostgreSQL can recognize (e.g., YYYY-MM-DD). And correct any incorrect or missing date values in the CSV file. 
   -- or
-- Update the Datestyle Setting: Set the datestyle explicitly for your session using the following command:
SET datestyle TO 'ISO, DMY';

-- Now, try to COPY the csv files!


-- 4. Insert additional data into SQL, using same COPY function

-- copy additional data (week-53) in cc_detail table

COPY cc_detail
FROM 'D:\cc_add.csv' 
DELIMITER ',' 
CSV HEADER;


-- copy additional data (week-53) in cust_detail table (remember to update the file name and file location in below query)

COPY cust_detail
FROM 'D:\cust_add.csv' 
DELIMITER ',' 
CSV HEADER;

uery - Financial Dashboard Data.sql…]()

---

## 📌 Insights Delivered

- Identified top-performing card categories among high-income users
- Detected drop in transaction volumes for specific age groups in Q3
- Segmented customers for targeted loyalty campaigns

---

## 🔗 Related Links

- [Power BI Portfolio (GitHub)](https://github.com/pijush42/PowerBi-Portfolio)
- [Project Preview ](https://www.linkedin.com/posts/pijush-kuri-uk42_powerbi-dataanalytics-postgresql-activity-7317349798477488128-skEF?utm_source=share&utm_medium=member_desktop&rcm=ACoAACpwg2wBfiALgINQFk9F0T3pMRYn1B2aLo8))]
- [Contact Me on LinkedIn](https://www.linkedin.com/in/pijush-kuri-uk42)

---

## 📬 Contact

**Pijush Kuri**  
📧 pijushkuri42@gmail.com  
📍 Frankfurt, Germany  
🔗 [GitHub Profile](https://github.com/pijush42)

---

> ⚡ *Feel free to fork this repo or get in touch for collaboration or freelance data projects!*
