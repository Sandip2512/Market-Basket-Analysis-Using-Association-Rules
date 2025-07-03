# 🛒 Market Basket Analysis Using Association Rules

## 📘 Overview
This project applies **Market Basket Analysis** on a real-world retail transaction dataset using the **Apriori algorithm** to uncover frequently bought product combinations and generate **association rules**. These insights help in product bundling, personalized recommendations, and sales strategy optimization.

---

## 📊 Dataset Description

- **Dataset:** `online_retail.csv`  
- **Type:** E-commerce transaction data  
- **Rows:** 541,909  
- **Columns:** 8  
- **Key Features:**
  - `InvoiceNo` – Transaction ID
  - `StockCode` – Product code
  - `Description` – Product name
  - `Quantity` – Items purchased
  - `InvoiceDate` – Date of transaction
  - `UnitPrice` – Price per item
  - `CustomerID` – Unique customer identifier
  - `Country` – Customer location

---

## 🎯 Project Objective

- Identify frequently purchased product sets.
- Generate strong association rules using **Apriori**.
- Discover valuable product relationships to support cross-selling.
- Visualize the top rules for easier business interpretation.

---

## 🔁 Methodology

### 1. **Data Preprocessing**
- Loaded data using `pandas`.
- Removed missing values and filtered invalid transactions (e.g., negative quantities).
- Limited analysis to transactions from the **United Kingdom**.
- Converted transactional data into a **basket matrix** format for rule mining.

### 2. **Frequent Itemset Mining**
- Used `mlxtend.apriori()` with `min_support=0.01` to find frequent itemsets.
- Extracted combinations of products purchased together with statistical significance.

### 3. **Association Rule Generation**
- Applied `association_rules()` with filters:
  - **Confidence > 50%**
  - **Lift > 1.2**
- Calculated metrics: support, confidence, and lift for each rule.

### 4. **Visualization**
- Created a **bar plot** showing top 10 rules by lift, annotated with support and confidence.
- Used `textwrap` and `matplotlib` to handle long item names cleanly.
- (Optional) Generated a **network graph** of top product associations using `networkx`.

---

## 📌 Key Insights

The analysis revealed strong purchasing patterns among certain products:

| Antecedent(s)                              | Consequent(s)                           | Confidence | Lift  |
|-------------------------------------------|-----------------------------------------|------------|-------|
| PLASTERS IN TIN SPACEBOY                  | PLASTERS IN TIN CIRCUS PARADE           | 85.0%      | 2.30  |
| JUMBO BAG RED RETROSPOT                   | JUMBO BAG PINK POLKADOT                 | 77.2%      | 2.04  |
| SET/6 RED SPOTTY PAPER PLATES             | SET/6 RED SPOTTY PAPER CUPS             | 78.3%      | 2.11  |
| LUNCH BAG SPACEBOY DESIGN                 | LUNCH BAG RED RETROSPOT                 | 72.5%      | 1.95  |
| SET/20 RED RETROSPOT PAPER NAPKINS        | SET/6 RED SPOTTY PAPER CUPS             | 70.2%      | 1.85  |

### 💡 Interpretation
- Products with **similar themes or designs** (e.g., "Retrospot", "Spaceboy") are often bought together.
- **High lift values** (e.g., >2.0) suggest these co-purchases are non-random and highly valuable for targeting.

---

## ✅ Conclusion

The Apriori-based Market Basket Analysis uncovered strong product relationships that retailers can use to:

- Design **combo offers** or **bundle deals**
- Create **personalized product recommendations**
- Optimize **store layout** or **e-commerce suggestions**
- Improve **inventory planning** for co-purchased products

These insights are directly applicable to marketing and sales teams in retail or e-commerce settings.

---

## ▶️ How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/Sandip2512/market-basket-analysis.git
   cd market-basket-analysis
