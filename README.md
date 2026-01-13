# Global Internet Usage & Socio-Economic Correlation Analysis

This project explores the evolution of global internet usage from 2000 to the present day. It integrates data from various sources (World Bank, Internet Speed tests, and Education statistics) to identify the socio-economic drivers of digital adoption and provides predictive modeling for future trends.

## 🚀 Features

* **Multi-Source ETL:** Merges internet usage data with regional metadata, broadband speed rankings, GDP, and educational literacy rates.
* **Database Integration:** Includes a pre-configured `SQLAlchemy` and `PostgreSQL` schema for persistent storage of structured indicators.
* **Dynamic EDA:**
    * Regional trend analysis using line plots.
    * Distribution shifts (2000 vs. 2022) highlighting the digital divide.
    * Quantile analysis (Top 5% vs. Bottom 5% performers).
* **Goal Tracking:** Automated monitoring of countries achieving the "50% Connectivity Goal."
* **Correlation Engine:** Statistical analysis of internet usage against:
    * GDP (Normalized to US$)
    * Life Expectancy
    * Government Education Expenditure
    * Adult & Youth Literacy Rates
* **Best-Fit Regression Forecasting:** A custom regression engine that tests 9 different mathematical models per country to predict usage for 2024–2026.

## 🛠 Tech Stack

* **Language:** Python 3.x
* **Data Manipulation:** `pandas`, `numpy`
* **Database:** `SQLAlchemy`, `PostgreSQL`
* **Statistical Analysis:** `scipy.stats`
* **Visualization:** `matplotlib`, `seaborn`

## 📊 Analytical Pipeline



[Image of the data analysis lifecycle]


### 1. Data Normalization
The script handles missing values (represented as `..` in World Bank datasets) and normalizes economic figures (converting GDP to Millions of US$) to ensure statistical comparability.

### 2. Correlation Study
The project computes Pearson correlation coefficients to determine how strongly education and wealth influence a nation's digital maturity.

### 3. Forecasting Logic
Rather than a "one-size-fits-all" linear regression, the engine evaluates 9 model variations for each country, including:
* **Linear:** $y = a + bx$
* **Logarithmic:** $y = a + b \ln(x)$
* **Exponential:** $y = a \cdot e^{bx}$
* **Reciprocal:** $y = 1 / (a + bx)$

The model with the lowest Sum of Squared Errors (SSE) is selected to generate the final 3-year forecast.



## 📁 Data Structure

| File | Description |
| :--- | :--- |
| `internet_usage.csv` | Historical internet usage % by country (2000-2023). |
| `country_regions.xlsx` | Mapping of countries to World Bank regions. |
| `internet_speed.csv` | Broadband speed rankings and average Mbps (2023). |
| `edu.csv` | Global education statistics and literacy rates. |
| `GDP.csv` | Historical GDP and Life Expectancy data. |

## 📈 Visualizations

The script generates several key insights:
1.  **Regional Growth:** Line charts showing how fast different continents are catching up.
2.  **The 50% Milestone:** A bar chart showing the count of countries crossing the 50% usage threshold per year.
3.  **Forecast Plots:** Combined scatter and line plots showing actual historical data vs. the "Best-Fit" predicted trend line.

---

## 🔧 Setup & Usage

1.  **Install dependencies:**
    ```bash
    pip install pandas numpy sqlalchemy matplotlib seaborn scipy openpyxl
    ```
2.  **Database (Optional):** Uncomment the SQLAlchemy engine sections to enable PostgreSQL export.
3.  **Run Analysis:**
    ```bash
    python analysis_script.py
    ```

**Would you like me to help you write a summary of the findings (e.g., which socio-economic factor had the strongest correlation with internet growth in your data)?**
