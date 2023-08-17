
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


<p align="center">
  <img width="460" height="300"src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/polar_plot_land.png">
</p>



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


## Compute Correlation between CO2 and Temperature

We load the CO2 data, calculate the correlation between mean land surface temperature and CO2 levels over a common range of years. This is done by combining temperature and CO2 datasets using inner merge and calculates the correlation coefficient to assess their relationship.

Below is a scatter plot with temperature on the x-axis and CO2 levels on the y-axis, where each point is colored based on the year. It also adds a regression line to the plot. The correlation coefficient between temperature and CO2 is calculated and displayed.


<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/correlation_co2.png">
</p>



## Plot Temperature Vs Year for each City

This plot gives temperature increase over the time for the city London.

We can plot the same for any city over the globe amongst the chosen cities.

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/temp_year_london.png">
</p>




