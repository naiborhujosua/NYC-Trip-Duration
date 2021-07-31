# NYC-Trip-Duration
## Introduction
![New York City Traffic](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/nyctraffic.jpg)
This is a comprehensive Exploratory Data Analysis for the [New York City Taxi Trip Duration](https://www.kaggle.com/c/nyc-taxi-trip-duration) competition with Python and Data Visualization libraries such as matplotlib and seaborn. I also use [New York City Taxi with OSRM](https://www.kaggle.com/oscarleo/new-york-city-taxi-with-osrm) to support the primary dataset.

The goal of this playground challenge is to predict the duration of taxi rides in NYC based on features like trip coordinates or pickup date and time. We start the exploratory data analysis by loading the dataset using pandas, checking missing values, doing feature engineering,checking outliers and comparing between univariate and bivariate features,improving the model using ML Algorithms(Decision Tree and Gradient Boosting) as regression model.
We also implement Haversine Formula for calculating the duration between two points(longitude and latitude) as follows 
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

# Exploratory Data Analysis
## Trip Duration Distributon
 ![Trip Duration Distribution](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_1.JPG)<br>
 We do log transformation to the target variable because the evaluation metric in the competition is RMSLE. We can see based off the histogram that the log trip duration is bell-shaped distribution with peak at 6.5.
 
 
  ## Number of Samples and Average Log Trip Duration by Date
 ![Number of Samples and Average Log Trip Duration by Date](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_2.JPG)<br>
 There is a significant drop on January 23, 2016 for the number of taxi trips while the average of Log trip duration ranges between 6.26 to 6.69 with peak on January 23,2016. Furthermore, the number of taxis ranges around 8000 trips.
 
 
 
 
 
 ## Number of Samples and Average Log Trip Duration by Day
 ![Trip Duration Distribution](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_3.JPG)
 The trip volume depicts that there is an increase from monday to friday and decrease from Friday to Sunday. In addition to that, there is a maximum trip volume at over 220,000 occurs on Friday while minimum occurs on Sunday. This patterns also occurs on average log trip duration with the peak on thursday. This implies that people use more taxi trips on weekdays than weekends with. This correlates with the trip duration on average that is longer on weekdays than weekends. 
 
 
 
 
 
 ## Number of Samples and Average Log Trip Duration by Hour
 ![Number of Samples and Average Log Trip Duration by Hour](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_4.JPG)<br>
 This graph depicts that there is a spikes in trip volumne at 8am(Getting to work) and 6pm(head home). Average log trip duration starts increasing around 6 am and decrease after 8 am. This implies that there is a positive correlation between trip volumne and average log trip duration. 
 
 
  ## Average Speed in hour
 ![Average Speed in hour](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_8.JPG)<br>
 The combination of external dataset, we will be able to extract average speed at different time of day and week. The graphs depicts that the change in average speed is inverse to the change of trip volume which means the more taxi on the road , the lower the speed. 
 
 
## Distribution of time duration by number of passengers
 ![Distribution of time duration by number of passengers](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_5.JPG)<br>
We can ssee there are  some taxis which have no passengers. the median based on the boxplot graph is around 3. the other change in the number of passengers from 1 to 6 passengers shows a constanct median. However, there is a drops when adding more than 6.
 
 
 
 
 ## Distribution of time duration by Vendor Id
 ![Trip Duration Distribution](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_6.JPG)
 Based off the vendor id , it depicts thats vendor 1 has more outliers than vendor 2 with same median.
 
 
 
 ## Distance Vs Trip Duration(Haversine Distance)
 ![Distance Vs Trip Duration(Haversine Distance)](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_7.JPG)<br>
 
 
 
 

 
 
 
 ## Total Distance Vs Trip Duration
 ![Total Distance Vs Trip Duration](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_9.JPG)<br>
 
 
 
 
 
 
 ## Total Distance Vs Total Travel Time
 ![Total Distance Vs Total Travel Time](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_10.JPG)<br>
 
 
 
 
 
 
 ## Number of Samples in Train and Test
 ![Number of Samples in Train and Test](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_11.JPG)<br>
 
 
 
 
 
 
 ## Trip Location Distribution of Train and Test Data
 ![Trip Location Distribution of Train and Test Data](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_12.JPG)<br>
 
 
 
 
 
 ## Trip Location Distribution of Train and Test Data
 ![Trip Location Distribution of Train and Test Data](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_13.JPG)<br>
 
 
 
 
 
 ## Feature Importance
 ![Feature Importance](https://github.com/naiborhujosua/NYC-Trip-Duration/blob/main/output_14.JPG)<br>
