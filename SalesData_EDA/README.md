# 🪔 Diwali Sales Analysis

An exploratory data analysis (EDA) project examining consumer purchasing behaviour during the Diwali festival season. The analysis uncovers patterns across demographics, geography, and product categories to identify the most valuable customer segments.

---

## 📁 Repository Structure

```
├── Diwali Sales Data.csv      # Raw sales dataset (~11,250 records)
├── Sales_Analysis.ipynb       # Jupyter notebook with full EDA
└── README.md
```

---

## 📊 Dataset Overview

| Attribute | Details |
|-----------|---------|
| **Rows** | ~11,250 transactions |
| **Columns** | 13 (after cleaning) |
| **Source** | Diwali festival retail sales |

### Key Columns

| Column | Description |
|--------|-------------|
| `User_ID` | Unique customer identifier |
| `Cust_name` | Customer name |
| `Product_ID` | Unique product identifier |
| `Gender` | Customer gender (M/F) |
| `Age Group` | Age bracket (0-17, 18-25, 26-35, 36-45, 46-50, 51-55, 55+) |
| `Age` | Customer age |
| `Marital_Status` | 0 = Single, 1 = Married |
| `State` | Indian state of the customer |
| `Zone` | Geographic zone (Northern, Southern, Eastern, Western, Central) |
| `Occupation` | Customer's profession |
| `Product_Category` | Category of purchased product |
| `Orders` | Number of orders placed |
| `Amount` | Total purchase amount (INR) |

---

## 🔧 Data Cleaning Steps

- Dropped empty/irrelevant columns (`Status`, `unnamed1`)
- Removed rows with null values in the `Amount` column
- Converted `Amount` column from float to integer
- Final cleaned dataset shape: **~11,239 rows × 13 columns**

---

## 🔍 Exploratory Data Analysis

The notebook analyzes sales patterns across five dimensions:

### 1. Gender
- Female customers outnumber male customers significantly
- Female buyers also generate **higher total revenue** than male buyers

### 2. Age Group
- The **26–35 age group** dominates both order count and total spend
- Female customers in this bracket are the single largest buying segment

### 3. State / Geography
- Top states by order volume and revenue:
  1. **Uttar Pradesh**
  2. **Maharashtra**
  3. **Karnataka**

### 4. Marital Status
- **Married women** are the highest-spending customer group, with greater purchasing power than their single or male counterparts

### 5. Occupation
- Buyers predominantly work in:
  - **IT Sector**
  - **Healthcare**
  - **Aviation**

### 6. Product Category
- Top-selling categories by revenue:
  1. **Food**
  2. **Clothing**
  3. **Electronics**

---

## ✅ Conclusion

> *Married women aged 26–35 from Uttar Pradesh, Maharashtra, and Karnataka — working in IT, Healthcare, or Aviation — are the most likely buyers of Food, Clothing, and Electronics during Diwali.*

This customer profile represents the highest-value target segment for Diwali marketing campaigns.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Core language |
| pandas | Data manipulation & aggregation |
| NumPy | Numerical operations |
| Matplotlib | Base plotting |
| Seaborn | Statistical visualizations |
| Jupyter Notebook | Interactive analysis environment |

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the Notebook
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
jupyter notebook Sales_Analysis.ipynb
```

---

## 📌 Visualizations in the Notebook

- Bar chart: Gender vs. order count
- Bar chart: Gender vs. total sales amount
- Grouped bar chart: Age group vs. count, segmented by gender
- Bar chart: Age group vs. total amount
- Bar chart: Top 10 states by orders and revenue
- Bar chart: Marital status vs. count and amount by gender
- Bar chart: Occupation vs. count and revenue
- Bar chart: Product category vs. count and revenue
- Bar chart: Top 10 most ordered products by Product ID

---

## 🙏 Acknowledgements

Original project tutorial by [Rishabh Mishra](https://github.com/rishabhnmishra/Python_Diwali_Sales_Analysis).
