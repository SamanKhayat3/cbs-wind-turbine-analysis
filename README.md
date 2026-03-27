# Wind Turbine Performance Analysis (CBS Open Data)

## Overview

This project analyzes wind turbine performance in the Netherlands using publicly available data from Statistics Netherlands (CBS).

The objective is to evaluate how turbine height relates to electricity production efficiency, measured as electricity production per unit of rotor area.

---

## Question and Key Insight

This analysis investigates how electricity production per rotor area varies across wind turbine height classes in the Netherlands, using normalized output to isolate efficiency differences beyond blade size.

Based on average data from 2010–2024, the results show a clear positive relationship: taller turbines produce more electricity per unit of rotor area, with turbines ≥96 meters demonstrating the highest performance. This indicates that increased turbine height is associated with greater efficiency.

---

## Data Source

- CBS Open Data (StatLine)
- Dataset: **Windenergie op land; productie en capaciteit naar ashoogte**
- Dataset ID: `71227NED`
- Link: https://opendata.cbs.nl/#/CBS/nl/dataset/71227ned/table
- Accessed on: 27-03-2026

---

## Methodology

1. Data was retrieved programmatically from the CBS OData API, ensuring reproducibility and avoiding manual data handling.
2. Relevant metadata (time periods, turbine height classes, and measures) was merged into the dataset.
3. The variable *electricity production per rotor area* was selected as the key performance metric.
4. Data was filtered for the period 2010–2024 to ensure a consistent and comparable time window, as earlier data is less complete.
5. For each turbine height class:
   - Mean yearly production per rotor area was calculated
   - Year-to-year standard deviation was calculated
6. Results were visualized using a bar chart with error bars.

---

## How to Run

1. Clone or download this repository

2. Install dependencies:

pip install -r requirements.txt

3. Start Jupyter Notebook:

jupyter notebook

4. Open and run the notebook file:

- cbs_wind_turbine_analysis_code.ipynb

---

## Repository Structure


- README.md — project description and instructions  
- requirements.txt — Python dependencies  
- cbs_wind_turbine_analysis_code.ipynb — main analysis notebook  


---

## Assumptions & Limitations

- Electricity production per rotor area is a valid proxy for efficiency after normalizing for blade size.
- Averaging over 2010–2024 provides a representative comparison across height classes.
- Data prior to 2010 is excluded due to lower completeness.
- Differences within height classes do not dominate the observed trends.
- Due to data limitations, this analysis does not control for potential confounding factors such as turbine location, technology, or installation year, which may influence the observed performance differences.
