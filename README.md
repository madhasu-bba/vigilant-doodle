# 📊 Cohort Retention Analysis – Online Retail II

## 📌 Project Overview

This project focuses on **customer cohort retention analysis** using the **Online Retail II dataset**. The objective is to understand how customer retention changes over time by grouping customers according to the month of their first valid purchase.

Instead of looking at overall customer activity, cohort analysis helps track different groups of customers separately and understand their repeat-purchase behavior over multiple months.

The project includes data cleaning, cohort creation, retention calculation, a cohort retention table, a heatmap, and business insights.

---

## 🎯 Objective

The main objectives of this project are:

* Build a customer cohort retention table.
* Identify each customer's first valid purchase month.
* Track customer activity in subsequent months.
* Calculate monthly retention percentages.
* Visualize retention using a heatmap.
* Identify customer drop-off patterns.
* Understand seasonal changes in customer retention.
* Generate actionable business insights from retention data.

---

## 📂 Dataset

**Dataset:** Online Retail II – UCI

**Data Period:** 1 December 2009 – 9 December 2011

The dataset contains retail transaction-level information, including customer IDs, invoice information, invoice dates, quantities, and prices.

Since the dataset does not contain an actual signup date, the **month of a customer's first valid purchase** was used as a proxy for the signup/cohort month.

---

## 🧹 Data Cleaning

The raw dataset contained **1,067,371 rows**.

The following cleaning steps were applied:

| Cleaning Step                           | Rows Remaining |
| --------------------------------------- | -------------: |
| Raw rows                                |      1,067,371 |
| After removing missing CustomerID       |        824,364 |
| After removing cancellations            |        805,620 |
| After removing Quantity ≤ 0 / Price ≤ 0 |        805,549 |
| After excluding partial December 2011   |        788,244 |

After cleaning, the analysis contained:

* **5,850 unique customers**
* **24 customer cohorts**
* Cohorts from **December 2009 to November 2011**

Guest checkouts without a CustomerID were removed because they could not be tracked across time. Cancellation invoices and non-positive quantity/price transactions were also removed because they do not represent valid purchases.

---

## 👥 Cohort Definition

A **cohort** is a group of customers who share a common starting event within the same period.

In this project:

> A customer's cohort is the calendar month of their first valid purchase.

For example:

* A customer whose first valid purchase occurred in January 2010 belongs to the **2010-01 cohort**.
* Their activity in February 2010 is measured as **M1**.
* Their activity in March 2010 is **M2**.
* Their activity continues across subsequent months.

This lets you compare customer behavior by how long they have been customers, rather than by calendar month.

---

## 📅 Retention Methodology

The retention window is measured using the number of calendar months since the customer's cohort month.

* **M0** = Cohort month
* **M1** = One month after cohort month
* **M2** = Two months after cohort month
* **M3** = Three months after cohort month
* And so on.

A customer is considered **retained** in a particular month if they placed at l
