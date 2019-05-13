The objective is to rewrite the Bike Sharing analysis done in the Python for Statistical Programming subject using Dask data structures and ecosystem instead of plain pandas.

Task description:
Training data: whole 2011 and first 3 quarters of 2012.
Test data: 4th quarter of 2012. Do not fit your models with these data! They should just be used to see how good/bad your model predictions are.
Error metric: R2 score (scikit-learn's default for regression).

Features to use: at least the ones present in the data (except for cnt). Do not use both casual and registered columns, as cnt=casual+registered (you may use one, but not both). Additionally, you can use other sources of data you deem appropriate to predict from extra features.

The maximum score of the assignment is 4 points and the grading will be as follows:
Creation of a git repository with a proper README, incremental commits, and some sort of automatic or programmatic download of the data before the analysis (1 point). Notice that the data should not be checked out in the repository. Including data files in git repositories is considered a bad practice.
Use of dask.dataframe and distributed.Client for all the data manipulation (2 points). Remember that calling .compute() in a Dask DataFrame turns it into a pandas dataframe, which resides in RAM and loses the distributed advantages. The more Dask structures are used, the higher the grade.
Use of Dask-ML for distributed training and model selection https://ml.dask.org/ (1 point). See below for inspiration.

Short data description (copied from the web)
Original columns:
weathersit: 1: Clear, Few clouds, Partly cloudy, 2: Mist and Cloudy, Mist and Broken clouds, Mist and Few clouds, Mist 3: Light Snow, Light Rain and Thunderstorm and Scattered clouds, Light Rain an dScattered clouds 4: Heavy Rain and Ice Pallets and Thunderstorm and Mist, Snow and Fog instant: record index
dteday: date
season: season (1:spring, 2:summer, 3:fall, 4:winter)
yr: year (0: 2011, 1:2012)
mnth: month ( 1 to 12)
holiday: weather day is holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
weekday: day of the week
workingday: if day is neither weekend nor holiday is 1, otherwise is 0.
temp: Normalized temperature in Celsius. The values are divided to 41 (max)
atemp: Normalized feeling temperature in Celsius. The values are divided to 50 (max)
hum: Normalized humidity. The values are divided to 100 (max)
windspeed: Normalized wind speed. The values are divided to 67 (max)
casual: count of casual users
registered: count of registered users
cnt: count of total rental bikes including both casual and registered