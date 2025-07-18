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





erDiagram
    Customers ||--o{ Orders : places
    Books ||--o{ Orders : contains

    Customers {
        int Customer_ID PK
        varchar Name
        varchar Email
        varchar Phone
        varchar City
        varchar Country
    }

    Books {
        int Book_ID PK
        varchar Title
        varchar Author
        varchar Genre
        int Published_Year
        numeric Price
        int Stock
    }

    Orders {
        int Order_ID PK
        int Customer_ID FK
        int Book_ID FK
        date Order_Date
        int Quantity
        numeric Total_Amount
    }
