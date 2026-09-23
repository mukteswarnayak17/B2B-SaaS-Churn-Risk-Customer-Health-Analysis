# B2B SaaS Customer Churn & Health Analysis

An Exploratory Data Analysis (EDA) project focused on understanding customer churn, revenue patterns, billing behavior, and customer support performance in a B2B Software-as-a-Service (SaaS) business.

---

## 📌 Project Overview

Customer churn is one of the major challenges for SaaS businesses. Understanding why customers leave requires analyzing different areas of the customer lifecycle, including subscriptions, billing, support interactions, and customer demographics.

This project analyzes multiple interconnected operational datasets to identify patterns related to:

- Customer churn
- Monthly Recurring Revenue (MRR)
- Invoice payment behavior
- Customer demographics
- Subscription characteristics
- Support ticket activity
- Support resolution time
- Potential customer health indicators

The analysis was performed using Python and focuses on transforming raw operational data into meaningful business insights.

---

## 🎯 Project Objectives

The main objectives of this project are:

1. Understand the overall customer and business profile.
2. Analyze customer distribution across industries and company sizes.
3. Measure the historical customer churn rate.
4. Analyze Monthly Recurring Revenue (MRR).
5. Identify patterns in invoice payment behavior.
6. Analyze customer support ticket volume and resolution time.
7. Identify operational factors that could potentially be associated with customer churn.
8. Define possible next steps for building a customer health and churn prediction system.

---

## 🛠️ Tech Stack

### Programming Language
- Python 3

### Environment
- Jupyter Notebook
- Google Colab

### Python Libraries
- Pandas
- NumPy
- Matplotlib
- Seaborn
- OpenPyXL

---

## 📂 Dataset Overview

The project uses five core operational datasets.

| Dataset | Records | Description |
|---|---:|---|
| `cleaned_accounts.xlsx` | 1,200 | Business account information including industry, country, and employee count |
| `cleaned_invoices.xlsx` | 14,500 | Billing records containing invoice amounts and payment statuses |
| `cleaned_subscriptions.xlsx` | 1,200 | Subscription information including seat count, MRR, and historical churn flags |
| `cleaned_support_tickets.xlsx` | 5,600 | Customer support interactions including categories, priority levels, and resolution hours |
| `cleaned_users.xlsx` | 21,884 | Individual user profiles mapped to their respective business accounts |

The datasets are connected primarily through the `account_id` field, which allows customer-level analysis across different operational areas.

---

## 🔗 Data Relationships

The main relationship between the datasets is based on the customer account.

```text
                    ┌─────────────────────┐
                    │       Accounts      │
                    │                     │
                    │     account_id      │
                    │     industry        │
                    │     country         │
                    │     employees       │
                    └──────────┬──────────┘
                               │
                ┌──────────────┼──────────────┐
                │              │              │
                ▼              ▼              ▼
       ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
       │Subscriptions │ │   Invoices   │ │    Users     │
       │              │ │              │ │              │
       │    MRR       │ │ Invoice Amt  │ │  User Info   │
       │    Seats     │ │ Payment      │ │              │
       │ Churn Flag   │ │   Status     │ │              │
       └──────────────┘ └──────────────┘ └──────────────┘
                │
                │
                ▼
       ┌──────────────────┐
       │ Support Tickets  │
       │                  │
       │ Category         │
       │ Priority         │
       │ Resolution Time  │
       └──────────────────┘
