# Predicting-crop-and-soybean-yield-for-Illinois

This project is aimed to develop a model to predict crop yield (corn and
soybean) for Illinois State using data of daily weather information:
precipitation, temperature (maximum and minimum) and annual crop information: corn
yield, soybean yield.

**Data Cleaning: Handling missing values**

The precipitation data were available for all counties of the state with some missing values whereas there is no
data recorded of minimum and maximum temperature for few counties. Since the
temperature does not change much at the same latitude, an algorithm was developed
which used the centroid latitude of each polygon from the shape file of Illinois. The data
adjacent to missing counties (based on a developed algorithm) was used as the proxy
observation for minimum and maximum temperature. The algorithm was developed in
such a way that it could take the next closest county data if the closest county data was
also missing.

**Data Preparation: Developing dataset for model development**

As corn and soybean are planted during April to mid-May and are harvested during mid-
September and mid-October, the period from April to October is considered for the
model development. Based on daily observed weather data, WetDays: number of wet
days, SeasonalTmax: maximum temperature of the season, SeasonalTmin: minimum
temperature of the season, SeasonalAvgTmin: average of the daily minimum temperature
of the season, SeasonalAvgTmax: the average of daily maximum temperature of the
season, SeasonalPrep: total precipitation of the season, GDD: growing degree days
(temperature-dependent mostly used to explain the crop growth), DaysBelowNeg2deg:
number of days when the temperature goes below -2°C, DaysAbove35deg: number of
days when the temperature goes above 35°C were calculated. These are crucial variables
that are generally used to determine/explain crop behavior.

**Model Performance**

Linear Regression</br>
Corn 0.82</br>
Soybean 0.78</br>
Gradient Boosting</br>
Corn 0.95</br>
Soybean 0.93</br>


