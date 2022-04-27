# SF-Real-Estate-Analysis

This repo contains the results of the module 6 challenge. To view the file, open the "Starter_Code" folder and open the "san_francisco_housing.ipynb" file. 

In this module, I assumed the role the role of an analyst at a proptech company that wants to offer an instant, one-click service for people to buy properties and then rent them. The company wants to have a trial of this offering in the San Francisco real-estate market. If the service proves popular, they can then expand to other markets. My Assignment was to use my data visualization skills, including aggregation, interactive visualizations, and geospatial analysis, to find properties in the San Francisco market that are viable investment opportunities.

For this assignment, I createed the following deliverable: A Jupyter notebook that contains my analysis of the housing rental market data for San Francisco. The analysis is complete with professionally styled and formatted interactive visualizations. Specifically, after reading in a csv file into the notebook and creating the DataFrame that was used in the analysis, I was required to create visualizations by using hvPlot and GeoViews.

The main task was to visualize and analyze the real-estate data in the Jupyter notebook by (1) calculating and ploting the housing units per year, (2) calculating and ploting the average prices per square foot, (3) comparing the average prices by neighborhood, (4) building an interactive neighborhood map, and (5) composing an accurate data story.

## Installation Guide

First, install geoviews and hvplot into your development environment. In the workbook, you may then use the read_csv function and Path module, to create a DataFrame by importing the sfo_neighborhoods_census_data.csv file from a named "Resources" folder.

```python
conda install -c pyviz geoviews
conda install -c pyviz hvplot


from pathlib import Path

sfo_data_df = pd.read_csv(
    Path("./Resources/sfo_neighborhoods_census_data.csv")
)

```
---

## Technologies

This project leverages python 3.7 with the following libraries and dependencies:

* [pandas](https://github.com/pandas-dev/pandas) - For manipulating data

* [hvplot](https://github.com/holoviz/hvplot) - High-level plotting API for the PyData ecosystem built on HoloViews

---

### **Calculated and Ploted the Housing Units per Year**

For this part of the assignment, I used numerical and visual aggregation to calculate the number of housing units per year, and then visualized the results as a bar chart. To do so, I completed the following steps: 

(1) Used the `groupby` function to group the data by year and aggregated the results by the `mean` of the groups.

(2) Used the `hvplot` function to plot the `housing_units_by_year` DataFrame as a bar chart and made the x-axis represent the `year` and the y-axis represent the `housing_units`.

(3) Styled and formatted the line plot to ensure a professionally styled visualization.

### **Calculated and Ploted the Average Sale Prices per Square Foot**

Here, I calculated the average prices per square foot, and then visualized the results as a bar chart. To do so, I completed the following steps:

(1) Grouped the data by year, and then average the results. 

(2) Create a new DataFrame named `prices_square_foot_by_year` by filtering out the “housing_units” column. The new DataFrame includes the averages per year for only the sale price per square foot and the gross rent.

(3) Used hvPlot to plot the `prices_square_foot_by_year` DataFrame as a line plot.

(4) Styled and formated the line plot to ensure a professionally styled visualization.

(5) Used both the `prices_square_foot_by_year` DataFrame and interactive plots to answer the following questions:

(A) Did any year experience a drop in the average sale price per square foot compared to the previous year?

(B) If so, did the gross rent increase or decrease during that year?

### **Compared the Average Sale Prices by Neighborhood**

In this section, I used interactive visualizations and widgets to explore the average sale price per square foot by neighborhood. To do so, I completed the following steps:

(1) Created a new DataFrame that groups the original DataFrame by year and neighborhood and then aggregated the results by the `mean` of the groups.

(2) Filtered out the `housing_units` column to create a DataFrame that includes only the `sale_price_sqr_foot` and `gross_rent` averages per year.

(3) Created an interactive line plot with hvPlot that visualizes both `sale_price_sqr_foot` and `gross_rent`. Set the x-axis parameter to the year (`x="year"`). Used the `groupby` parameter to create an interactive widget for neighborhood.

(4) Styled and formated the line plot to ensure a professionally styled visualization.

(5) Used the interactive visualization to answer the following question:

(A) For the Anza Vista neighborhood, is the average sale price per square foot for 2016 more or less than the price that’s listed for 2012?

### **Built an Interactive Neighborhood Map**

For this part of the assignment, I explored the geospatial relationships in the data by using interactive visualizations with hvPlot and GeoViews. To build a map, I used the `sfo_data_df` DataFrame (created during the initial import), which includes the neighborhood location data with the average prices. To do all this, completed the following steps:

(1) Read the `neighborhood_coordinates.csv` file from the `Resources` folder into the notebook, and created a DataFrame named `neighborhood_locations_df`. I set the `index_col` of the DataFrame as “Neighborhood”.

(2) Using the original `sfo_data_df` Dataframe, I created a DataFrame named `all_neighborhood_info_df` that groups the data by neighborhood and then aggregated the results by the `mean` of the group.

(3) Using hvPlot with GeoViews enabled, I created a `points` plot for the `all_neighborhoods_df` DataFrame. 

### **Data Story**

Based on the visualizations that created, I answered the following questions:

(A) How does the trend in rental income growth compare to the trend in sales prices? Does this same trend hold true for all the neighborhoods across San Francisco?

(B) What insights can you share with your company about the potential one-click, buy-and-rent strategy that they're pursuing? Do neighborhoods exist that you would suggest for investment, and why?

---
## Contributors

Brought to you by Wilson Rosa. https://www.linkedin.com/in/wilson-rosa-angeles/.

---
## License

MIT
