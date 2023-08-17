
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
Installing the Libraries

```bash
pip install seaborn
pip install netCDF4
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

## Visualization of Land Surface Temperature Change For Specific Cities

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/citywise_plot.png">
</p>


## Ocean Surface Temperature Data Extraction

We repeat the same procedure to extract temperature data for Ocean surface.


## Visualization of Mean Ocean Surface Temperature Change


<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Ocean_surface.png">
</p>


## Visualization of Ocean Surface Temperature Change Separately

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/ocean_plots.png">
</p>

## Plot for Atmospheric Carbon Dioxide Emission Over the Years

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Co2_plot.png">
</p>

## Correlation Between Temperature and CO2

We load the CO2 data, calculate the correlation between mean land surface temperature and CO2 levels over a common range of years. This is done by combining temperature and CO2 datasets using inner merge and calculates the correlation coefficient to assess their relationship.

Below is a scatter plot with temperature on the x-axis and CO2 levels on the y-axis, where each point is colored based on the year. It also adds a regression line to the plot. The correlation coefficient between temperature and CO2 is calculated and displayed.


<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/correlation_co2.png">
</p>


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


## Conclusion 

- After a comprehensive analysis of the data, it becomes apparent that volcanic eruptions and solar irradiance variations are not the main drivers of the temperature increase.
- While these natural factors do have some influence, their impact on temperature changes seems to be relatively small. 

Therefore, we can deduce that the primary cause of the temperature rise is the CO2 emissions resulting from human activities.

