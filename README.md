
<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Global_warming_logo.jpeg">
</p>

<p align="center">
  
# Investigating the Drivers of Global Warming

## Overview

This project aims to comprehensively examine the factors contributing to global warming by analyzing a diverse dataset of global surface temperature measurements, atmospheric CO2 concentrations, volcanic activity, and solar irradiance over various timescales. By employing robust statistical methods and data visualization techniques, we will explore the relationships between these variables to discern whether human-made factors, particularly increased CO2 emissions, are the primary drivers of observed global temperature increases
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

In this we calculate the mean Land Surface Temperature (LST) by grouping temperature data by year. Below are the steps to obtain the data 

<p align="center">
  <img width="180" height="400" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/data_extraction.jpg">
</p>

- Extract Temperature, latitude and longitude present in .netcdf file.
- Actual latitude and longitude for each city are different than those present in .netcdf file. Hence we need to compute square distance between each latitude and longitude of respective city and find the nearest co-ordinate.
- Extract data for that city and add it in final dataframe.
- Repeat step 3 till data for each city is extracted and present in final dataframe.
- Final dataframe will contain Date, city, temperature, actual latitude, actual longitude, Nearest latitude, Nearest longitude and country column.

Note: Grided Form means latitude and longitude are divided into a sequence from max to min values. For e.g. latitude range from -90 to +90. Then it will be present as -90, -88, -86,....., +86, +88, +90.


## Visualization of Mean Land Surface Temperature Change 


<p float="left">
  <img src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/polar_plot_land.png" height="150" width="250" />
  <img src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/line_mean_land.png" height="150" width="250" />
</p>

<p align="left">
  <img width="250" height="300"src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/polar_plot_land.png">
</p>

<p align="right">
  <img width="250" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/line_mean_land.png">
</p>


Above indicates a noticeable increase in mean land surface temperatures from 1880 to 2022.
The temperature range rose from -0.35°C to 1.3°C over a 42-year span which signifies a significant 471% temperature increase during this period.
For instance, considering the city of Berlin, the temperature climbed from 1.16°C to 1.64°C in 42 years.


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

## Role of Solar Irradiations for Rise in Temperature

## Correlation between Temperature and Total Solar Irridance

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/tsi_scatterplot.png">
</p>



