
<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Global_warming_logo.jpeg">
</p>

<p align="center">
  
# Investigating the Drivers of Global Warming

## Overview

This project aims to comprehensively examine the factors contributing to global warming by analyzing a diverse dataset of global surface temperature measurements, atmospheric CO2 concentrations, volcanic activity, and solar irradiance over various timescales. By employing robust statistical methods and data visualization techniques, we will explore the relationships between these variables to discern whether human-made factors, particularly increased CO2 emissions, are the primary drivers of observed global temperature increases

## Objective

- Determine temperature trends at distinct geographical locations.
- Calculate and analyze the global surface average temperature variation over time.
- Investigate the correlation between levels of CO2 and temperature patterns.
- Explore the potential impact of volcanic eruptions on global surface temperature changes.
- Examine the influence of solar irradiance activity on variations in global surface temperature.

## Authors

- [@abolipathak](https://github.com/abolipathak)

- [@YashPimpale27](https://github.com/YashPimpale27)
## Installation

</p>

Libraries Used

```bash
import pandas as pd
import numpy as np
import netCDF4 as nc
from datetime import datetime, timedelta
import matplotlib.pyplot as plt
import seaborn as sns
from matplotlib.lines import Line2D
import matplotlib as mplt
import cartopy.crs as ccrs
import cartopy.feature as cfeature
import PIL
```

## Land Surface Temperature Data Extraction 

Monthly Temperature data for each latitude and longitude from year 1880-2023 is present in a grided form in .netcdf file. We need to extract data for specific cities from this .netcdf file for all the years. Below steps are followed :

<p align="center">
  <img width="180" height="400" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/data_extraction.jpg">
</p>

- Extract Temperature, latitude and longitude present in .netcdf file.
- Actual latitude and longitude for each city are different than those present in .netcdf file. Hence we need to compute square distance between each latitude and longitude of respective city and find the nearest co-ordinate.
- Extract data for that city and add it in final dataframe.
- Repeat above step till data for each city is extracted and present in final dataframe.
- Final dataframe will contain Date, city, temperature, actual latitude, actual longitude, Nearest latitude, Nearest longitude and country column.

Note: Grided Form means latitude and longitude are divided into a sequence from max to min values. For e.g. latitude range from -90 to +90. Then it will be present as -90, -88, -86,....., +86, +88, +90.

Below is the Final extracted dataset obtained.

<p align="center">
  <img width="550" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/land_extracted_data.jpg">
</p>

## Visualization of Mean Land Surface Temperature Trend

The gif depicts the mean land surface temperature for 12 months as line on the polar scale. Each line indicates mean temperature of a respective year with inner most line indicating year 1880 and outer most as year 2022.

<p align="center">
  <img width="500" height="500" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Global_Mean_Temperature_Change_V3.gif">
</p>

Below figure depicts a line graph with mean land temperature on Y-axis and Year on X-axis.

<p align="center">
  <img width="550" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Mean_Land_Surface_Temperature_1.jpg">
</p>

Above figures indicate a noticeable increase in mean land surface temperatures from 1880 to 2022.
The temperature range rose from -0.35°C to 1.3°C over a 42-year span which signifies a significant 471% temperature increase during this period.

## Visualization of Land Surface Temperature Trend For Specific Cities

<p align="center">
  <img width="700" height="500" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/citywise_plot.png">
</p>


## Ocean Surface Temperature Data Extraction

We repeat the same procedure mentioned above (Land Surface Temperature) to extract temperature data for Ocean surface.

## Visualization of Mean Ocean Surface Temperature Trend

<p align="center">
  <img width="620" height="450" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Ocean_surface.png">
</p>

## Oceanwise Surface Temperature Trends

<p align="center">
  <img width="620" height="450" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/ocean_plots.png">
</p>

## Correlation Between Temperature and CO2

First load the yearwise atmospheric Carbon dioxide emission data and visualize the data using barplot to observe its trend.

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Co2_plot.png">
</p>

The atmospheric carbon dioxide (CO2) levels have exhibited a consistent upward trend over the course of time. The initial recorded atmospheric CO2 concentration in the year 1959 was 315.98 parts per million (ppm), while in the year 2022, it was measured to be 418.56 ppm.

Since CO2 levels in the atmosphere have been steadily rising, let's investigate if this has anything to do with the increase in temperature.

We now calculate the correlation between mean land surface temperature and CO2 levels over a common range of years to assess their relationship. This is done by combining temperature and CO2 datasets using inner merge.

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/correlation_co2.png">
</p>

The above scatter plot with temperature on the x-axis and CO2 levels on the y-axis, where each point is colored based on the year. It also adds a regression line to the plot which indicates the trajectory of linear relationship. It reveals a significant positive correlation between the two, substantiated by a Pearson correlation coefficient of 0.951. This coefficient indicates a strong linear relationship between the two variables, suggesting that as CO2 concentrations increase, there is a corresponding elevation in temperature levels.

## Role of Volcanic Eruptions in Rising CO2

The substantial volume of CO2 emissions has reached a level where sensors struggle to differentiate between CO2 originating from volcanic sources and CO2 generated by human activities. As a consequences, there is currently a lack of available data specifically attributing CO2 emissions to volcanic sources. Hence we conducted a data modelling procedure to derive estimations of CO2 emissions originating from volcanic activities.

## Data Collection and Integration

We have dataset containing amount of sulpher dioxide released during volcanic eruptions. Also we have CS ratio for few volcanos which is the ratio of amount of carbon dioxide per sulpher dioxide present in gases released during respective volanic eruption. Hence we need to predict missing CS values using a statistical machine learning model. For this, we need to prepare data before passing it as input to the regression model. 


<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/volcano_flowchart.jpg">
</p>

## Proportion of Atmospheric CO2 Vs Volcanic CO2 Over Time

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/volcanic_co2.png">
</p>

It is evident from the plot that atmospheric CO2 levels are significantly higher than volcanic CO2 emissions. Atmospheric CO2 levels have been steadily increasing over the years, while volcanic CO2 emissions remain relatively stable. This highlights the substantial impact of human activities on atmospheric CO2 levels

## Role of Solar Irradiations for Rise in Temperature

## Correlation between Temperature and Total Solar Irridance

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/tsi_scatterplot.png">
</p>

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Temp_Solar_Plot.jpg">
</p>

## Conclusion 

- After a comprehensive analysis of the data, it becomes apparent that volcanic eruptions and solar irradiance variations are not the main drivers of the temperature increase.
- While these natural factors do have some influence, their impact on temperature changes seems to be relatively small. 

Therefore, we can deduce that the primary cause of the temperature rise is the CO2 emissions resulting from human activities.



Installation :

https://cdf.gsfc.nasa.gov/html/sw_and_docs.html
