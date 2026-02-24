# Customer Retention & Churn Analysis  
## 📊 Customer Churn Intelligence Dashboard  
![Customer Churn Dashboard](https://futureinterns.com/wp-content/uploads/2025/12/DS-Task-2.png)
---

## 🎯 Project Objective

This Power BI dashboard analyzes customer churn behavior to uncover key patterns in customer retention, revenue impact, and subscription trends.  

The primary goal is to identify:
- Why customers are leaving  
- Which customer segments churn the most  
- How churn affects revenue  
- Monthly churn and retention trends  

This project transforms raw customer data into actionable business intelligence.

---

## 🛠 Tools & Technologies Used

- Power BI Desktop  
- Power Query Editor  
- DAX (Data Analysis Expressions)  
- Data Modeling & Relationship Building  

---

## 📂 Dataset Overview

This analysis integrates multiple structured datasets:

### 1️⃣ Accounts Data
- Customer ID  
- Country  
- Industry  
- Plan Tier  
- Trial Status  
- Signup Date  

### 2️⃣ Subscription Data
- Monthly Recurring Revenue (MRR)  
- Annual Recurring Revenue (ARR)  
- Upgrade / Downgrade Flag  
- Auto-Renew Status  
- Start Date / End Date  

### 3️⃣ Churn Data
- Churn Date  
- Churn Reason  
- Refund Amount  

### 4️⃣ Usage Data
- Feature Usage Count  
- Usage Duration  
- Error Count  

### 5️⃣ Support Data
- Ticket Priority  
- Resolution Time  
- Escalation Flag  
- Satisfaction Score  

---

## 🧹 Data Cleaning & Transformation

The following preprocessing steps were performed:

1. Corrected inconsistent column names  
2. Converted date columns to proper format  
3. Removed duplicate records  
4. Standardized categorical values (Country, Plan Tier, Industry)  
5. Converted churn flags to numeric values  
6. Created relationships between all tables  
7. Built calculated measures using DAX  

---

## 📏 Key DAX Measures

### Total Customers
```DAX
Total Customers = COUNT(accounts[customer_id])
```

### Total Churn
```DAX
Total Churn = COUNT(churn_data[customer_id])
```

### Churn Rate
```DAX
Churn Rate = DIVIDE([Total Churn], [Total Customers])
```

### Active Customers
```DAX
Active Customers = [Total Customers] - [Total Churn]
```

### Monthly Churn
```DAX
Monthly Churn =
CALCULATE(
    COUNT(churn_data[customer_id]),
    FILTER(
        ALL(churn_data[churn_date]),
        churn_data[churn_date] <= MAX(churn_data[churn_date])
    )
)
```

---

## 📊 Dashboard Features

### KPI Cards
- Total Customers  
- Total Churn  
- Churn Rate  
- Active Customers  
- Revenue Metrics (MRR & ARR)  

### Visualizations Included
- Bar Chart: Churn by Plan Tier  
- Pie Chart: Churn by Country  
- Line Chart: Monthly Churn Trend  
- Area Chart: Active vs Churned Customers  
- Ribbon Chart: Plan Performance Over Time  
- Decomposition Tree: Churn Drivers  
- Support Ticket Analysis  

### Filters Implemented
- Month  
- Plan Tier  
- Country  

---

## 🔍 Key Insights

- Trial users show higher churn rates  
- Certain plan tiers contribute significantly to churn  
- Lower feature usage is associated with increased churn  
- High-priority support tickets indicate potential churn risk  
- Revenue loss is concentrated among premium churned users  

---

## 💡 Business Recommendations

- Improve onboarding experience for trial users  
- Introduce feature adoption campaigns  
- Monitor high-priority support tickets proactively  
- Implement churn prediction alerts  
- Offer retention incentives for high-value customers  

---

## 🚀 Project Outcome

This dashboard enables data-driven decision-making by:

- Identifying churn patterns  
- Monitoring retention health  
- Understanding revenue impact  
- Supporting strategic retention planning  

---

## 📌 Project Details

**Created By:** Jahnavi S T  
**Tool Used:** Power BI Desktop  
