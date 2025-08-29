# Medicare Part D Prescriber Data Analysis for Negotiation Support

[Negotiation Support for Lenalidomide Generic vs. Revlimid Tableau Dashboard](https://public.tableau.com/app/profile/sandeep.ghotra/viz/NegotiationSupportLenalidomideGenericOpportunityvs_Revlimid/Dashboard1)


## Project Overview

This project analyzes the publicly available CMS Medicare Part D Prescribers by Provider and Drug dataset (specifically using the 2022 data) to uncover insights relevant to pharmaceutical rebate negotiations and cost management strategies. The analysis explores prescribing patterns, identifies high-cost/high-volume drugs, compares brand vs. generic utilization, examines prescriber specialty contributions, analyzes market share, and detects potential outliers.

The primary goal is to process and aggregate this complex dataset into actionable summaries suitable for visualization and strategic decision-making, particularly focusing on identifying cost-saving opportunities like generic drug adoption.

## Data Source

* **Dataset:** Medicare Part D Prescribers - by Provider and Drug
* **Year:** 2022 (Based on the filename `Medicare_Part_D_Prescribers_by_Provider_and_Drug_2022-1.csv`)
* **Source:** Centers for Medicare & Medicaid Services (CMS)
* **Note:** The raw data file is **not included** in this repository due to its size. It can typically be downloaded directly from the CMS website. This analysis was performed specifically on data filtered for the state of Maryland.

## Analysis Steps

The analysis, contained within the `cms_prescriber-1.ipynb` Jupyter Notebook, follows these key steps (structured as 'Tickets'):

1.  **Data Loading & Initial EDA:** Loading the dataset, initial cleaning (data types, missing values), and basic exploratory data analysis (summary statistics, distributions).
2.  **High-Cost/Volume Drug Identification:** Aggregating data by drug (generic and brand) to identify top contributors to cost and claim volume. Calculation of Cost Per Claim.
3.  **Brand vs. Generic Analysis:** Comparing cost and utilization metrics for brand drugs and their generic equivalents, including calculating Generic Dispensing Rates (GDR).
4.  **Provider Prescribing Patterns:** Analyzing prescribing habits at the individual provider (NPI) level, identifying top prescribers overall and for specific drugs.
5.  **Outlier Detection:** Using the IQR method to identify potential outliers in provider cost-per-claim and claim volume for specific drugs.
6.  **Specialty Contribution Analysis:** Examining how different medical specialties contribute to overall costs/claims and the utilization of specific high-interest drugs.
7.  **Market Share & Usage Patterns:** Calculating market share (volume and value) for specific drugs (e.g., Revlimid/Lenalidomide) against competitors and analyzing average days supply.
8.  **Data Preparation for Visualization:** Consolidating key aggregated tables into clean CSV files suitable for external visualization tools like Tableau.

## Tools & Libraries Used

* **Language:** Python 3
* **Core Libraries:**
    * `pandas`: Data manipulation and analysis.
    * `numpy`: Numerical operations.
    * `matplotlib`: Basic plotting.
    * `seaborn`: Enhanced statistical plotting.
* **Environment:** Jupyter Notebook

## How to Run

1.  **Obtain Data:** Download the relevant CMS Part D Prescriber data file (e.g., for 2022) and place it in the same directory as the notebook, or update the `file_path` variable in Ticket 1.
2.  **Install Dependencies:** Ensure you have the required Python libraries installed. You can typically install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn jupyterlab
    ```
    *(Consider adding a `requirements.txt` file for easier environment setup).*
3.  **Run Notebook:** Open `cms_prescriber-1.ipynb` in JupyterLab or Jupyter Notebook and execute the cells sequentially. The analysis performs filtering for Maryland data.

## Output

The notebook generates several intermediate pandas DataFrames containing aggregated insights. The final step (Ticket 8) exports these key DataFrames into CSV files (saved in the `tb_data` sub-directory) which are intended to be used as data sources for visualization tools like Tableau to create interactive dashboards for stakeholders.

