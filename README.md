# Healthcare Data Analysis: Elective Hip Replacement Surgeries in New York State

## Overview
This project analyzes hospital discharge data from New York State, focusing on elective hip replacement surgeries. The goal was to uncover insights into Length of Stay (LOS), cost efficiency, and demographic trends across 151 hospitals. The analysis was conducted using Power BI and DAX, with the final dashboard providing actionable insights for improving hospital operations and patient care.

## Key Insights
- **Length of Stay (LOS)**: Ranged from 1.4 days to 12.0 days across hospitals.
- **Cost per Discharge**: Varied significantly, with some hospitals costing up to $85,000 per discharge.
- **Demographic Trends**: Patients aged 50+ accounted for 70% of discharges and had longer LOS.
- **Key Drivers**: Extreme severity of illness and discharge to skilled nursing homes were major contributors to longer LOS.

## Methodology
1. **Data Cleaning**: The dataset was cleaned and filtered using Power Query.
2. **Exploratory Analysis**: Key demographic variables (age, gender) and clinical factors (severity of illness, mortality risk) were analyzed.
3. **DAX Measures**: Key metrics like Average LOS, Average Cost per Discharge, and Percentage Variation were calculated.
4. **Visualization**: Interactive dashboards were created to visualize trends and outliers.

## DAX Functions Used
- `Total Discharges = COUNTROWS(hospital_discharges)`
- `Average LOS Days = AVERAGE(hospital_discharges[length_of_stay])`
- `Average Cost per Discharge = DIVIDE(SUM(hospital_discharges[total_costs]), [Total Discharges])`

## Final Dashboard
[Link to Interactive Dashboard](https://app.powerbi.com/groups/me/reports/b77aa5d9-ac44-4360-99e1-a8d9b8c3eebf/46d83e22d57023121d38?experience=power-bi)  


## Repository Contents
- `README.md`: Project overview and documentation.
- `Healthcare_Analysis.pbix`: Power BI file for the final dashboard.
- `Dataset.csv`: Sample dataset used for analysis.
- `DAX_Functions.txt`: List of DAX measures used.
- `Visualizations/`: Screenshots of key visualizations.
- `Final_Report.pdf`: PDF version of the final report.

## LinkedIn Article
[Read the LinkedIn Article](#)
