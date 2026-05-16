
# E-Commerce Customer Segmentation using RFM and K-Means

## Project Objective

The objective of this project is to analyze e-commerce transaction data and segment customers using RFM analysis and K-Means clustering.

This helps businesses:
- Identify high-value customers
- Improve customer retention
- Create personalized marketing strategies
- Detect inactive customers

---

# Dataset Description

The dataset contains transaction-level purchase records from an e-commerce business.

## Columns

| Column | Description |
|---|---|
| InvoiceNo | Invoice number |
| StockCode | Product code |
| Description | Product description |
| Quantity | Quantity purchased |
| InvoiceDate | Purchase date |
| UnitPrice | Product price |
| CustomerID | Unique customer ID |
| Country | Customer country |

Each row represents one purchased product in a transaction.

---

# Data Cleaning

The following cleaning operations were performed:

- Removed missing Customer IDs
- Removed missing descriptions
- Removed cancelled invoices
- Removed duplicate records
- Removed negative quantities
- Removed zero/negative prices
- Converted InvoiceDate into datetime format

Final cleaned dataset shape:
```python
```

---

# Feature Engineering

Customer-level features created:

- Total Revenue
- Total Purchases
- Total Quantity Purchased
- Average Order Value
- Unique Products Purchased

## RFM Features

### Recency
how recently the customer made a purchase

### Frequency
how often the customer purchases

### Monetary
how much the customer has spent

---

# Exploratory Data Analysis (EDA)

## 1. Countries Generating Highest Revenue

Findings:
- United Kingdom generated the highest revenue
- India and Germany were also major contributors
- Most revenue came from European countries

### Business Insight
The company should focus marketing efforts on high-performing countries.

---

## 2. Most Sold Products

Findings:
- USB C cable and cotton bedsheet were frequently purchased
- Certain products had very high order quantities

### Business Insight
Popular products should always remain in inventory.

---

## 3. Highest Revenue Products

Findings:
- Bluetooth speaker followed by running shoes and denim jackets generated the highest revenue
- Some products generated high revenue despite lower quantities

### Business Insight
High-revenue products should receive promotional visibility.

---

## 4. Purchase Frequency Distribution

Findings:
- Most customers made only a few purchases
- A small number of customers purchased very frequently

### Business Insight
Frequent customers represent loyal customer segments.

---

## 5. Order Value Distribution

Findings:
- Most orders had low to medium order value
- Few customers generated extremely large orders

### Business Insight
High spenders should receive loyalty rewards.

---

## 6. Outlier Detection

Findings:
- Significant outliers existed in revenue and quantity
- Some customers spent substantially more than average

### Business Insight
Outliers may represent VIP customers or bulk buyers.

---

# K-Means Clustering

## Clustering Steps

1. Selected RFM features
2. Scaled data using StandardScaler
3. Used Elbow Method
4. Applied K-Means clustering
5. Assigned cluster labels

Optimal clusters selected: 
```python
4
```


# cluster interpretation

| Cluster | Characteristics | Customer Type |
|---|---|---|
| 0 | good frequency, high monetary, moderate recency | Promising customers |
| 1 | high frequency and monetary, good recency | loyal and high value Customers |
| 2 | least recency, lowest frequency and monetary value | churned or lost Customers |
| 3 | Low spending and infrequent purchases | One time shoppers |


# Business Recommendations

## Actionable Recommendations for Customer Segments
Based on the K-Means clustering, here are tailored recommendations for each identified customer segment:

Cluster 0: Promising Customers

Goal: Increase purchase frequency and average order value to move them into the 'Loyal & High-Value' segment.

Recommendations:

1)Personalized Product Recommendations: Use past purchase data to suggest complementary or upgraded products.

2)Tiered Loyalty Programs: Offer incentives for reaching a higher spending tier or making a certain number of purchases.

3)Exclusive Previews/Early Access: Provide early access to new products or sales events to make them feel valued.

4)Bundle Deals: Create attractive bundles of products they might be interested in, encouraging higher spending per transaction.

5)Follow-up Campaigns: Send targeted emails after a purchase, asking for reviews and suggesting related items.


Cluster 1: Loyal & High-Value Customers (Champions)

Goal: Retain their loyalty, encourage repeat purchases, and leverage them for advocacy.

Recommendations:

1)Exclusive Loyalty Rewards: Implement a top-tier loyalty program with special benefits, discounts, or services not available to others.

2)VIP Access/Events: Invite them to exclusive events, product launches, or private sales.

3)Personalized Communication: Send personalized thank-you notes or special offers for their birthday/anniversary.

4)Referral Programs: Encourage them to refer new customers by offering generous rewards for successful referrals.

5)Feedback & Co-creation: Involve them in product development or ask for feedback on new services to deepen their sense of ownership and value.


Cluster 2: Churned/Lost Customers

Goal: Attempt to re-engage a portion of these customers, but with a focus on cost-effectiveness.

Recommendations:

1)Win-back Campaigns: Send targeted emails with strong incentives (e.g., significant discounts, free shipping) for their next purchase.

2)Feedback Surveys: Conduct surveys to understand why they stopped purchasing and address potential issues (without expecting high response rates).

3)Low-Cost Re-engagement: Use less intrusive channels like social media retargeting with enticing offers.

4)Sunset Strategy: For those who don't respond to multiple re-engagement efforts, consider removing them from active marketing lists to optimize resources.


Cluster 3: New/One-Time Shoppers (Potential)

Goal: Convert them into repeat buyers and guide them towards becoming 'Promising Customers'.

Recommendations:

1)Onboarding Email Series: Send a series of welcome emails introducing them to the brand, popular products, and key benefits.

2)Second Purchase Incentives: Offer a small discount or free gift with their next purchase to encourage repeat business.

3)Educational Content: Provide helpful guides, tutorials, or tips related to their initial purchase to enhance their experience.

4)Cross-sell Opportunities: Based on their first purchase, recommend complementary products or categories.

5)Feedback Request: Politely ask for feedback on their first purchase experience to address any issues early on.



---

# Conclusion

This project successfully identified meaningful customer segments using RFM analysis and K-Means clustering.

The analysis can help the business:
- Improve customer retention
- Increase marketing effectiveness
- Identify high-value customers
- Personalize customer experience
- Provide discounts 

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

---

# Project Structure

```bash
├── Ecommerce_Customer_Segmentation.ipynb
├── README.md
├── requirements.txt
├── dataset_source.md
├── outputs/
└── images/
```

---

# How to Run

1. Clone repository
2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Open google colab notebook
4. Run all cells sequentially
