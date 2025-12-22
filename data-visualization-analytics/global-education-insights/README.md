# Global Education Insights

## Project Overview

This project analyzes worldwide education data and its relationships with gender, proficiency levels, and socioeconomic indicators. Using Python and SQLite, the analysis explores patterns in educational outcomes across countries through database management, data quality assessment, and exploratory visualization.

---

## Objectives

- Build a relational database structure for education data
- Analyze gender gaps in educational completion rates
- Examine correlations between reading and math proficiency
- Explore relationships between education and socioeconomic factors

---

## Key Findings

- **Gender Gap**: Completion rate disparities exist between genders, varying by education level (primary, lower-secondary, upper-secondary)
- **Proficiency Correlation**: Strong positive correlation between reading and math proficiency scores across educational stages
- **Tertiary Education**: Negative correlation (r = -0.68) between tertiary enrollment and birth rate
- **Regional Patterns**: Choropleth maps reveal geographic clusters in tertiary enrollment, birth rates, and unemployment

---

## Database Structure

The SQLite database consists of five normalized tables:

| Table | Description |
|-------|-------------|
| countries | Country names and identifiers |
| out_of_school_rates | Out-of-school percentages by education level |
| completion_rates | Completion rates by gender and level |
| education_proficiency | Reading and math proficiency scores |
| social_indicators | Birth rate, unemployment, tertiary enrollment |

---

## Methodology

1. **Database Creation**: Build and populate SQLite tables from Global_Education.csv
2. **Data Cleaning**: Verify dtypes, handle missing values, remove duplicates, fix country-name typos
3. **Outlier Analysis**: Boxplots and IQR method for outlier detection
4. **Exploratory Analysis**: Bar charts, correlation heatmaps, scatter plots
5. **Geographic Visualization**: Plotly choropleth maps for key indicators

---

## Project Structure

| Path | Description |
|------|-------------|
| src/global-education-insights-code.ipynb | Main analysis notebook |
| src/global-education-insights-report.pdf | Detailed findings report |
| data/ | Global education dataset |

---

## Technologies Used

- **Language**: Python 3.x
- **Database**: SQLite
- **Libraries**: pandas, numpy, matplotlib, seaborn, plotly
- **Visualization**: Choropleth maps, correlation heatmaps, bar charts
