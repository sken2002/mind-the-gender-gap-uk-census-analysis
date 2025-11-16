# UK 2011 Census: A Visual Analysis of Demographic & Gender Disparities

**Project Objective:** To explore the 2011 UK Census microdata to uncover key demographic and economic patterns across England and Wales, with a special focus on geospatial disparities in work, gender, and health.

---

## Key Questions Addressed

This analysis seeks to answer several key questions about the population:
* What is the regional distribution of average weekly work hours, and how does this differ between men and women?
* How is the workforce structured, and what is the gender composition of different occupations?
* How do major life events (like marital status) correlate with economic activity?
* What is the relationship between age and self-reported health status?
* Using a decomposition model, what observable factors (like occupation, industry, and family status) contribute to the gender gap in work hours, and how much remains unexplained?

---

## Data Sources

1.  **Primary Dataset:**
    * **File:** `2011 Census Microdata Teaching File.csv`
    * **Source:** ONS Census Government website.
    * **Note:** This file is included in the repository.

2.  **Geospatial Data:**
    * **File:** `NUTS1_Jan_2018_SGCB_in_the_UK.shp`
    * **Source:** ONS Open Geography Portal.
    * **Note:** The shapefile and its related files (`.dbf`, `.shx`, etc.) are included in the `/data` folder for reproducibility.

---

## Key Findings & Visualizations

The analysis is presented as a series of static (Matplotlib/Seaborn) and interactive (Plotly) visualizations.

1.  **The Regional Work-Hour Gender Gap:** A 2x2 dashboard that maps and ranks average weekly work hours for men and women.
    * **Insight:** Men consistently work longer hours, but the gap varies significantly by region. The discrepancy is most pronounced in London, where men work the longest hours and women work the shortest.

2.  **The "Maternity Penalty":** A line graph showing the average hours worked by age and gender, complete with a 95% confidence interval.
    * **Insight:** It highlights a distinct dip in work hours for women in the 35-44 age bracket, a trend not seen for men, correlating with the average age of childbirth.

3.  **Gender Composition of Occupations:** An interactive 100% stacked bar chart.
    * **Insight:** Reveals stark gender segregation. "Admin" and "Caring/Leisure" are heavily female-dominated, while "Skilled Trades" and "Process/Machine" are overwhelmingly male.

4.  **Economic Activity by Marital Status:** A 100% stacked bar chart illustrating how economic roles shift with marital status.
    * **Insight:** "Looking after home" is a significant category for married individuals but almost non-existent for single individuals, who are primarily "Employees."

5.  **The Age-Health Connection:** A heatmap showing the percentage breakdown of health status by age.
    * **Insight:** Clearly demonstrates the strong negative correlation between age and self-reported health, with the percentage of "Very Good" health reports declining in older age brackets.

---

## Modeling the Gender-Hours Gap

An **Oaxaca-Blinder decomposition** was used to break down the gap in average work hours. The model confirms that observable factors like occupation, industry, and family composition account for a portion of the disparity. However, a significant part of the gap remains "unexplained," suggesting that unobserved variables (such as education, personal choice, or potential discrimination) play a major role.

---

## How to Reproduce This Work

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/sken2002/mind-the-gender-gap-uk-census-analysis.git](https://github.com/sken2002/mind-the-gender-gap-uk-census-analysis.git)
    ```
2.  **Install dependencies:** This project requires Python 3 and the following libraries. You can install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn geopandas plotly scipy patsy statsmodels ipython
    ```
    *(Note: `geopandas` may have additional installation requirements like `rtree` or `pygeos` depending on your system. Please see its documentation for details.)*
3.  **Run the notebook:** Open and run the `Group 2 Final Assignment.ipynb` notebook to reproduce all analyses and visualizations. All data paths are relative and should work correctly.