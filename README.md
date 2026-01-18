# 💰 Personal Finance Dashboard

> **Excel-based budget tracking and financial analysis dashboard**

An interactive Excel dashboard that analyzes personal spending patterns, tracks budget performance, and visualizes financial trends across 21 months of transaction data.

**Dataset** - https://www.kaggle.com/datasets/bukolafatunde/personal-finance

[![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://www.microsoft.com/en-us/microsoft-365/excel)
[![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)]()

<img width="2259" height="1129" alt="image" src="https://github.com/user-attachments/assets/36f19d0f-f613-4583-8722-ee59187984f2" />


---

## 📊 Project Overview

This project demonstrates Excel proficiency through a comprehensive personal finance dashboard that:
- Tracks income and expenses across multiple categories
- Compares actual spending against budget targets
- Visualizes spending trends over time
- Provides actionable insights for financial planning

**Project Type**: Data Analysis • Dashboard Design • Financial Modeling  

---

## 🎯 Key Features

### Data Management
- 📁 **807 transactions** spanning 21 months (Jan 2018 - Sep 2019)
- 🏷️ **Hierarchical categorization** (8 main categories, 24+ subcategories)
- 💳 **Multiple account tracking** (Checking, Credit Cards)
- 📅 **Monthly aggregation** with automated calculations

### Analysis & Insights
- 💰 Monthly income vs. expense tracking
- 📊 Category-wise spending breakdown
- 🎯 Budget vs. actual performance monitoring
- 📈 Trend analysis across time periods

### Visualizations
- 📉 **Line Chart**: Income and expense trends over time
- 📊 **Area Chart**: Category spending patterns by month

---

## 📂 Dashboard Structure

### Sheet 1: PersonalTransactions
**Purpose**: Raw transaction data storage

| Column | Description | Example |
|--------|-------------|---------|
| Date | Transaction date | 2018-01-15 |
| Description | Transaction details | "Amazon" |
| Amount | Transaction value | $45.99 |
| Transaction Type | Debit or Credit | "debit" |
| Category | Spending category | "Shopping" |
| Main Category | Parent category | "Personal" |
| Account Name | Payment source | "Platinum Card" |

**Records**: 807 transactions  
**Date Range**: January 1, 2018 - Swptember 31, 2019

### Sheet 2: Budget
**Purpose**: Monthly budget targets by category

- Defines spending limits for each category
- Used for budget vs. actual comparisons
- Linked via VLOOKUP to main categories

### Sheet 3: CategoryMapping
**Purpose**: Hierarchical category structure

| Category | Main Category |
|----------|---------------|
| Groceries | Food |
| Restaurants | Food |
| Mortgage & Rent | Housing |
| Gas & Fuel | Transportation |

**Total Categories**: 24 subcategories → 8 main categories

### Sheet 4: Personal Finance Dashboard
**Purpose**: Visual summary and analysis

- Monthly spending summaries by category
- 2 interactive charts (Line + Area)
- Automated calculations using SUMIFS
- Trends and insights

---

## 🔍 Technical Highlights

### Formula Examples

**1. Category Aggregation (SUMIFS)**
```excel
=SUMIFS(PersonalTransactions!$C:$C, 
        PersonalTransactions!$A:$A, ">="&$A2, 
        PersonalTransactions!$A:$A, "<"&DATE(YEAR($A2),MONTH($A2)+1,1),
        PersonalTransactions!$F:$F, B$1,
        PersonalTransactions!$D:$D, "debit")
```
*Calculates total spending for a specific category within a month*

**2. Category Lookup (VLOOKUP)**
```excel
=VLOOKUP(E2, CategoryMapping!$A:$B, 2, FALSE)
```
*Maps subcategories to main category groups*

**3. Income Calculation**
```excel
=SUMIFS(PersonalTransactions!$C:$C,
        PersonalTransactions!$A:$A, ">="&$A2,
        PersonalTransactions!$A:$A, "<"&DATE(YEAR($A2),MONTH($A2)+1,1),
        PersonalTransactions!$D:$D, "credit")
```
*Sums all income (credit) transactions for the month*


```

**Relationships**:
- `PersonalTransactions[Category]` → `CategoryMapping[Category]`
- `CategoryMapping[Main Category]` → `Budget[Main Category]`
```
---

## 📊 Key Insights

### Spending Analysis
- **Total Income**
- **Total Expenses**
- **Net Savings**
- **Savings Rate**

---

**If you found this project helpful, please consider giving it a ⭐!**
