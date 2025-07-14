# Online Bookstore Analysis

## Overview
This project involves a comprehensive analysis of an online bookstore's sales data using SQL. The goal is to extract valuable insights and answer various business questions based on the dataset. The following README provides a detailed account of the project's objectives, business problems, solutions, findings, and conclusions.

## Objectives
- Analyze the distribution of book genres.
- Identify the most common authors and their works.
- List and analyze books based on publication years, prices, and stock levels.
- Explore and categorize books based on specific criteria and keywords.

## Dataset
The data for this project is sourced from a fictional online bookstore dataset.

## Schema
```sql
DROP TABLE IF EXISTS Books;
CREATE TABLE Books (
    Book_ID SERIAL PRIMARY KEY,
    Title VARCHAR(100),
    Author VARCHAR(100),
    Genre VARCHAR(50),
    Published_Year INT,
    Price NUMERIC(10, 2),
    Stock INT
);

DROP TABLE IF EXISTS Customers;
CREATE TABLE Customers (
    Customer_ID SERIAL PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(100),
    Phone VARCHAR(15),
    City VARCHAR(50),
    Country VARCHAR(150)
);

DROP TABLE IF EXISTS Orders;
CREATE TABLE Orders (
    Order_ID SERIAL PRIMARY KEY,
    Customer_ID INT REFERENCES Customers(Customer_ID),
    Book_ID INT REFERENCES Books(Book_ID),
    Order_Date DATE,
    Quantity INT,
    Total_Amount NUMERIC(10, 2)
);

# Online Bookstore Analysis

## Overview
This project analyzes online book sales using a MySQL database. It includes the creation of a database schema, tables for books, customers, and orders, and various SQL queries to extract insights from the data.

## Database Schema
The database consists of the following tables:
- **Books**: Contains information about books available for sale.
- **Customers**: Stores customer details.
- **Orders**: Records customer orders.

## SQL Scripts
- **schema.sql**: Contains the SQL commands to create the database and tables.
- **queries.sql**: Contains various SQL queries to analyze the data.

## Getting Started
To set up the database locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/OnlineBookstore-Analysis.git
