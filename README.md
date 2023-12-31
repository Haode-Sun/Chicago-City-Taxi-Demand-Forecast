# Chicago City Taxi Demand Forecast

## Introduction
This project selected Chicago taxi travel data from October 1, 2022 to November 30, 2022, combined with hourly weather data, census data and socioeconomic characteristics, and established four prediction models. It is verified that the best model fitting degree can reach 0.763. In addition, I also calculated the number of taxis per hour and per census tract to explore its temporal and spatial autocorrelation.  
## Data Description
I have chosen three different data sources for this project:  

**1.Chicago taxi trip records:** https://data.cityofchicago.org/Transportation/Taxi-Trips/wrvz-psew  
The data comes from a dataset the official Chicago Data Portal collects. I chose to go for two months of trip data, and to avoid the impact of specific holidays that might disrupt expected demand on a given weekend or weekday, I chose a study period of two months of data from October 1, 2022, to November 30, 2022, avoiding national holidays (e.g., Christmas).  

**2.Weather data:** https://www.visualcrossing.com/weather/weather-data-services  
I collected hourly weather data from visual crossing for Chicago from October to November 2022 and chose three metrics as predictor variables, including temperature, precipitation and wind speed.  

**3.Census and Sociodemographic information**  
I used the Cenpy library to explore and query the US Census API and return Pandas Dataframes. I obtained median income, race (calculated as the proportion of the population that is white), age, and calculated average commuting time and public transport preferences as predictor variables.  

## Methods
- Splitting training and testing  
This project split two training and testing datasets based on time: one before 20 November 2022 as the training set and the other after 20 November 2022 as the testing set.The feature variables selected for model prediction are time, total population, median income, ethnicity, average commute time, transportation preference, and weather factors, including temperature, precipitation, and wind speed.  

- Check Error Metrics  
I introduce Mean Squared Error (Mean Squared Error) as an indicator to measure, which represents the expected value of the square of the difference between the actual value and the predicted value. Similarly, the smaller the value of MSE, the closer the prediction result of the model is to the true value.  
## Conclusion
| Model                | MAE     | MSE     | R2    |
|----------------------|---------|---------|-------|
| Support Vector Machine | 11.158 | 461.274 | -0.145|
| Random Forest        | 2.707   | 95.640  | 0.763 |
| Logistic Regression  | 11.810  | 536.048 | -0.330|
| xgboost              | 0.2852  | 0.237   | 0.999 |



