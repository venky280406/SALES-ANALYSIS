# Sales Analysis: AAL Apparel, Q4 2020 (Australia)

**Course-End Project: Applied Data Science with Python**

A comprehensive Python-based data science project focused on wrangling, analyzing, and visualizing Q4 2020 sales data for AAL Apparel in Australia. This project demonstrates proficiency in using the Python data science stack to extract actionable business intelligence from raw retail data.

## Business Problem

Retailers need continuous visibility into their sales performance across different regions, demographic groups, and times of the day. The goal of this project is to clean raw transactional data, perform statistical analysis, and build visual dashboards to identify top-performing sectors and highlight areas requiring targeted marketing interventions.

## Dataset

The project utilizes a dataset named `AusApparalSales4thQrt2020.csv`, which contains 7,560 transactional records of apparel sales in Australia during the 4th Quarter of 2020. 

**Key Fields:**
* `Date`: The date of the transaction
* `Time`: Time slot (Morning, Afternoon, Evening)
* `State`: Australian state of the transaction (e.g., WA, NSW, VIC)
* `Group`: Target demographic (Kids, Men, Women, Seniors)
* `Unit`: Number of units sold
* `Sales`: Total sales amount in USD

## Tools & Libraries Used

* **Language:** Python 3
* **Data Wrangling & Aggregation:** `pandas`, `numpy`
* **Statistical Analysis:** `scipy.stats`
* **Data Visualization:** `matplotlib`, `seaborn`

## Project Tasks & Workflow

### 1. Data Wrangling & Cleaning
* **Inspection & Cleaning:** Identified and fixed leading/trailing spaces in text columns. Parsed text-based date columns into proper `datetime` objects.
* **Missing Value Treatment:** Demonstrated techniques for handling null values, including `dropna()` and imputing missing `Sales` and `Unit` data using the median of the respective State and Group (`fillna` with `transform`).
* **Normalization:** Applied Min-Max scaling to the `Unit` and `Sales` columns to standardize the data on a 0-1 scale.
* **Chunking & Aggregation:** Used `groupby()` and `agg()` to chunk data by state and generate high-level summary tables.
* **Pivoting:** Created pivot tables to analyze multi-dimensional relationships (e.g., State vs. Demographic Group).

### 2. Exploratory Data Analysis & Statistics
* **Descriptive Statistics:** Calculated Mean, Median, Mode, Standard Deviation, and Skewness for numerical columns.
* **Outlier Detection:** Used the 1.5 * IQR rule to identify outliers in sales and unit volumes (found ~1.6% outliers).
* **Time-Series Analysis:** Generated Daily, Weekly, Monthly, and Quarterly sales reports, identifying best/worst performing calendar days and month-over-month growth trends.
* **Hypothesis Testing:** Conducted One-Way ANOVA tests using `scipy.stats.f_oneway` to determine if sales differences across States, Groups, and Times of Day were statistically significant. 

### 3. Data Visualization
* Built a comprehensive Sales & Marketing (S&M) Dashboard using Seaborn.
* Utilized box plots, bar charts, line plots, and heatmaps to visualize sales distributions, peak periods, and state-by-state comparisons.

## Key Business Insights

* **Top Regions:** Victoria (VIC), New South Wales (NSW), and South Australia (SA) are the powerhouse states, generating 70.3% of the total $340.3M Q4 revenue. VIC alone generated over $105M.
* **Underperforming Regions:** Western Australia (WA), Northern Territory (NT), and Tasmania (TAS) are the lowest-selling states, each contributing less than 7% to total sales.
* **Demographics:** Sales are relatively evenly split across demographics, but Men ($85.75M) slightly outperformed Seniors ($84.03M).
* **Time of Day:** Morning is the peak shopping period ($114.2M), closely followed by Afternoons. Evenings are the weakest time slot.
* **Statistical Significance:** ANOVA testing revealed that sales differences between **States** are highly statistically significant (p = 0), whereas differences between Demographic Groups and Times of Day are not statistically significant.
* **Monthly Trends:** December saw a massive 49.2% month-over-month surge in sales ($135.3M), while November saw a 20.7% dip compared to October.

## Recommendations

Based on the analysis, the business should:
1. **Target Weaker States:** Allocate marketing budget to WA, NT, and TAS, utilizing volume-led offers to boost market share in these underperforming regions.
2. **November Interventions:** Since November experienced a significant slump before the December holiday rush, introduce targeted "Pre-Holiday" or "Black Friday" promotions in November to smooth out the revenue curve.
3. **Group-Specific Offers:** Tailor campaigns to the weakest demographic in specific states (e.g., target Seniors in VIC and NSW, and Women in WA).