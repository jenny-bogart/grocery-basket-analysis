## Grocery Store Market Basket Analysis

### Problem Statement
Retailers want to understand which products are commonly bought together to optimize product placement, customer recommendations, and promotions. This project analyzes grocery transaction data to uncover underlying purchasing trends and show the likelihood of a customer purchasing a product and purchasing additional products

### Dataset
The dataset I used contains transaction data from 2023-2025 from a multi location grocery chain. Each row represents an item purchased in a transaction, including transaction date, product information, and quantity.

Source: Kaggle - Groceries Market Basket Dataset
https://www.kaggle.com/datasets/irfanasrullah/groceries

### Goals
My goals of this project are to:
- Clean and preprocess raw transaction data
- Explore purchasing behavior and basket composition
- Identify frequently purchased item combinations
- Model cross-selling opportunities using association rules
- Demonstrate how insights could be used for recommendations

### Methods
- Exploratory Data Analysis
- Market basket analysis (association rule mining)
- Customer segmentation

### Tools
- Python
- Pandas, NumPy
- mlxtend
- Matplotlib / Seaborn
- Google Colab

### Project Structure
grocery-basket-analysis/
├── data/
│ ├── raw/
│ ├ |── groceries - groceries.csv
│ ├ |── README.me
│ └── processed/
│ ├ |── README.me
│ ├ |── categories - test.csv
│ ├ |── grocery_transactions_clean.csv
│ ├ |── transactions_clean.pkl
├── notebooks/
│ ├── 01_data_cleaning.ipynb
│ └── 02_grocery_eda.ipynb
│ └──03_market_basket_analysis.ipynb
└── README.md

### Project Status
- [x] Data cleaning
- [x] Exploratory data analysis
- [x] Association rule mining
- [x] Modeling and evaluation

### Key Insights
- Customers rarely purchase vegetables in isolation; produce purchases occur in clusters.

- Root vegetables and other vegetables have a consistently high lift (>1.4), indicating strong co-purchasing behavior beyond random chance.

- Dairy items (milk, yogurt) frequently appear alongside produce, suggesting cross-department promotion opportunities.

- High-lift rules often have moderate support, highlighting that valuable insights can exist outside top-frequency items.

- Customers exhibit basket complementation, not impulse add-ons.

- Vegetable purchasing reflects meal planning behavior, not single-item needs.

- High confidence does not imply high lift → frequent items inflate confidence.

- Lift proved to be the most reliable metric for identifying non-obvious relationships.

- Rule stability across random samples suggests patterns are structural, not noise.

- Rules that appeared in ≥7 randomized samples were significantly more consistent than others. This supports that discovered associations are generalizable, not artifacts of a specific sample.

- Apriori analysis is more useful than another unsupervised method because it captures all the rules, even if they appear in only a small amount of transaction. Most customers buy things like bread, milk, vegetables, etc. which could skew the clustering results

### Business Recommendations
- Bundle root vegetables with leafy greens at a 5–10% discount

- Place dairy adjacently to produce sections

- Use high-lift, low-support rules for targeted coupons, not store-wide promotions

### Future Work
- Segment rules by customer type

- Time-based basket analysis (weekday vs weekend)

- Profit-weighted association rules

- Use rules as features for recommendation systems
