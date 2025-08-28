# 📚  Bookstore Analysis  

![MySQL](https://img.shields.io/badge/Database-MySQL-blue)  
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)  
![License](https://img.shields.io/badge/License-MIT-lightgrey)  

## 📖 Overview  
This project implements a relational **Online Bookstore Database** using MySQL.  
It demonstrates **database design, data import from CSV files, and SQL-based analytics** through 20+ queries that address real-world bookstore operations.  

The goal is to provide a structured, efficient, and scalable solution for managing books, customers, and orders, while generating useful business insights.  

---

## 🗂️ Project Structure  
- `Books.csv` → Book catalog (title, author, genre, year, price, stock)  
- `Customers.csv` → Customer information (name, email, city, country)  
- `Orders.csv` → Transactional order details  
- `BookStore_Analysis.sql` → SQL script for schema creation, data import, and business queries  

---

## 🛠️ Database Schema  
```mermaid
erDiagram
    Books {
        int Book_ID PK
        varchar Title
        varchar Author
        varchar Genre
        int Published_Year
        decimal Price
        int Stock
    }
    Customers {
        int Customer_ID PK
        varchar Name
        varchar Email
        varchar Phone
        varchar City
        varchar Country
    }
    Orders {
        int Order_ID PK
        int Customer_ID FK
        int Book_ID FK
        date Order_Date
        int Quantity
        decimal Total_Amount
    }

    Customers ||--o{ Orders : places
    Books ||--o{ Orders : contains
