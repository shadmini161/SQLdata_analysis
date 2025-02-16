# SQLdata_analysis
This project demonstrates the use of SQL for data extraction, transformation, and analysis. The primary goal is to perform in-depth analysis of a given dataset to derive valuable insights, trends, and patterns that can aid decision-making.
# SQL-Based Data Analysis Project
## Features
Data Extraction: Writing complex SQL queries to retrieve and filter data from various relational databases.

Data Transformation: Utilizing SQL functions to clean and manipulate data (e.g., aggregations, joins).

Data Analysis: Conducting exploratory data analysis (EDA) using SQL to uncover trends, correlations, and key performance indicators (KPIs).

## Technologies Used
SQL: For querying and analyzing data in relational databases.

PostgreSQL_PgAdmin4: Database management systems.
# QUESTIONS solved by project:

~ Q1: Who is the senior most employee based on job title? 


SELECT title, last_name, first_name 
FROM employee
ORDER BY levels DESC

~ Q2: Which countries have the most Invoices? 


SELECT COUNT(*) AS c, billing_country 
FROM invoice
GROUP BY billing_country
ORDER BY c DESC

~Q3: What are top 3 values of total invoice? 



SELECT total 
FROM invoice
ORDER BY total DESC

~ Q4: Which city has the best customers? We would like to throw a promotional Music Festival in the city we made the most money. 
Write a query that returns one city that has the highest sum of invoice totals. 
Return both the city name & sum of all invoice totals 


SELECT billing_city,SUM(total) AS InvoiceTotal
FROM invoice
GROUP BY billing_city
ORDER BY InvoiceTotal DESC

~ Q5: Who is the best customer? The customer who has spent the most money will be declared the best customer. 
Write a query that returns the person who has spent the most money.


SELECT customer.customer_id, first_name, last_name, SUM(total) AS total_spending
FROM customer
JOIN invoice ON customer.customer_id = invoice.customer_id
GROUP BY customer.customer_id
ORDER BY total_spending DESC






