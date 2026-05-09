# 🛒 Market Basket Analysis

> An end-to-end retail data analysis project using Python and Power BI — covering sales trends, customer segmentation, RFM scoring, product recommendations, and association rule mining on real-world e-commerce transaction data.

---

## 📁 Project Structure

Market-Basket-Analysis/
│
├── Basket_Analysis.ipynb         # Main Jupyter Notebook (full analysis)
├── Basket_Analysis.pbix          # Power BI Dashboard (3 pages)
├── online_retail.csv             # Dataset (541K+ transactions)
├── screenshots/
│   ├── page1_overview.png        # Dashboard Page 1
│   ├── page2_daily_trend.png     # Dashboard Page 2
│   └── page3_yearly_growth.png   # Dashboard Page 3
└── README.md

---

## 📊 Dashboard Preview

### Page 1 – Sales Overview
![Sales Overview](screenshots/page1_overview.png)

### Page 2 – Daily Sales Trend
![Daily Trend](screenshots/page2_daily_trend.png)

### Page 3 – Yearly Growth
![Yearly Growth](screenshots/page3_yearly_growth.png)

---

## 📂 Dataset

| Column | Description |
|---|---|
| `InvoiceNo` | Unique transaction identifier |
| `StockCode` | Product/item code |
| `Description` | Product name |
| `Quantity` | Number of units purchased |
| `InvoiceDate` | Date and time of transaction |
| `UnitPrice` | Price per unit (GBP) |
| `CustomerID` | Unique customer identifier |
| `Country` | Customer's country |

- **Source:** UCI Machine Learning Repository — Online Retail Dataset
- **Period:** December 2010 – December 2011
- **Records:** 541,000+ transactions
- **Countries:** 37+
- **Primary Market:** United Kingdom

---

## 🔬 Analysis Performed (Jupyter Notebook)

### 1. 🧹 Data Cleaning & Preprocessing
- Handled missing values (`dropna`)
- Parsed `InvoiceDate` to datetime format
- Filtered out negative quantities (returns) and zero unit prices
- Created `TotalPrice = Quantity × UnitPrice`
- Filtered UK-specific data for focused analysis

### 2. 📈 Exploratory Data Analysis (EDA)
- Monthly sales trend visualization
- Sales by **Hour of Day** and **Day of Week**
- Top 20 selling products by quantity
- Transaction count per country
- Average Order Value (AOV) calculation

### 3. 👥 Customer Segmentation
- Customer spending quantile tiers: `Low`, `Medium`, `High`, `Very High`
- Purchase frequency distribution
- Top 20 customers by total spending

### 4. 🏆 RFM Analysis
Built a full **Recency, Frequency, Monetary** scoring model:

| Metric | Description |
|---|---|
| **Recency** | Days since last purchase |
| **Frequency** | Number of unique invoices |
| **Monetary** | Total amount spent |

- Customers scored on a 1–4 scale per dimension
- RFM Score combined (e.g., `444` = top segment, `111` = churn risk)
- **Customer Lifetime Value (CLV)** calculated as `Frequency × Monetary / Recency`

### 5. 📦 Product Analysis
- Top 10 products by quantity sold (interactive Plotly bar chart)
- Top 10 products by number of unique customers
- Product return rate analysis
- Monthly return trends

### 6. 🤝 Association Rule Mining (Market Basket)
- Used **Apriori algorithm** (`mlxtend`) to find frequent itemsets
- Generated **association rules** with support, confidence, and lift metrics
- Identified which products are commonly bought together

### 7. 🧠 Product Recommendation (Word2Vec)
- Trained a **Word2Vec model** on customer purchase sequences
- Built a `similar_products()` function to find products similar to a given item
- Built an `aggregate_vectors()` function for basket-level recommendations
- Train/validation split: 90% / 10% of customers

---

## 📊 Power BI Dashboard

The dashboard has **3 interactive pages** built on the same dataset:

| Page | Content |
|---|---|
| **Page 1** | KPI cards (2.50M unit price, 541K invoices), quantity by country bar chart, monthly country distribution pie chart, quarter filter |
| **Page 2** | Daily unit price bar chart (Dec 2010 – Jan 2011), country slicer for drill-down |
| **Page 3** | Year-over-year unit price line chart (2010 → 2011) showing clear upward growth |

---

## 🔍 Key Findings

- 🇬🇧 **United Kingdom** accounts for the vast majority of all transactions
- 📈 **Revenue nearly tripled** from 2010 to 2011, showing strong YoY growth
- ⏰ Peak shopping hours and days identified for targeted marketing
- 🏅 Top customer segments (`RFM = 444`) identified for loyalty programs
- ⚠️ Churn-risk customers (`RFM = 111`) flagged for re-engagement campaigns
- 🛍️ Frequently co-purchased products identified for bundle recommendations
- 🤖 Word2Vec model enables personalized product recommendations per customer basket

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **Python 3** | Core analysis language |
| **Pandas / NumPy** | Data manipulation |
| **Matplotlib / Seaborn** | Static visualizations |
| **Plotly Express** | Interactive charts |
| **mlxtend** | Apriori + Association Rules |
| **Gensim Word2Vec** | Product recommendation model |
| **tqdm** | Progress tracking |
| **Power BI Desktop** | Business intelligence dashboard |

---


## 👨‍💻 Author

**Kavikumar**
- GitHub: [@kavikumar03](https://github.com/kavikumar03)

---
## 📄 License

This project is open source and available under the [MIT License](LICENSE).

