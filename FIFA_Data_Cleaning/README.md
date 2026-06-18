# ⚽ FIFA 21 Data Cleaning & Transformation Project

## 📌 Project Overview
This repository contains a comprehensive, end-to-end data cleaning and transformation pipeline applied to the messy **FIFA 21 Raw Dataset** (containing 18,979 player records and 77 attributes). Using Python and Pandas, the raw, unformatted, and inconsistently structured text data was transformed into a standardized, analysis-ready format ideal for SQL ingestion or BI dashboarding.

Data cleaning is a critical step in the Analytics Engineering workflow. This project demonstrates advanced data manipulation techniques, handling of complex string formatting, currency conversions, and structural reshaping.

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python
* **Library:** Pandas, NumPy
* **Environment:** Jupyter Notebook / Anaconda

---

## 🔍 Data Cleaning Challenges & Solutions

Here is the step-by-step breakdown of the data transformation processes executed in the notebook:

### 1. Height and Weight Normalization
* **Issue:** The `Height` column contained text values like `170cm` or imperial measurements (e.g., `5'11"`), and `Weight` had suffixes like `72kg` or `lbs`.
* **Solution:** Stripped text characters, identified differing units, converted all measurements into standard numeric columns, and renamed the headers to `Height(cm)` and `Weight(kg)` for strict schema enforcement.

### 2. Contract Status Segmentation
* **Issue:** The `Contract` column was a highly inconsistent string column containing year ranges (`2004 ~ 2021`), loan texts (`Jun 30, 2021 On Loan`), or `Free`.
* **Solution:** Parsed the column into four clear, analytic fields:
  * `Contract Start` & `Contract End` (extracted numeric years)
  * `Contract Length(years)` (calculated field)
  * `Contract Status` (Categorized into *Contact*, *On Loan*, or *Free*)

### 3. Financial Columns Standarization (`Value`, `Wage`, `Release Clause`)
* **Issue:** Financial fields were stored as string text prefixed with Euros (`€`) and suffixed with `M` (Millions) or `K` (Thousands) (e.g., `€103.5M`, `€560K`).
* **Solution:** Wrote a robust custom cleaning function to strip symbols, multiply suffix-based numeric scales (`M` by 1,000,000 and `K` by 1,000), and cast the columns into continuous `float64`/`int64` datatypes.

### 4. Player Performance Metrics (`Hits`)
* **Issue:** The `Hits` metric contained string characters like `K` for thousands and `NaN` values for players with no profile hits.
* **Solution:** Created a transformation script to clean string values, fill structural blanks securely, and cast the column into proper numeric types.

### 5. Cleaning Special Characters (`W/F`, `SM`, `IR`)
* **Issue:** Categorical ratings columns representing star counts (Weak Foot, Skill Moves, International Reputation) contained a special star symbol character (`★`).
* **Solution:** Cleaned and stripped out the `★` character across all columns, casting them into numeric categories for smoother aggregation.

---

## 📁 Repository Structure

```text
├── FIFA21 Data Cleaning.ipynb   # Main Jupyter notebook containing documented Pandas code
├── fifa21 raw data v2.csv       # Messy, uncleaned original dataset
├── fifa21 cleaned output.csv    # Transformed, ready-to-load output dataset
└── README.md                    # Project documentation
