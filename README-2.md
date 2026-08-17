# U.S. Weather Analysis — Advanced Python EDA

## Overview
An advanced exploratory data analysis project on one year of real daily weather data (mean/min/max temperature, 134-year historical averages, all-time records, and precipitation) across **10 major U.S. cities**, sourced from FiveThirtyEight's published dataset (originally scraped from Weather Underground).

This project goes beyond basic pandas `describe()` — it includes feature engineering, statistical hypothesis testing, and multi-chart visual storytelling.

## Business Questions Answered
1. Which cities are running warmer/colder than their own historical average, and by how much?
2. Is the temperature difference between cities statistically significant, or could it be random noise?
3. Which specific days came closest to all-time temperature records?
4. Is there a relationship between temperature anomalies and precipitation anomalies?
5. What does the underlying seasonal trend look like once daily noise is smoothed out?

## What's Inside
- **`weather_analysis.ipynb`** — the full analysis notebook (33 cells): data loading, cleaning, feature engineering, 7 visualizations, and a one-way ANOVA statistical test
- **`combined_weather_data.csv`** — cleaned, combined, feature-engineered dataset (3,650 rows = 10 cities × 365 days)
- **`raw_data/`** — original per-city source CSVs
- **`charts/`** — all 7 exported chart images (PNG)

## Techniques Demonstrated
- Combining multiple raw files into one tidy DataFrame
- Data quality auditing (missing values, duplicates, dtype checks)
- Feature engineering: anomaly calculations, record-proximity flags
- Group-by aggregation and multi-metric summary tables
- Visualization: line trends, heatmaps, box plots, correlation matrices, regression scatter plots, rolling averages
- **Statistical hypothesis testing** — one-way ANOVA (`scipy.stats.f_oneway`) to test significance of inter-city temperature differences
- Pearson correlation testing with p-values

## Key Findings
1. Temperature differences between cities are **statistically significant** (ANOVA p-value ≪ 0.05)
2. Seattle and Los Angeles ran the warmest **relative to their own historical averages** (+3.9°F, +3.1°F); Indianapolis ran the coldest relative to its average (-1.8°F)
3. Temperature and precipitation anomalies show only a **weak correlation** — unusually warm days aren't reliably wetter or drier
4. February was the most anomalously cold month across nearly every city studied

## How to View
Open `weather_analysis.ipynb` directly on GitHub — it renders with all charts and outputs inline, no setup needed. To re-run locally: `pip install pandas numpy matplotlib seaborn scipy jupyter` then `jupyter notebook weather_analysis.ipynb`.

---
*Built as a freelance portfolio project — Advanced Python Data Analysis (pandas, seaborn, scipy, statistical testing).*
