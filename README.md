# Total trip duration prediction of taxi trips in New York City

In this competition, Kaggle is challenging you to build a model that predicts the total ride duration of taxi trips in New York City. Your primary dataset is one released by the NYC Taxi and Limousine Commission, which includes pickup time, geo-coordinates, number of passengers, and several other variables.

The competition dataset is based on the 2016 NYC Yellow Cab trip record data made available in Big Query on Google Cloud Platform. The data was originally published by the NYC Taxi and Limousine Commission (TLC). The data was sampled and cleaned for the purposes of this playground competition. Based on individual trip attributes, participants should predict the duration of each trip in the test set.

### Data Fields

| Data Fields        | Meaning | 
| :----------------: | :------ | 
| id                 | a unique identifier for each trip     | 
| vendor_id          | a code indicating the provider associated with the trip record      | 
| pickup_datetime    | date and time when the meter was engaged     | 
| dropoff_datetime   | date and time when the meter was disengaged     | 
| passenger_count    | the number of passengers in the vehicle (driver entered value)     | 
| pickup_longitude   | the longitude where the meter was engaged     | 
| pickup_latitude    | the latitude where the meter was engaged     | 
| pickup_latitude    | the latitude where the meter was engaged     | 
| dropoff_longitude     | the longitude where the meter was disengaged     | 
| dropoff_latitude     | the latitude where the meter was disengaged     | 
| store_and_fwd_flag | This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server - Y=store and forward; N=not a store and forward trip     | 
| trip_duration      | duration of the trip in seconds     | 

### File descriptions

- train.csv - the training set (contains 1458644 trip records)
- test.csv - the testing set (contains 625134 trip records)
- target.csv - this set contains the actual trip durations (used for testing the model)

## Project Description

### 1. Data Analysis

In this part of the project, I have done some preprocessing by removing the outliers out of the train and test data sets. Also, I have added new columns to better describe each trip, including the day, month, year, hour, etc. I have created some histograms, scatter plots, and diagrams to display useful information from the data including the busiest pickup days, the trips per day period, the average trip duration per day of the week, etc. Finally, I calculated the manhattan distance between each pickup and dropoff point in order to increase dramatically the model's accuracy in predicting the total ride duration in the next part of the project.


### 2. Clustering and trip duration prediction

In this part of the project, I have used K-Means clustering and the elbow method to find the optimal number of clusters. For the trip duration prediction, I used RandomForestRegressor from the sklearn library. Also, by using GridSearchCV I managed to increase the model's accuracy by finding the best possible set of parameters. Finally, I found the performance of the model by calculating the MAE (Mean Absolute Error) and MSE (Mean Square Error).


### 3. Bonus

In the bonus part of this assignment, I have created a New York city map displaying all the pickup points, using the folium library. Moreover, I have created more graphical representations and features (for example a new label that indicates if the trip happened on a weekend) to extract more conclusions from the data.
