# NYC-Trip-Duration
## Introduction
![New York City Traffic](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/nyctraffic.jpg)
This is a comprehensive Exploratory Data Analysis for the [New York City Taxi Trip Duration](https://www.kaggle.com/c/nyc-taxi-trip-duration) competition with Python and Data Visualization libraries such as matplotlib and seaborn. I also use [New York City Taxi with OSRM](https://www.kaggle.com/oscarleo/new-york-city-taxi-with-osrm) to support the primary dataset.

The goal of this playground challenge is to predict the duration of taxi rides in NYC based on features like trip coordinates or pickup date and time. We start the exploratory data analysis by loading the dataset using pandas, checking missing values, doing feature engineering,checking outliers and comparing between univariate and bivariate features,improving the model using ML Algorithms(Decision Tree and Gradient Boosting) as regression model.
We also implement Haversine Formula using for calculating the duration between two points(longitude and latitude) as follows 
![Haversine Formula](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/haversineformula.png)
# File descriptions
- train.csv - the training set (contains 1458644 trip records)
- test.csv - the testing set (contains 625134 trip records)
- sample_submission.csv - a sample submission file in the correct format

# Data fields
- id - a unique identifier for each trip
- vendor_id - a code indicating the provider associated with the trip record
- pickup_datetime - date and time when the meter was engaged
- dropoff_datetime - date and time when the meter was disengaged
- passenger_count - the number of passengers in the vehicle (driver entered value)
- pickup_longitude - the longitude where the meter was engaged
- pickup_latitude - the latitude where the meter was engaged
- dropoff_longitude - the longitude where the meter was disengaged
- dropoff_latitude - the latitude where the meter was disengaged
- store_and_fwd_flag - This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server - Y=store and forward; N=not a store and forward trip
- trip_duration - duration of the trip in seconds
