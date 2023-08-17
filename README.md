
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
    
## Data Extraction 

<p align="center">
  <img width="180" height="400" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/data_extraction.jpg">
</p>


In data extraction the code reads temperature data from a NetCDF file for various cities' latitudes and longitudes, matches the available dates with a pre-defined date range, calculates squared distances to find the nearest point on the grid for each city, and constructs a dataframe containing city, temperature, location, and date information for further analysis.

Similarly for Ocean data, the code extracts ocean temperature data from a NetCDF file for various ocean coordinates, matches available dates, calculates squared distances to find the nearest grid point, and constructs a dataframe containing ocean temperature, location, and date information for further analysis.





## Calculating Percentage Increase in Temperature for Cities

We calculate the temperature increase percentage for each city by iterating through grouped data for each city. We calculate the temperature increase between a specified start and end year, and stores the results in a DataFrame 

<p align="center">
  <img width="460" height="300" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/temperature_increase_data_citywise.jpg">
</p>


## Calculating Mean Land Surface Temperature

In this we calculate the mean Land Surface Temperature (LST) by grouping temperature data by year. Then create a DataFrame storing years and corresponding mean temperatures. The minimum and maximum mean LST values are calculated and displayed.
## Plot Temperature vs Year for Land Surface Data


<p align="center">
  <img width="460" height="400" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Global_Mean_Temperature_Change.gif">
</p>

## Plot Temperature vs Year for Ocean Surface Data

<p align="center">
  <img width="760" height="400" src="https://github.com/ACM40960/project-abolipathak/blob/main/Images/Mean_Ocean_Surface_Temperature.jpg">
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




