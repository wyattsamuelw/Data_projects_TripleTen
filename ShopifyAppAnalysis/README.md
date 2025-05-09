
# Shopify App Analysis: Insights & Dashboards

## **Project Overview**  
This Power BI project explores the **Shopify app ecosystem** using publicly scraped data from the Shopify App Store. The goal is to understand the key factors that contribute to app success, such as review volume, developer engagement, and app quality across different developers and categories.

**View the PowerBI Report :** [ShopifyReport](https://drive.google.com/file/d/1ubC2tx7Pjq_HKV9V6R2vrK5shT03D35Z/view?usp=sharing)  


---

## **Data Source:**  
**shopify.xlsx**  
The dataset includes the following tables:
- `apps`: Metadata about apps, including developer, rating, and review count
- `reviews`: Individual user reviews with rating, helpful votes, and developer replies
- `apps_categories`: Join table connecting apps to their categories
- `categories`: Names and descriptions of each category

---

## **Report Pages and Key Visuals**

### **1. App Landscape**
- **KPI Card**: Total number of unique apps (7,341)
- **Line Chart**: Trend of total reviews over time based on `lastmod` date
- **Scatterplot**: `reviews_count` vs. `average rating`, annotated with insights:
  > "Apps with more reviews tend to have higher average ratings. Most cluster under 5K reviews, but even the most-reviewed apps maintain strong ratings. Popularity and quality appear to go hand-in-hand."

---

### **2. Reviews**
- **New DAX Column**: `helpful_reviews = rating * (1 + helpful_count)`
- **KPI Card**: Average of `helpful_reviews` (~5.48)
- **New DAX Column**: `developer_answered = IF(ISBLANK(developer_reply), 0, 1)`
- **Scatterplot**: Average rating vs. developer reply status

---

### **3. App Reviews**
- **New Relationship**: `reviews[app_id]` → `apps[id]` (Many-to-One)
- **Bar Chart**: Sum of ratings by developer (raw volume)
- **Bar Chart**: Average `helpful_reviews` by developer (quality-weighted)
- **Bar Chart**: Developer responsiveness (average of `developer_answered`), filtered to apps with over 500 reviews

---

## **Insights**
- Developers with the highest volume of reviews aren't always the most helpful or responsive.
- Many high-quality apps maintain high average ratings, even with large review counts.
- Some developers consistently respond to users, correlating with slightly higher average ratings.

---

### **Included Files**
- `shopify.xlsx`: Source dataset (not included in ZIP due to file size limits — 10MB max)
- `1.1.jpg`: KPI Card – Total number of unique apps
- `1.2.jpg`: Line Chart – Review count over time (lastmod date)
- `1.3.jpg`: Scatterplot – Reviews count vs. average rating with interpretation
- `2.1.jpg`: KPI Card – Average of helpful_reviews (DAX column)
- `2.2.jpg`: Scatterplot – Avg. rating by developer reply status (developer_answered)
- `3.1.jpg`: Bar Chart – Sum of ratings by developer
- `3.2.jpg`: Bar Chart – Average helpful_reviews by developer
- `3.3.jpg`: Bar Chart – Developer responsiveness (filtered to reviews_count > 500)
- **README.md** (this file)  


**Created by:** Sam Wyatt  
**Date:** 4/9/2025  
**Contact:** wyattsamuelw@gmail.com  
