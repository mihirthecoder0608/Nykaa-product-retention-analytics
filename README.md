# Nykaa Product Retention & Customer Lifetime Value (LTV) Analytics

## 1. Project Overview

Customer retention and repeat purchase velocity are vital drivers of profitability in e-commerce.

This project analyzes transactional customer data for Nykaa to uncover retention bottlenecks, understand purchasing behavior, segment customers by value, and identify opportunities to maximize Customer Lifetime Value (LTV).

The project integrates **MySQL, Python, and Power BI** to transform raw transactional data into actionable product and business recommendations.

## 2. Business Objectives

- Measure overall customer retention rates and month-over-month cohort decay.
- Identify customer segments using Recency, Frequency, and Monetary (RFM) analysis.
- Analyze category reorder intervals to determine optimal replenishment timing.
- Evaluate acquisition and retention channels for high-LTV customer concentration.
- Prioritize product features and retention interventions using the RICE framework.
- Build interactive Power BI dashboards for retention monitoring and executive reporting.

## 3. Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data cleaning, exploratory data analysis (EDA), and inter-purchase interval calculations |
| Pandas and NumPy | Data manipulation and statistical analysis |
| Matplotlib and Seaborn | Exploratory data visualization |
| Jupyter Notebook | Analysis documentation and execution |
| MySQL Workbench | Schema setup, cohort matrices, and RFM queries using CTEs and window functions |
| Power BI | Interactive retention dashboards and DAX-based KPI reporting |

## 4. Dataset

The project uses the **Nykaa Product Retention & LTV transactional dataset**.

- **Total records:** 10,000 orders
- **Unique customers:** 2,451
- **Database table:** `nykaa_retention_data`
- **Primary attributes:** `Order_ID`, `User_ID`, `Order_Date`, `Order_Value`, `Category`, and acquisition channel/customer attributes.

The dataset captures multi-category purchases across Skincare, Makeup, Haircare, Personal Care, and Fragrance, enabling customer-level retention, purchasing frequency, and category-level behavioral analysis.

## 5. Project Workflow

1. **Data Inspection:** Examine transaction logs, date formats, and schema consistency.
2. **Data Cleaning and ETL:** Convert date formats, fix safe update issues, and prepare the dataset for MySQL analysis.
3. **Exploratory Analysis:** Evaluate order frequency, spending distributions, category performance, and purchasing behavior.
4. **SQL Analysis:** Construct cohort matrices using `TIMESTAMPDIFF()` for monthly cohorts and CTEs/window functions for RFM segmentation.
5. **Dashboard Development:** Build interactive Power BI dashboards covering retention, customer segmentation, and category/channel dynamics.
6. **Product Roadmap:** Apply the RICE framework to prioritize retention features and interventions.

## 6. Key Findings

### Overall Retention & Cohort Decay

- **Total orders analyzed:** 10,000
- **Total unique customers:** 2,451
- **Month 1 retention drop-off:** Approximately 75%
- **Long-term baseline retention:** Approximately 20–28%, stabilizing from Month 2 onward.

The early retention decline highlights an opportunity to improve the post-purchase customer experience through timely replenishment reminders, personalized engagement, and targeted reactivation campaigns.

### RFM Customer Segmentation

| Customer Segment | User Count | % of Users | Avg. Orders / User | Key Characteristic |
|---|---:|---:|---:|---|
| Loyal Repeat Buyers | 1,273 | 51.9% | 5.3 | Steady core revenue backbone |
| Occasional Shoppers | 615 | 25.1% | 2.8 | High potential for loyalty conversion |
| At Risk / Churned | 420 | 17.1% | 1.8 | Inactive for more than 120 days |
| Champions / Privé VIPs | 143 | 5.9% | 8.2 | Spend above ₹13,900 per customer |

**Key takeaway:** Loyal repeat buyers form the largest customer segment, while Champions / Privé VIPs represent a smaller, high-value group that deserves differentiated loyalty benefits. At-risk customers offer an opportunity for targeted win-back campaigns.

### Category Reorder Clock

| Category | Order Volume | Median Reorder Interval |
|---|---:|---:|
| Skincare | 3,900 | 47 days |
| Makeup | 3,000 | 52 days |
| Personal Care | 1,500 | 48 days |
| Haircare | 1,100 | 60 days |
| Fragrance | 500 | 90 days |

Skincare and Makeup account for approximately **69% of total platform order volume**.

The category-level reorder intervals provide a basis for designing replenishment reminders around customers' observed purchasing cycles rather than relying on a single generic reminder schedule.

### Channel Performance

- **App Push and Organic Search:** Generate the highest overall transaction volumes.
- **WhatsApp Nudges:** Deliver the highest concentration of Privé VIP members, making WhatsApp a promising channel for targeted engagement.

These findings suggest that acquisition volume and high-value customer conversion should be evaluated separately when allocating marketing and retention resources.

## 7. Power BI Dashboard

The Power BI report contains three analytical pages.

### Retention & Cohorts

- Active-user retention matrix by acquisition month.
- Month-over-month cohort decay trends.
- Reorder velocity across user cohorts.

### RFM Customer Segmentation

- User distribution across RFM tiers.
- Monetary value contribution by segment.
- Recency vs. Frequency cross-filtering.

### Category & Channel Dynamics

- Category order volume and average order value (AOV).
- Median replenishment cycles per category.
- Acquisition channel distribution and Privé VIP penetration.

**How to interact with the dashboard:** Download the `.pbix` file from this repository and use the interactive slicers for Category, Channel, and Privé membership status.

## 8. Business Recommendations

### 1. Automated Category Replenishment Alerts

Trigger automated WhatsApp or app push reorder reminders around the observed replenishment window for Skincare, Makeup, and other repeat-purchase categories.

**Expected outcome:** Improve repeat purchase rates by reaching customers when they are more likely to need a replenishment.

### 2. Targeted WhatsApp Re-engagement for Occasional Shoppers

Leverage WhatsApp nudges, identified as a promising channel for Privé VIP engagement, to encourage occasional shoppers to make repeat purchases and progress toward loyalty milestones.

**Expected outcome:** Improve repeat purchase frequency and increase the conversion of occasional shoppers into loyal customers.

### 3. Proactive Win-Back Campaigns for At-Risk Users

Deploy targeted reactivation campaigns for the At-Risk / Churned segment (17.1% of customers), prioritizing users whose inactivity exceeds 120 days.

Potential interventions include personalized product recommendations, category-specific offers, and carefully targeted discounts.

**Expected outcome:** Recover inactive customers while controlling unnecessary discount expenditure.

### 4. Privé VIP Loyalty Gamification

Introduce tiered reward milestones for Champions / Privé VIPs (5.9% of customers) to encourage continued engagement and protect high-value customer relationships.

Potential features include exclusive rewards, early access to launches, and personalized benefits.

**Expected outcome:** Strengthen loyalty and encourage continued spending among high-value customers.

## 9. Feature Prioritization (RICE Framework)

The RICE framework prioritizes product initiatives based on Reach, Impact, Confidence, and Effort.

**Formula:**

RICE Score = (Reach × Impact × Confidence) / Effort

| Feature / Initiative | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---|---:|---:|---:|---|---:|---|
| Automated Category Replenishment Nudges | 2,000 | 3.0 | 90% | 2 weeks | 2,700 | High |
| Privé VIP Loyalty Gamification | 2,000 | 2.0 | 90% | 4 weeks | 900 | Medium |
| Personalized Shade & Skin Profiler | 1,000 | 3.0 | 80% | 6 weeks | 400 | Low |

*Note: RICE scores are calculated using effort expressed in weeks. Reach, impact, confidence, effort, and priority should be validated against the final project calculations before using them for actual product decisions.*

Automated replenishment nudges emerge as the first initiative to test because of their potential reach, relatively low implementation effort, and direct connection to observed reorder behavior.

## 10. Repository Structure

The repository is organized as follows:

```text
Nykaa-Product-Retention-Analytics/
│
├── data/
│   └── nykaa_retention_data.csv
│
├── queries.sql
├── retention_analysis.ipynb
├── dashboard_screenshot.png
├── README.md
└── .gitignore
```

## 11. How to Run and Explore

### SQL Analysis — MySQL Workbench

1. Open MySQL Workbench and create a database:

   ```sql
   CREATE DATABASE nykaa_db;
   USE nykaa_db;
   ```

2. Import `nykaa_retention_data.csv` using the Table Data Import Wizard into a table named `nykaa_retention_data`.

3. Open and run `queries.sql` to execute the schema setup, cohort matrices, and RFM queries.

### Python Analysis — Jupyter Notebook

1. Download or clone this repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Open `retention_analysis.ipynb` in Jupyter Notebook and run all cells.

### Power BI Report

1. Open the Power BI project file (`.pbix`) if included in the repository.
2. If required, configure the data source and refresh the dataset.
3. Interact with the report using the Category, Channel, and Privé membership slicers.

The dashboard screenshot is provided for a quick visual preview. A screenshot alone does not provide interactive Power BI functionality.

## 12. Limitations

- The analysis describes transactional patterns in the dataset and does not establish strict causality.
- External promotional events and marketing campaign spend data were not included in the dataset.
- Customer purchase behavior may change over time, so historical reorder intervals should not be treated as fixed rules.
- Recommendations should be validated through A/B testing before full platform rollout.
- RFM segments and estimated customer value depend on the available transaction history and the chosen analysis period.

## 13. Conclusion

This project demonstrates how **MySQL, Python, and Power BI** can be unified to address e-commerce customer retention challenges.

By transforming 10,000 order records into cohort analyses, RFM segments, category-level reorder insights, and channel performance comparisons, the project provides a data-driven roadmap for reducing churn and maximizing Customer Lifetime Value (LTV).

The analysis highlights opportunities to improve replenishment timing, convert occasional shoppers into loyal customers, reactivate at-risk users, and strengthen relationships with high-value Privé VIPs.

The resulting recommendations connect customer behavior to actionable product initiatives, with the RICE framework helping prioritize implementation efforts.

---

## Author
**Mihir  Mishra**

[Linkedin](https://www.linkedin.com/in/mihirmishra74638ghy)
[Email](mihirmishra006@gmail.com)

**Skills Demonstrated:** Data Cleaning · Cohort Retention Analysis · RFM Segmentation · SQL (CTEs, Window Functions) · Python · Power BI · RICE Framework Prioritization

