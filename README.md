### OBJECTIVE ####
The objective is to rewrite the Bike Sharing analysis done in the Python for Statistical Programming subject using Dask data structures and ecosystem instead of plain pandas.

### DATA ####
Predict the total number of bicycle users on an hourly basis. https://www.kaggle.com/marklvl/bike-sharing-dataset/downloads/Bike-Sharing-Dataset.zip/1 (Overview: https://www.kaggle.com/marklvl/bike-sharing-dataset/home)

### TASK DESCRIPTION ####
- **Training data:** whole 2011 and first 3 quarters of 2012.
- **Test data:** 4th quarter of 2012. Do not fit your models with these data! They should just be used to see how good/bad your model predictions are.
- **Error metric:** R2 score & RMSE

**Features to use:** at least the ones present in the data (except for cnt). Do not use both casual and registered columns, as cnt=casual+registered (you may use one, but not both). Additionally, you can use other sources of data you deem appropriate to predict from extra features.

### DATA DESCRIPTION ####
##### Original columns:
- weathersit: 1: Clear, Few clouds, Partly cloudy, 2: Mist and Cloudy, Mist and Broken clouds, Mist and Few clouds, Mist 3: Light Snow, Light Rain and Thunderstorm and Scattered clouds, Light Rain an dScattered clouds 4: Heavy Rain and Ice Pallets and Thunderstorm and -  Mist, Snow and Fog instant: record index
- dteday: date
- season: season (1:spring, 2:summer, 3:fall, 4:winter)
- yr: year (0: 2011, 1:2012)
- mnth: month ( 1 to 12)
- holiday: weather day is holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
- weekday: day of the week
- workingday: if day is neither weekend nor holiday is 1, otherwise is 0.
- temp: Normalized temperature in Celsius. The values are divided to 41 (max)
- atemp: Normalized feeling temperature in Celsius. The values are divided to 50 (max)
- hum: Normalized humidity. The values are divided to 100 (max)
- windspeed: Normalized wind speed. The values are divided to 67 (max)
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered
