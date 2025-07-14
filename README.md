Bangalore Property Price Analysis Report
------------------------------------------------
🏙️ Introduction
This analysis examines property prices in Bangalore, focusing on price per square foot to detect and manage outliers using statistical methods. The dataset contains 13,200 records with features such as location, size, total square footage, number of bathrooms, and price.
A complete exploratory data analysis (EDA) and outlier‑handling workflow for Bangalore house prices.This notebook-driven project cleans the data, detects & removes outliers with four different methods, normalises the key variable, and visualises correlations.

📂 Project Structure

├── data
│   └── house_price.csv                # Raw dataset
├── notebooks
│   └── bangalore_price_analysis.ipynb # Finished Jupyter notebook 
├── additional files
│   └── cleaned_data.csv               # csv file after perfroming eda
│   └── duplicated_file.csv            # csv file containing the duplicates
└── README.md                          # <–– You are here

📊 Dataset
-------------------------------------------------------------------------------

Attribute                      Description

location                       - Locality of the property

size                           -  Number of bedrooms (BHK)

total_sqft                     -  Built‑up area (sq ft)

bath                           -  No. of bathrooms

price                          -  Listing price (₹ lakh)

bhk                            -  Extracted integer bedrooms

price_per_sqft                 -  Calculated price per sq ft (₹)

Source : house_price.csv — Kaggle/Udemy Bangalore Housing dataset.


🚀 Notebook Walk‑through
--------------------------------------------------------------------------------

Operations Performed :

1. Basic EDA           
2. Outlier detection - Mean ± 3 σ, Percentile (5–95 %), IQR (1.5 × IQR),  Z‑score (z< 3)
3. Box‑plot comparison - IQR chosen
4. Hist‑plot, log1p transformation, skew/kurtosis check
5. Correlation matrix & heat‑map
6. Scatter plots for visual correlation


🔍 Key Insights
-------------------------------------------------------------------------------------

📊 Exploratory Data Analysis (EDA)
----------------------------------------------------------
1. Dataset Size (Before Cleaning): 13,203 rows × 7 columns.
2. Missing Values: No missing values were detected across any columns.
3. Duplicated Rows: Detected 1049 duplicate rows
4. Action Taken: All duplicates were removed to ensure data integrity.
5. Cleaned Dataset Info (After Removing Duplicates): 12151 entries.
6. Data Types & Memory Usage: All columns are properly typed (int64, float64, object). No type conversion or correction was necessary at this stage.


🚫 Outlier Detection & Removal
-----------------------------------------------------------------

1. Four statistical methods were applied:
      1. Mean & Standard Deviation: Removed values beyond ±3 standard deviations.
      2. Percentile Method: Kept values between 5th and 95th percentile.
      3. Interquartile Range (IQR): Removed values outside 1.5×IQR range.
      4. Z-Score Method: Eliminated values with Z-score > 3 or < -3.


📦 Box Plot Comparison
-----------------------------------------------------------------------

A box plot was used to compare the effectiveness of each method.✅ IQR method provided the best balance between retaining meaningful data and removing extreme outliers.

📈 Normality Check & Transformation
----------------------------------------------------------------------

1. Histogram Analysis: The price per square foot column was highly skewed.
2. Transformation Applied: Log transformation (log1p) was used.
3. Skewness & Kurtosis: Before Transformation: High skewness and kurtosis. After Transformation: Reduced skewness, making the data more normally distributed.

🔥 Correlation Analysis
------------------------------------------------------
🔍 Heatmap Insights :
1. Strong Positive Correlations:
    1. bath and bhk: 0.88 → Homes with more bedrooms tend to have more bathrooms.
    2. total_sqft and price: 0.66 → Larger properties generally cost more.
    3. price and price_per_sqft: 0.61
    4.price_per_sqft and log_price_per_sqft: 0.97 → Validates the effectiveness of log transformation.
2. Moderate Correlations:
    1. bath and price: 0.56
    2. bath and price_per_sqft: 0.35
3. Low or Negligible Correlations:
    1. total_sqft and price_per_sqft: 0.13
    2. total_sqft and log_price_per_sqft: 0.05
📌 These insights confirm that while property size and number of rooms impact the price, price per square foot is not strongly influenced by total square footage alone.

🔍 Scatter Plot Observations:
1. Most properties are between 500–3000 sqft.
2. Their price per sqft is mostly between ₹3000–₹8000.
3. A few large properties (>10,000 sqft) show very low price per sqft.
4. These could be outliers or bulk/plot sales.
5. After cleaning, the pricing pattern is more clear and consistent.
6. There's no clear linear relationship between size and price per sqft.

✅ Conclusion

Outlier Removal: IQR method was the most effective and visually appropriate.
Data Transformation: Log transformation significantly improved data normality.


🏃‍♂️ How to Run
-------------------------------------------------------------------

1. Launch Jupyter Lab:
2. jupyter lab - Open notebooks/bangalore_price_analysis.ipynb.
3. Run cells sequentially (Shift + Enter).
4. The notebook will recreate all plots and save them to output/ automatically.



