# Marketing Campaign Data Processing and Data Visulization Process

This project focuses on the data cleaning and processing of a customer marketing campaign dataset. The entire workflow is performed using the **Pandas** library within a **Google Colab** notebook.

The goal is to take a raw CSV, excel file, identify and correct issues, and transform the data into a clean, structured format ready for analysis.

---

## Dataset

* **File:** `marketing_campaign.csv`
* **Description:** Contains customer demographic data, spending habits, and campaign responses.

---

## Project Workflow

### 1. Data Loading (Google Colab & Pandas)
* The `google.colab.files` module is used to upload the `marketing_campaign.csv` file into the Colab environment.
* **Pandas** (`pd.read_csv`) is used to load the file into a DataFrame.
* Initial inspection is performed using `df.info()`, `df.describe()`, and `df.isnull().sum()` to find missing values and check data types.

### 2. Data Cleaning (Pandas)
* **Missing Values:** The `Income` column's missing values are filled using the median, calculated with `df['Income'].median()`.
* **Categorical Data:** The `Marital_Status` column is standardized by replacing non-standard values (like 'YOLO', 'Absurd') with 'Single' using `df.replace()`.
* **Redundant Data:** Columns with no variance (e.g., `Z_CostContact`, `Z_Revenue`) are removed using `df.drop()`.

### 3. Data Processing & Transformation (Pandas)
New, useful columns are created from existing data using standard Pandas operations:
* **`Total_Spending`:** Created by summing all `Mnt...` (amount spent) columns.
* **`Age`:** Calculated by subtracting the `Year_Birth` column from a reference year (2015).

### 4. Data Aggregation (Pandas)
The `df.groupby()` function is used to summarize the processed data:
* **Spending by Education:** Calculated the average `Total_Spending` for each `Education` level.
* **Summary by Marital Status:** Created a summary table of customer counts and income by `Marital_Status`.

---

## Tools Used

* **Google Colab:** For the notebook environment and file uploading.
* **Pandas:** For all data loading, cleaning, processing, and aggregation tasks.

The analysis is presented in a dynamic Power BI dashboard.



**###Data Visulization:**
<img width="772" height="408" alt="Data Visulization" src="https://github.com/user-attachments/assets/f7256095-43b4-4a89-9184-2a43349378cc" />
### Dashboard Highlights:
* **Overall Performance:** Displays total spent and average customer age.
* **Segmentation:** Scatter plot showing the strong correlation between Income and Total Spending, segmented by Marital Status.
* **Product Preference:** Analysis of spending mix across categories, revealing which customer groups favor certain products (e.g., Wine vs. Meat).

## Next Steps
To explore the analysis further, download the project files:
1.  Clone this repository.
2.  Open the Power BI file (`.pbix`) (if available) or import the `marketing_campaign.csv` into Power BI.
3.  Review the data model and visualizations.

## Data visualization with KPI, slicer, Time -Series graph and Cards
<img width="716" height="425" alt="KPI   SLICER-POWERBI" src="https://github.com/user-attachments/assets/28aeff99-595b-4baf-99a8-0ac41158eca4" />
<img width="917" height="497" alt="SLICER01" src="https://github.com/user-attachments/assets/b81a45cf-08a8-4b33-80a3-393fb5be2bad" />



📊 Marketing Campaign Performance Dashboard

This project analyzes the Marketing Campaign Dataset in Power BI to deliver an interactive dashboard and an executive summary for business stakeholders.

🎯 Key Performance Indicators (KPIs)

The dashboard focuses on these critical metrics:

Category

KPI Name
Definition
Profitability
Total Revenue
Sum of all product spending (e.g., Wines, Meats).
Profitability
Total Profit
Revenue minus promotional costs.
Efficiency
CLV
Average total spending per customer.
Efficiency
Response Rate
Percentage of customers accepting the last campaign.
Growth
YoY Growth
Year-over-Year change in Total Revenue.

✨ Core Features

Interactivity: Uses Slicers on date (Dt_Customer), demographics (Marital_Status, Education), and financial metrics (Income, Recency).
Visuals:
Cards for instant KPI totals.
Line Chart for Time-Series Analysis of Revenue and YoY Growth.
Bar/Donut Charts for customer segmentation (e.g., spending by Education Level) and campaign acceptance rates.
Implementation: Developed using clean DAX Measures and includes a dedicated Date Table for accurate time intelligence.

💡 Future Enhancements
Focus areas include implementing Row-Level Security (RLS) and using AI Visuals (e.g., Key Influencers) to find drivers of low response rates.
