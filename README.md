# Cairo vs. Global Temperature Trends Analysis

## Overview  
This project examines historical temperature trends for Cairo versus global averages. It explores how local temperatures compare to the global trend, providing insights into regional climate patterns and their relation to global changes.

## Data Sources  
- **City Data:** Contains columns such as year, city, country, and average city temperature (for Cairo, Egypt).  
- **Global Data:** Contains global average temperature data by year.

## Methodology  
1. **Data Gathering:**  
   - A SQL query was used to extract essential columns from the joined `city_data` and `global_data` tables:
     ```sql
     SELECT c.year, c.city, c.country, c.avg_temp AS city_temp, g.avg_temp AS global_temp
     FROM city_data c
     JOIN global_data g ON c.year = g.year
     WHERE c.city = 'Cairo' AND c.country = 'Egypt';
     ```
2. **Data Preparation:**  
   - The extracted data was cleaned and then imported into Excel.
   - A 7-day moving average was calculated for both Cairo’s and the global temperatures using Excel’s `AVERAGE` function, smoothing out short-term fluctuations.
3. **Visualization:**  
   - A line chart was created to compare the trends over time. Two lines illustrate the 7-day moving averages for Cairo and global temperatures, respectively.

## Key Findings  
- **Temperature Comparison:**  
  - Cairo’s average temperature is consistently higher than the global average, and the difference remains steady over the years.
- **Trend Similarity:**  
  - The overall shape of the temperature trends for Cairo mirrors that of the global data. Both datasets exhibit an upward trend, indicating global warming.
- **Temporal Variations:**  
  - The analysis reveals that while the overall global trend is increasing, there are periods of cooling (e.g., between 1830 and 1841 globally) and specific local fluctuations (notably a decrease in Cairo’s temperature between 1817 and 1824).
- **Correlation Analysis:**  
  - A strong positive correlation (r ≈ 0.9129) was observed between the average temperatures of Cairo and the global dataset, indicating that as global temperatures change, Cairo’s temperatures tend to follow a similar pattern.

## Tools & Technologies  
- **SQL:** For data extraction from relational databases.  
- **Microsoft Excel:** Used for computing moving averages and initial data visualization.  
- **Visualization Software:** Additional tools (e.g., Python’s matplotlib or Tableau) can be employed for further analysis if desired.

## How to Reproduce  
1. **Data Extraction:**  
   - Run the provided SQL query to gather the required columns for Cairo and global temperature data.
2. **Data Preparation:**  
   - Import the resulting CSV into Excel and calculate the 7-day moving averages for both temperature datasets.
3. **Visualization:**  
   - Plot the moving averages using Excel’s charting features to replicate the line chart comparing local and global temperature trends.
4. **Analysis:**  
   - Review the chart and compute statistical measures (e.g., correlation coefficient) for quantitative comparison.
