# python-api-challenge
Homework 6 Python API

<h2>Global Weather data exploration</h2>
Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

(WeatherPy.ipynb)
In Pandas, we used the OpenWeatherMap API to check the weather of over 600 random cities across the globe. The parameters captured included latitude/longitude, name, cloudiness, humidity, maximum temperature (F), and wind speed.

After double-checking for NaNs and empty data fields, we created multiple scatter plots to determine correlations between multiple variables (like temperature) and latitude (AKA distance from the Equator).

The following shows the correllation between Temperature as a function of Latitude. The closer the city is to the equator (0°), the warmer the maximum temperature, generally.
<img src="/output_data/Fig1.png" />

This chart shows the current % humidity as a function of the city's latitude. The plot shows no clear correllation between the two, although there is a slight bias toward higher humidities.
<img src="/WeatherPy/output_data/Fig2.png" />

This chart shows the % cloudiness as a function of the city's latitude. There is no correllation between the two parameters, but there appear to be closters of cities with the same cloudiness at similar latitudes
<img src="/WeatherPy/output_data/Fig3.png" />

This chart  shows the relationship between wind speed and a city's latitude. There is no correllation between the two, and the data shows a bias toward lower wind speeds.
<img src="/WeatherPy/output_data/Fig4.png" />

<hr>

We also broke down these comparisons into relationships in the Northern Hemisphere versus the Southern Hemisphere. However, it should be noted that there is more landmass and, therefore, more data points randomly placed in the Northern Hemisphere than the Southern Hemisphere. 

In comparing the maximum temperatures from the Northern and Southern Hemispheres by their specific latitudes, there seems to be a much stronger correllation (R value) between temperature and latitude in the Northern Hemisphere:

Northern Hemisphere:
<img src="/WeatherPy/output_data/Fig1A.png" />

Southern Hemisphere:
<img src="/WeatherPy/output_data/Fig1B.png" />

In comparing the percent humidities from the Northern and Southern Hemispheres by their specific latitudes, there again seems to be little to no correllation between the two:

Northern Hemisphere:
<img src="/WeatherPy/output_data/Fig2A.png" />

Southern Hemisphere:
<img src="/WeatherPy/output_data/Fig2B.png" />

In comparing the percent cloudiness from the Northern and Southern Hemispheres by their specific latitudes, there seems to be even less correllation between the two measures:

Northern Hemisphere:
<img src="/WeatherPy/output_data/Fig3A.png" />

Southern Hemisphere:
<img src="/WeatherPy/output_data/Fig3B.png" />

In comparing the wind speeds from the Northern and Southern Hemispheres by their specific latitudes, there seems to be no correllation. A bias toward lower wind speeds is more obvious in the larger N. Hemisphere dataset:

Northern Hemisphere:
<img src="/WeatherPy/output_data/Fig4A.png" />

Southern Hemisphere:
<img src="/WeatherPy/output_data/Fig4B.png" />

<hr>
(VacationPy.ipynb)
In this activity, the perfect Vacation Destination was determined from the previously-acquired list of random cities accessed from the OpenWeatherMap API. A heatmap was to be generated from the top hotel destinations where the city's weather met the following parameters for the perfect getaway:

1. Between 70F and 80F
2. Wind Speed <10mph
3. No cloudiness

After narrowing down the list of 600+ cities to only five destinations, we queried the GoogleMaps API to find the closest Hotel to this city. The hotel name was saved to a new dataframe and mapped on a Google-based HeatMap.
