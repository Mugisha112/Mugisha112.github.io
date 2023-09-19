---
title:  "Power BI Pizza Sales Report Project"
mathjax: true
layout: post
categories: media
---

PROBLEM STATEMENT

[Pizza shop problem statement.docx](https://github.com/Mugisha112/Mugisha112.github.io/files/12656316/Pizza.shop.problem.statement.docx)

## DAX Calculated columns and fields used in report building

Total Revenue = SUM(pizza_sales[total_price])

Total Orders = DISTINCTCOUNT(pizza_sales[order_id])

Total Pizzas Sold = SUM(pizza_sales[quantity])

Avg Order Value = DIVIDE([Total Revenue], [Total Orders])

Avg Pizzas Per Order = DIVIDE([Total Pizzas Sold], [Total Orders])

Extracted Day name and hour name from order date and order time for daily and hourly trends.

Top and Bottom 5 selling pizzas by Revenue, Quantity and Orders using Top N filter

## Built Report

[Pizza sales report.pdf](https://github.com/Mugisha112/Mugisha112.github.io/files/12656326/Pizza.sales.report.pdf)
