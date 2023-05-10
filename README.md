#  Data-Transformation-and-Cleaning-Using-Pandas

This project involves the analysis of energy data from various sources, including the United Nations, World Bank, and Scimago Journal and Country Rank. The goal is to extract insights and trends related to energy supply, renewable electricity production, GDP, and scientific journal contributions in the field of Energy Engineering and Power Technology.

## Dataset Description

1. **Energy Indicators**: This dataset contains indicators of energy supply and renewable electricity production for different countries. It is sourced from the United Nations and is available in the file [Energy Indicators.xls](Energy%20Indicators.xls). The dataset is cleaned and transformed to remove unnecessary columns, convert energy supply units, handle missing values, and rename countries.

2. **World Bank GDP**: This dataset provides the GDP (Gross Domestic Product) of countries from 1960 to 2015. It is sourced from the World Bank and is available in the file [world_bank.csv](world_bank.csv). The dataset is processed to skip the header and rename certain countries for consistency with other datasets.

3. **Scimago Journal and Country Rank**: This dataset ranks countries based on their journal contributions in the field of Energy Engineering and Power Technology. It is obtained from [Scimago Journal and Country Rank](http://www.scimagojr.com/countryrank.php?category=2102) and is available in the file [scimagojr-3.xlsx](scimagojr-3.xlsx).

## Project Steps

1. **Step 0: Data Preparation**: In this step, the energy dataset is loaded from the `Energy Indicators.xls` file, and data cleaning operations are performed. Unnecessary columns are removed, column labels are updated, energy supply is converted to gigajoules, missing values are handled, and country names are standardized.

2. **Step 1: Loading GDP Data**: The GDP dataset is loaded from the `world_bank.csv` file. The header is skipped, and certain country names are renamed for consistency.

3. **Step 2: Loading ScimEn Data**: The Scimago Journal and Country Rank dataset is loaded from the `scimagojr-3.xlsx` file.

4. **Step 3: Merging Datasets**: The three datasets (Energy, GDP, and ScimEn) are merged into a new dataset using the intersection of country names. Only the last 10 years of GDP data (2006-2015) and the top 15 countries by Scimagojr Rank are considered. The resulting dataset has 20 columns and 15 entries.

5. **Step 4: Lost Entries Calculation**: This step calculates the number of entries lost during the dataset merging process.

6. **Step 5: Average GDP Calculation**: The average GDP over the last 10 years is calculated for each country. Missing values are excluded from the calculation. The results are sorted in descending order.

7. **Step 6: Mean Energy Supply per Capita**: The mean value of the 'Energy Supply per Capita' column is calculated.

8. **Step 7: Maximum % Renewable Country**: The country with the maximum percentage of renewable energy (% Renewable) is identified along with the corresponding percentage.

9. **Step 8: Maximum Self-Citations to Total Citations Ratio**: A new column is created to represent the ratio of self-citations to total citations. The country with the highest ratio is determined.

10. **Step 9: High Renewable Countries**: A new column is created to identify countries with a % Renewable value at or above the median. Countries are marked with '1' if they meet the criteria and '0' otherwise.

