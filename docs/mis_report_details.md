# 📊 MIS Report Development Details

---

## 📌 Overview

This document explains the detailed process of building the **Daily MIS Report**, including data modeling, calculations, and business logic applied.

---

## ⚙️ Data Modeling Approach

* Loaded dataset into **Excel Data Model (Power Pivot)**
* Avoided heavy Excel formulas on raw data (~500K rows)
* Used **DAX measures for aggregation and performance optimization**

---

## 📐 Measures (DAX) Created

The following measures were created to support reporting:

* **Total Sales**
* **Total Orders (Distinct InvoiceNo)**
* **Total Quantity Sold**
* **Average Order Value (AOV)**
* **Returned Orders (order-level logic)**
* **Return %**

---

## 🔁 Return Logic (Important)

Returns were initially identified at transaction level (negative quantity).

To ensure accuracy:

* Return logic was implemented at **order level (InvoiceNo)**
* Any order containing negative quantity → marked as returned

👉 This avoids incorrect return percentage calculations

---

## 🧮 Derived Columns Created

* Sales = Quantity × Unit Price
* Year, Month, Weekday extracted from Invoice Date
* Custom date handling for **dynamic daily trend (7/14 days)**

---

## 📊 MIS Report Structure

---

### 🔹 KPI Summary

* Total Sales
* Total Orders
* Total Quantity
* Average Order Value
* Return %

---

### 🔹 Region-wise Performance

* Sales by Country
* Orders by Country
* Average Order Value

---

### 🔹 Product Performance

* Top products by revenue
* Contribution %
* Order distribution

---

### 🔹 Time-based Analysis

* Monthly Sales Trend
* Weekly Sales Pattern
* Daily Sales Trend (custom date range)

---

### 🔹 Returns Analysis

* Identified return transactions
* Measured return impact on revenue
* Implemented order-level return logic

---

### 🔹 Key Insights

* United Kingdom contributes majority of revenue
* Top products drive significant share of sales
* Return rate (~19%) impacts net sales
* Seasonal trends observed in later months
* Daily fluctuations due to bulk and return transactions

---

## 🧠 Key Concepts Applied

* Order-level vs transaction-level analysis
* Efficient aggregation using DAX
* Data cleaning for business accuracy
* Insight-driven reporting
* MIS report structuring

---

## 🚀 Outcome

Developed a **real-world MIS reporting system** capable of:

* Tracking daily business performance
* Identifying revenue drivers
* Monitoring return impact
* Supporting data-driven decisions

---
