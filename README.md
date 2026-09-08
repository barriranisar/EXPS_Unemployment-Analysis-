# 📊 Unemployment Analysis with Python (Covid-19 Impact Study)

An end-to-end Exploratory Data Analysis (EDA) and socioeconomic visualization project analyzing unemployment rate dynamics across India before and during the Covid-19 national lockdown (2019–2020)[cite: 3].

---

## 📌 Project Overview
- **Objective:** Investigate unemployment trends, evaluate the socioeconomic shock of the Covid-19 lockdown, compare urban versus rural resilience, and derive data-driven policy recommendations[cite: 3].
- **Dataset:** `Unemployment in India.csv` (740 valid monthly observations across 28 states/regions)[cite: 3].
- **Timeframe:** May 2019 – June 2020[cite: 3].
- **Key Target Metric:** `Estimated Unemployment Rate (%)`[cite: 3].

---

## 📂 Dataset Attributes & Schema

| Column Name | Cleaned Column Name | Data Type | Description |
| :--- | :--- | :---: | :--- |
| `Region` | `State` | Object | Name of the Indian State / Union Territory[cite: 3] |
| `Date` | `Date` | Datetime | Observation timeline (`YYYY-MM-DD`)[cite: 3] |
| `Frequency` | `Frequency` | Object | Reporting frequency (Monthly)[cite: 3] |
| `Estimated Unemployment Rate (%)` | `Unemployment_Rate` | Float64 | Percentage of unemployed workforce[cite: 3] |
| `Estimated Employed` | `Employed_Count` | Float64 | Total estimated employed individuals[cite: 3] |
| `Estimated Labour Participation Rate (%)` | `Labour_Participation_Rate` | Float64 | Percentage of working-age population active in labour force[cite: 3] |
| `Area` | `Area` | Object | Geographical sector (`Rural` or `Urban`)[cite: 3] |

---

## ⚙️ Data Engineering & Analytical Workflow

### 1. Data Cleaning & Header Normalization
* Stripped trailing and leading whitespace across raw column headers[cite: 3].
* Dropped 28 unpopulated trailing rows to ensure zero missing/null values across the dataset[cite: 3].

### 2. Temporal Feature Extraction & Phase Segmentation
* Parsed string dates into standard `datetime64[ns]` format with day-first ordering[cite: 3].
* Extracted `Year`, `Month_int`, and abbreviated `Month_name` for granular seasonal time-series slicing[cite: 3].
* Created a **Lockdown Phase Segmentation** feature (`Lockdown_Phase`) based on the National Lockdown threshold date (**24 March 2020**)[cite: 3]:
  - `Pre-Lockdown (2019-2020)`: Observations recorded prior to March 24, 2020[cite: 3].
  - `Lockdown Impact (2020)`: Observations recorded during the peak lockdown window (April–June 2020)[cite: 3].

---

## 📈 Statistical Distribution & Benchmark Metrics

```text
======================================================================
	 UNEMPLOYMENT, EMPLOYMENT & LABOUR PARTICIPATION SUMMARY 
======================================================================
       Unemployment_Rate  Employed_Count  Labour_Participation_Rate
count             740.00          740.00                     740.00
mean               11.79      7204460.03                      42.63
std                10.72      8087988.43                       8.11
min                 0.00        49420.00                      13.33
25%                 4.66      1190404.50                      38.06
50%                 8.35      4744178.50                      41.16
75%                15.89     11275489.50                      45.50
max                76.74     45777509.00                      72.57
======================================================================

```

---

## 🔬 Comparative Impact: Pre-Lockdown vs. Lockdown Period

| Lockdown Phase | Avg. Unemployment Rate (%) | Avg. Employed Workforce | Avg. Labour Participation (%) |
| --- | --- | --- | --- |
| **Pre-Lockdown (2019–2020)** | **9.51%** | **7,466,028** | **43.89%** |
| **Lockdown Impact (2020)** | **17.77%** | **6,517,203** | **39.33%** |

---

## 🔑 Key Insights & Analytical Findings

* **Unprecedented Shockwave (April–May 2020):** Following the strict lockdown mandates in March 2020, the average national unemployment rate jumped by **+86.8%** (from 9.51% to 17.77%), with several urban sectors recording single-month peaks exceeding **28% to 76%**.


* **Urban vs. Rural Economic Resilience:**
* **Urban areas** suffered a more acute disruption due to their heavy reliance on non-essential manufacturing, construction, retail, and gig-economy services.


* **Rural areas** exhibited greater economic resilience as agricultural cycles continued and absorbed displaced informal labor.




* **Workforce Contraction & Discouragement:** Average active employment dropped by nearly **1 million jobs per region**, while the Labour Participation Rate dropped sharply from **43.89% to 39.33%**, indicating significant labor force withdrawal during the peak pandemic crisis.


* **Regional Disparities:** High-density and migrant-heavy states/UTs (including Puducherry, Jharkhand, Bihar, and Haryana) experienced the most severe unemployment spikes during the lockdown phase.


* **Correlation Signals:**
* A strong negative correlation was observed between `Unemployment_Rate` and `Employed_Count`.


* A moderate inverse relationship emerged between unemployment and labour participation rate, confirming the "discouraged worker effect".





---

## 📊 Key Visualizations & Pattern Analysis

### 1. Longitudinal Timeline Trend (Rural vs. Urban)

* Tracks monthly trajectories from May 2019 to June 2020, pinpointing the acute spike in April–May 2020.



### 2. Geographical Disparity Boxplot

* Illustrates wider variance, higher medians, and prominent outliers in urban centers compared to rural regions during lockdown.



### 3. Top Affected States Ranking

* Identifies and benchmarks the top 10 hardest-hit states by average unemployment rate during the 2020 lockdown.



### 4. Cross-Feature Correlation Matrix

* Analyzes dependencies between unemployment, workforce count, and labor participation rates.



---

## 💡 Policy Insights & Economic Recommendations

1. **Urban Social Safety Nets:** Introduce urban employment guarantee programs modeled after rural schemes (e.g., MGNREGA) to support daily-wage and informal workers during economic freezes.


2. **MSME Liquidity Buffers:** Provide emergency credit lines, wage subsidies, and tax deferrals to prevent small businesses from executing mass layoffs during sudden shocks.


3. **Migrant & Informal Worker Registries:** Implement digital worker databases tied to direct benefit transfers (DBT) to ensure seamless food and cash assistance during nationwide crises.



---

## 🛠️ Technology Stack

* **Language:** Python 3.x


* **Data Manipulation:** Pandas, NumPy


* **Visualization:** Matplotlib, Seaborn


* **Temporal Processing:** Python Built-in `datetime`, `calendar`

* **Environment:** Jupyter Notebook



---

## 🚀 How to Run

1. Clone this repository:

```bash
git clone [https://github.com/](https://github.com/)<your-username>/EXPS_UnemploymentAnalysis.git

```

2. Install dependencies:

```bash
pip install numpy pandas matplotlib seaborn

```

3. Open the Jupyter Notebook:

```bash
jupyter notebook

```

```

```
