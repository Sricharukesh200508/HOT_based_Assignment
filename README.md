# Financial KPI Analysis & Data Visualization

This repository contains tools and analyses for advanced financial data analysis and visualization. It includes a Jupyter Notebook for Python-based statistical analysis and Tableau workbooks for business intelligence and sales pipeline tracking.

## Repository Contents

*   **`KPI_Analysis.ipynb`**: A comprehensive Jupyter Notebook designed to perform exploratory data analysis, statistical testing, and visualization on financial data (specifically quarterly income statements).
*   **`Salesforce Sales Cloud - Weighted Sales Pipeline.twbx`**: A packaged Tableau workbook (`.twbx`) focusing on sales pipeline analytics, weighted sales, and performance tracking within Salesforce Sales Cloud.
*   **`datascience.twb`**: A standard Tableau workbook (`.twb`) intended for data science-related data visualization and insights.

## Detailed Analysis of `KPI_Analysis.ipynb`

The Jupyter Notebook `KPI_Analysis.ipynb` is structured to process financial datasets (e.g., `incomeStatementHistory_quarterly.csv`) and extract meaningful business insights. It is broken down into the following key features:

### 1. Data Loading & Inspection
*   Utilizes Google Colab's file upload widget to securely import CSV datasets.
*   Reads the data into a Pandas DataFrame.
*   Automatically logs the number of rows, columns, and available data fields (e.g., `totalRevenue`, `grossProfit`, `netIncome`, `totalAssets`, etc.) to verify data integrity.

### 2. Advanced Correlation Analysis
*   Analyzes the relationship between **Total Revenue** and various raw Key Performance Indicators (KPIs) such as Gross Profit, Operating Income, Net Income, EBITDA, Total Assets, Total Liabilities, and Cash/Cash Equivalents.
*   Employs three different statistical correlation methods:
    *   **Pearson**: Measures linear correlation.
    *   **Spearman**: Measures monotonic relationships (rank correlation).
    *   **Kendall**: Measures ordinal association.
*   Calculates an **Average Absolute Correlation** to rank the Top 5 most influential KPIs.

### 3. Creation of Derived KPIs (Financial Ratios)
*   Enhances the raw dataset by calculating advanced financial metrics, which often provide better comparative insights than absolute numbers:
    *   **Gross Margin**: Profitability ratio (`grossProfit` / `totalRevenue`).
    *   **Return on Assets (ROA)**: Efficiency metric (`netIncome` / `totalAssets`).
    *   **Return on Equity (ROE)**: Profitability against equity (`netIncome` / `totalLiabilities` proxy).
    *   **Operating Margin**: Operational efficiency (`operatingIncome` / `totalRevenue`).

### 4. Statistical Significance Testing
*   Computes the **p-values** for the correlations between Total Revenue and the selected KPIs.
*   Categorizes the statistical significance of each KPI (e.g., `***` for $p < 0.001$, `**` for $p < 0.01$, `*` for $p < 0.05$, and `ns` for not significant).
*   Filters and highlights only the KPIs that are statistically significant ($p < 0.05$).

### 5. Professional Visualizations
*   **Advanced Pairplot**: Generates a scatter plot matrix using `seaborn.pairplot` comparing Revenue against the Top 5 significant KPIs. Includes KDE distributions on the diagonal and regression scatter plots.
*   **Correlation Heatmap**: Creates an annotated, color-coded heatmap (`seaborn.heatmap`) of the correlation matrix, providing a quick visual summary of the relationships between all significant variables.
*   Automatically saves and downloads these high-resolution graphics (`advanced_pairplot.png`, `advanced_heatmap.png`) for reporting purposes.

## Requirements & Environment

To run `KPI_Analysis.ipynb` locally or in a cloud environment, the following Python libraries are required:
*   `pandas`
*   `numpy`
*   `seaborn`
*   `matplotlib`
*   `scipy`

*(Note: The notebook includes `google.colab` imports which are specific to the Google Colab environment. If running locally via Jupyter, file loading mechanisms will need to be adapted to standard local paths).*
