---
title:  "Pizza Sales Report SQL Project"
layout: post
---

[Pizza shop problem statement.docx](https://github.com/Mugisha112/Mugisha112.github.io/files/12658587/Pizza.shop.problem.statement.docx)

SQL SOLUTION QUERIES - Notepad

[Pizza Sales SQL Queries - Solutions.txt](https://github.com/Mugisha112/Mugisha112.github.io/files/12658600/Pizza.Sales.SQL.Queries.-.Solutions.txt)

## SQL SOLUTION QUERIES:

## KPI REQUIREMENTS

## Total Revenue:

SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

## Average Order Value:
   
SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales

## Total Pizzas Sold:
   
SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales

## Total Orders:
   
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales

## Average Pizzas Per Order:
   
SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2)) AS Avg_Pizzas_per_order FROM pizza_sales

## CHART REQUIREMENTS

## Daily Trend for Total Orders:
   
SELECT DAYNAME(order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders FROM pizza_sales GROUP BY DAYNAME(order_date)

## Hourly Trend for Orders:
   
SELECT hour(order_time) as Hour_24, COUNT(DISTINCT order_id) as Total_Orders FROM pizza_sales GROUP BY hour(order_time)

## % of Sales by Pizza Category:
   
SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue, CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT FROM pizza_sales GROUP BY pizza_category

## % of Sales by Pizza Size:

SELECT pizza_size, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue, CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT FROM pizza_sales GROUP BY pizza_size ORDER BY pizza_size

## Total Pizzas Sold by Pizza Category:

SELECT pizza_category, SUM(quantity) as Total_Quantity_Sold FROM pizza_sales  GROUP BY pizza_category ORDER BY Total_Quantity_Sold DESC

## Top 5 Pizzas by Revenue:

SELECT Top 5 pizza_name, SUM(total_price) AS Total_Revenue FROM pizza_sales GROUP BY pizza_name ORDER BY Total_Revenue DESC

## Bottom 5 Pizzas by Revenue:

SELECT Top 5 pizza_name, SUM(total_price) AS Total_Revenue FROM pizza_sales GROUP BY pizza_name ORDER BY Total_Revenue ASC
