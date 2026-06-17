# Analysis-Of-Car-DataSet-using-Python
Data Cleaning and Transformation of car data set and Then exploring data set to ask different questions. Finally Making beautiful visualizations using seaborn and matplotlib. e.g. histograms, Pairplot, bar chart column chart, heatmap, tree map etc
# Let's generate a highly detailed and clean README.md file matching professional repository standards.

readme_content = """# Exploratory Data Analysis (EDA) on Automotive Dataset

This repository contains a comprehensive **Exploratory Data Analysis (EDA)** project focused on identifying key trends, pricing dynamics, and multi-variable correlations within an extensive automotive dataset (`car.csv`). 

Using Python's data science ecosystem (`Pandas`, `NumPy`, `Matplotlib`, and `Seaborn`), the project delivers end-to-end data pipelines starting from raw entry validation up to statistical distribution tracking and matrix visualization.

---

## 📋 Table of Contents
1. [Project Overview](#-project-overview)
2. [Dataset Architecture](#-dataset-architecture)
3. [Data Preprocessing & Cleaning Pipeline](#-data-preprocessing--cleaning-pipeline)
4. [Exploratory Questions Addressed](#-exploratory-questions-addressed)
5. [Key Visualizations & Core Insights](#-key-visualizations--core-insights)
6. [Installation & Execution Guide](#-installation--execution-guide)
7. [Technologies Used](#-technologies-used)

---

## 🔍 Project Overview
The automotive market is governed by a complex interplay of mechanical specifications, brand positioning, and pricing tiers. This project explores these dynamics by cleansing a noisy real-world vehicle dataset and transforming raw numbers into structured business insights. 

### Primary Objectives:
* Identify and rectify missing data gaps and duplicated records.
* Restructure column attributes for clean programming references.
* Evaluate brand volume distributions to locate top market players.
* Trace correlations between mechanical parameters (Engine HP, Cylinders) and consumer costs (MSRP).

---

## 📊 Dataset Architecture
The initial `car.csv` data layout contains **11,914 rows** and **16 features**:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Make` | Object | Manufacturer brand name (e.g., BMW, Audi, Toyota) |
| `Model` | Object | Vehicle model line moniker |
| `Year` | Int64 | Release / production calendar year |
| `Engine Fuel Type` | Object | Type of fuel required/recommended |
| `Engine HP` | Float64 | Engine horsepower rating |
| `Engine Cylinders` | Float64 | Total combustion cylinders count |
| `Transmission Type` | Object | Transmission system (Automatic, Manual, etc.) |
| `Driven_Wheels` | Object | Drivetrain layout (Rear, Front, All-Wheel Drive) |
| `Number of Doors` | Float64 | Count of vehicle doors |
| `Market Category` | Object | Market classification tags (Luxury, Performance, Crossover) |
| `Vehicle Size` | Object | Size metric category (Compact, Midsize, Large) |
| `Vehicle Style` | Object | Structural design (Coupe, Convertible, Sedan, SUV) |
| `highway MPG` | Int64 | Fuel economy achieved on highways |
| `city mpg` | Int64 | Fuel economy achieved within city limits |
| `Popularity` | Int64 | Normalized brand trend score metric |
| `MSRP` | Int64 | Manufacturer's Suggested Retail Price (Target USD Value) |

---

## 🛠️ Data Preprocessing & Cleaning Pipeline

The raw file required structured optimization before reliable insights could be extracted. The following steps are automated within `EDA Using Python.ipynb`:

1. **Dimensional Analysis:** Checks initial grid bounds (`.shape`) and value types (`.info()`).
2. **Handling Null Values:** Pinpoints feature missingness. Features like `Engine HP`, `Engine Cylinders`, and `Market Category` contained extensive nulls. Missing attributes are eliminated using `dropna(inplace=True)` to preserve absolute mathematical data integrity.
3. **De-duplication:** Tracks and expels repeating multi-column blocks to prevent skewed descriptive statistics via `.drop_duplicates()`.
4. **Feature Simplification:** Trims redundant/sparse dimensions (`Engine Fuel Type`, `Market Category`, `Vehicle Style`, `Popularity`, `Number of Doors`, `Vehicle Size`).
5. **Standardized Renaming:** Translates mixed-case variables to structured, clean titles:
   * `Engine HP` $\\rightarrow$ `HP`
   * `Engine Cylinders` $\\rightarrow$ `Cylinders`
   * `Transmission Type` $\\rightarrow$ `Transmission`
   * `Driven_Wheels` $\\rightarrow$ `Drive Mode`
   * `highway MPG` $\\rightarrow$ `MPG-H`
   * `city mpg` $\\rightarrow$ `MPG-C`
   * `MSRP` $\\rightarrow$ `Price`

---

## ❓ Exploratory Questions Addressed

The implementation includes specific programmatic masks to answer key exploratory questions:
* **Brand Dispersion:** Which manufacturer rules the production index by volume?
* **Model Frequency:** What specific car model series appears most frequently in market listings?
* **Transmission Partitioning:** How do automatic transmissions stack up against manuals when indexed against performance parameters?
* **Target Segments:** Isolating subsets (e.g., filtering out custom data frames specifically for `BMW` or `Audi` fleets) to trace high-end performance groupings.

---

## 📈 Key Visualizations & Core Insights

### 1. Feature Correlation Heatmap
A matrix tracking how mathematical attributes behave relative to one another.

![Vehicle Correlation Matrix](https://github.com/sadaatalsyed/Python_Projects_and_Scripts/blob/main/EDA_Cars/Heatmap.png)

* **Insight:** Horsepower (`HP`) and `Cylinders` show an extremely strong positive correlation with a vehicle's `Price`. Conversely, fuel efficiency metrics (`MPG-H`, `MPG-C`) exhibit a significant negative correlation with engine size and horsepower—confirming the performance-for-efficiency tradeoff.

### 2. Market Capitalization by Volume (Top Manufacturers)
A bar ranking illustrating the density of vehicle makes in the data workspace.

![Top Manufacturers](https://github.com/sadaatalsyed/Python_Projects_and_Scripts/blob/main/EDA_Cars/Top%20Manufacturers.png)

* **Insight:** Chevrolet, Ford, and Volkswagen hold massive volume counts within the dataset. Luxury segments like BMW and Audi maintain a notable footprint but are clustered at tightly defined performance distributions.



---

## 🚀 Installation & Execution Guide

### Prerequisites
Ensure your local workspace runs Python 3.8+ along with the required libraries.
