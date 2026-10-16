# Nigeria Gas Production and Use Dashboard (2021 to 2025)

A data project built during my SIWES Internship at NNPC Gas Infrastructure Company (NGIC), shared with my supervisor's approval. It uses public national data only. It does not use NGIC's internal data and is not an official NGIC product.

# What it does
- Shows how much natural gas Nigeria produced each month from January 2021 to December 2025
- Shows where the gas went: field use, domestic sales, export sales and flaring
- Flags months that look unusual compared with the months around them

# Data
Source: Gas Production Status Reports, Nigerian Upstream Petroleum Regulatory Commission (NUPRC), nuprc.gov.ng
- 60 months, one row per month
- Units: MMSCF (million standard cubic feet)
- 2021 to 2024 came from Excel files (in data/raw). 2025 came from a PDF table (also in data/raw), entered by hand, then checked against NUPRC's yearly totals
- October to December 2025 are marked provisional by NUPRC and may change after reconciliation

# Method
1. Combined the yearly files and cleaned the columns (Python, pandas)
2. Checked the numbers add up (utilised gas check: gap of 0.01 MMSCF at most; total production check: gap of 59.6 MMSCF at most, about 0.03% of a month)
3. Converted monthly figures to per day figures so short months are not treated as drops
4. Flagged unusual months by comparing each month with the median of the six months around it. A score above 2.5 or below -2.5 is flagged
5. Built a three page Power BI dashboard

# Main findings
- Domestic share of sold gas rose from 33.8% (2021) to 45.3% (2025)
- Domestic sales rose about 34% and exports fell about 17% between 2021 and 2025
- Flaring fell from 9.2% to 7.5% of production, mostly in 2022
- Exports swing much more than domestic sales
- 8 of 60 months flagged. September 2025 exports were the strongest flag


# How to run the notebook
1. Open notebook/Natural_Gas_Production_&_Utilization.ipynb in Google Colab
2. Upload the 4 Excel files from data/raw (2021 to 2024) to the Colab file panel. Do not rename them
3. Click Runtime, then Run all

# Limitations
- National data, not NGIC's own
- Describes what happened. It does not forecast or explain causes
- The checker finds sudden one month changes and can miss slow ones
- Only 60 months of data. Months near the start and end have fewer neighbours to compare with
- Shrinkage is left out of the charts because it is very small

# Files
* raw data: the original NUPRC files
* data/gas_monthly_clean.csv: the cleaned monthly data
* notebook/: Python code for cleaning, checks and the odd month checker
* dashboard/NGIC_Gas_Dashboard.pbix: the Power BI file (open with Power BI Desktop)

# Done By:
Mine Dema
