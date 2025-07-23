# 🎵 Music Store Data Analysis with SQL

Welcome to the Music Store Data Analysis project! This SQL-based project explores sales and customer behavior from a fictional digital music store database. The analysis is based on real-world business questions to help improve marketing, customer retention, and revenue strategies.

## 🎯 Objective

To analyze music store data using SQL by answering business-driven questions related to:
- Customer purchases
- Genre popularity
- City/country-wise performance
- Best customers and artists

## 🗂️ Project Files

| File | Description |
|------|-------------|
| [📄 Music Store Analysis-Questions.pdf](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/Music%20Store%20Analysis-Questions.pdf) | Contains all business questions (Easy, Moderate, Advanced) |
| [🖼️ MusicDatabaseSchema.png](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/MusicDatabaseSchema.png) | Database schema/ER Diagram |
| [📜 Music_Store_Query.sql](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/Music_Store_Query.sql) | SQL queries to answer all the questions |
| [🗄️ Music_Store_database.sql](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/Music_Store_database.sql) | SQL script to create and populate the database |
| [🗂️ Raw-Music Store Analysis-SQL Project.zip](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/Raw-Music%20Store%20Analysis-SQL%20Project.zip) | Complete raw project files |
| [🗃️ music store data.zip](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/music%20store%20data.zip) | Additional data used for querying |

## 🛠️ Tools Used

- **Database:** SQLite
- **Language:** SQL
- **Platform:** DB Browser for SQLite / any SQL editor

## 🗺️ Database Schema

![Database Schema](https://github.com/Aman-Jha07/SQL-Data-Analysis/blob/main/MusicDatabaseSchema.png)

The schema includes tables such as:
- `Customer`
- `Invoice`
- `InvoiceLine`
- `Track`
- `Artist`
- `Genre`
- `Album`
- `Employee`

## ❓ Business Questions

### 🔹 Easy Level
- Who is the senior-most employee?
- Which countries have the most invoices?
- What are the top 3 invoice values?
- Which city has the highest total invoice amount?
- Who is the best customer?

### 🔸 Moderate Level
- List all Rock music listeners.
- Top 10 artists with the most Rock tracks.
- Tracks longer than the average length.

### 🔻 Advanced Level
- Amount spent by each customer on each artist.
- Most popular music genre by country.
- Top spending customer per country.

## 💡 Sample Query

```sql
-- Find the best customer (highest total invoice)
SELECT c.FirstName || ' ' || c.LastName AS Customer_Name,
       SUM(i.Total) AS Total_Spent
FROM Customer c
JOIN Invoice i ON c.CustomerId = i.CustomerId
GROUP BY c.CustomerId
ORDER BY Total_Spent DESC
LIMIT 1;



