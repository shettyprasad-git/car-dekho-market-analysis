# Car Market Trends Analysis with Car Dekho Data

> **End-to-End Data Analytics Mini Project**  
> Data Exploration • Data Cleaning • Feature Engineering • EDA • Visualization • Correlation Analysis • Outlier Analysis • Business Insights

## 📌 Project Overview

This project presents an end-to-end analysis of the **Car Dekho used-car dataset** to understand the factors associated with vehicle selling prices and resale value.

The analysis follows a complete data analytics workflow: **data exploration, data-quality validation, cleaning, feature engineering, exploratory analysis, visualization, correlation analysis, outlier investigation, and business recommendations**.

The project is intended to support data-informed decisions for **used-car buyers, sellers, dealers, automotive analysts, and business teams**.

## 🎯 Problem Statement

The used-car market shows significant variation in resale prices based on factors such as **vehicle age, present price, kilometers driven, fuel type, transmission, seller type, and previous ownership**.

The objective is to analyze the Car Dekho dataset to identify key factors associated with selling prices, understand depreciation and resale-value patterns, and generate actionable insights.

## 🔍 Project Objectives

- Explore and understand the dataset structure.
- Check missing values, duplicates, invalid values, and data consistency.
- Clean and prepare the dataset for analysis.
- Engineer useful features such as vehicle age and resale retention.
- Analyze selling-price distributions and market segments.
- Study relationships between selling price and vehicle characteristics.
- Perform correlation and outlier analysis.
- Identify high-priced car models.
- Translate findings into business recommendations.

## 📊 Dataset Overview

The dataset initially contains **301 vehicle listings** and **9 variables**.

| Feature | Description |
|---|---|
| `Car_Name` | Name/model of the car |
| `Year` | Manufacturing/model year |
| `Selling_Price` | Selling price of the used car |
| `Present_Price` | Present/original price reference |
| `Kms_Driven` | Kilometers driven |
| `Fuel_Type` | Petrol, Diesel, or CNG |
| `Seller_Type` | Dealer or Individual |
| `Transmission` | Manual or Automatic |
| `Owner` | Number of previous owners |

The dataset contains **98 unique car names** and model years from **2003 to 2018**.

## 🧹 Data Exploration & Cleaning

The project performs:

- Dataset structure and dimension checks
- Data-type inspection
- Descriptive statistics
- Categorical-value analysis
- Missing-value analysis
- Duplicate detection
- Numeric-range validation
- Category validation

### Cleaning Results

- Initial records: **301**
- Exact duplicate rows: **2**
- Final unique records used for analysis: **299**
- Missing values: **0**
- Negative values in major numeric fields: **0**
- Text fields were standardized.
- Categorical values were validated.

No missing-value imputation was required because the supplied dataset contains no missing values.

## ⚙️ Feature Engineering

The analysis creates additional business-oriented variables.

### Car Age

`Car Age = Reference Year − Manufacturing Year`

### Depreciation Amount

`Depreciation Amount = Present Price − Selling Price`

### Resale Retention %

`Resale Retention % = (Selling Price / Present Price) × 100`

### Price Gap %

`Price Gap % = ((Present Price − Selling Price) / Present Price) × 100`

Vehicles are also grouped into **age bands** and **quartile-based mileage bands**.

## 📈 Exploratory Data Analysis

The project analyzes:

- Fuel-type distribution
- Selling price distribution
- Present price distribution
- Kilometers driven
- Vehicle age
- Resale retention
- Selling price by fuel type
- Selling price by seller type
- Selling price by transmission
- Selling price by ownership
- Vehicle age vs selling price
- Present price vs selling price
- Kilometers driven vs selling price
- Age-band pricing
- Resale retention by age
- Model-level pricing

## 📊 Key Findings

### 1. Overall Dataset

- **299 unique listings** remain after removing duplicates.
- Average selling price: **₹4.59 lakh**
- Average present price: **₹7.54 lakh**
- Average kilometers driven: **36.9K km**

### 2. Fuel Type

- Petrol is the dominant category with **239 listings**.
- Diesel has **58 listings**.
- CNG has very limited representation.
- Diesel has the highest average selling price at approximately **₹10.10 lakh**.

### 3. Vehicle Age

Vehicle age has a negative relationship with selling price:

**Correlation ≈ −0.23**

The analysis shows that newer vehicles generally command higher resale prices.

### 4. Present Price

Present Price has the strongest numerical relationship with Selling Price:

**Correlation ≈ 0.88**

It is therefore an important benchmark when estimating resale value.

### 5. Kilometers Driven

Kilometers driven has a relatively weak relationship with selling price:

**Correlation ≈ −0.09**

Mileage should therefore be considered together with model, age, present price, and configuration.

### 6. Seller Type & Transmission

- Dealer listings show a substantially higher price distribution than individual listings.
- Automatic vehicles show a higher price distribution than manual vehicles.
- These are dataset-level associations and should not be interpreted as causal effects.

### 7. Depreciation

Resale-value retention decreases as vehicle age increases. Younger vehicles generally retain a larger share of their present/original price.

### 8. Top Models

The top-model comparison is restricted to models with at least **3 listings** for greater stability.

**Fortuner** ranks among the highest-priced frequently listed models in the analysis.

## 📌 Correlation Analysis

| Variable | Correlation with Selling Price |
|---|---:|
| Present Price | **≈ 0.88** |
| Year | **≈ 0.23** |
| Kms Driven | **≈ −0.09** |
| Owner | **≈ −0.09** |
| Car Age | **≈ −0.23** |

> Correlation represents association, not causation.

## 🚨 Outlier Analysis

IQR-based analysis identified:

| Variable | Outliers |
|---|---:|
| Selling Price | 16 |
| Present Price | 14 |
| Kms Driven | 8 |

The outliers were **not automatically removed**, because high-value or high-mileage vehicles can be legitimate market observations.

Both mean and median were considered to avoid misleading conclusions.

## 💡 Business Insights

- **Present Price** is the strongest direct numerical benchmark for Selling Price.
- **Vehicle age** is associated with lower resale value.
- **Resale retention** decreases as vehicle age increases.
- **Mileage** has a weaker relationship with price than Present Price and Age.
- **Fuel type, transmission, and seller type** show clear differences in price distributions.
- **Car model** remains important; comparable vehicles should be evaluated within similar model groups.

## 🏢 Business Recommendations

### For Buyers

- Compare selling price with present price.
- Consider age and kilometers driven together.
- Compare against similar models and configurations.
- Use resale retention to understand depreciation.

### For Sellers & Dealers

- Benchmark vehicles against comparable models.
- Adjust pricing based on age and mileage.
- Consider fuel type and transmission when creating comparable groups.
- Avoid relying on one overall market-average price.

### For Automotive Analysts

- Segment vehicles by model, age, fuel type, and transmission.
- Use both mean and median where outliers exist.
- Develop predictive pricing models using the cleaned and engineered data.

## 🛠️ Technology Stack

- **Python**
- **Pandas** — data loading, cleaning, transformation, and aggregation
- **NumPy** — numerical calculations and feature engineering
- **Matplotlib** — visualization
- **Seaborn** — statistical visualization
- **Jupyter Notebook** — analysis workflow

## 📁 Recommended Project Structure

```text
car-dekho-market-analysis/
│
├── data/
│   └── car_dekho_dataset.csv
│
├── notebooks/
│   └── Car_Dekho_End_to_End_Analysis.ipynb
│
├── visualizations/
│   ├── fuel_distribution.png
│   ├── price_by_fuel.png
│   ├── age_vs_price.png
│   ├── present_vs_selling.png
│   ├── kms_vs_price.png
│   ├── category_comparison.png
│   ├── age_band_price.png
│   ├── resale_retention.png
│   ├── correlation.png
│   └── top_models.png
│
├── presentation/
│   └── Car_Dekho_End_to_End_Final_Presentation.pptx
│
├── README.md
└── requirements.txt
```

## ▶️ How to Run

### Clone the repository

```bash
git clone https://github.com/<your-username>/car-dekho-market-analysis.git
cd car-dekho-market-analysis
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
notebooks/Car_Dekho_End_to_End_Analysis.ipynb
```

## 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
jupyter
openpyxl
```

## 📁 Project Deliverables

- ✅ End-to-end Python/Jupyter Notebook
- ✅ Data exploration
- ✅ Data-quality checks
- ✅ Data cleaning and validation
- ✅ Feature engineering
- ✅ Exploratory data analysis
- ✅ Data visualizations
- ✅ Correlation analysis
- ✅ Outlier investigation
- ✅ Business insights
- ✅ Recommendations
- ✅ Project presentation

## 🚀 Future Scope

The next step is to build a **car-price prediction model** using the cleaned and engineered dataset.

Potential models include:

- Linear Regression
- Random Forest Regression
- Gradient Boosting
- XGBoost

Model performance can be evaluated using:

- **MAE**
- **RMSE**
- **R² Score**

Further improvements could include advanced feature engineering, categorical encoding, hyperparameter tuning, and deployment as an interactive car-price estimation application.

## 👨‍💻 Author

**Durga Prasad**

**Project:** Car Market Trends Analysis with Car Dekho Data  
**Domain:** Data Analytics

---

> **Project Workflow:**  
> Data Exploration → Data Quality Checks → Data Cleaning → Feature Engineering → EDA → Visualization → Correlation Analysis → Outlier Analysis → Business Insights → Recommendations
