 # Objective
 The objective of this project was to predict the number of taxi pickups that will happen in next 10 minutes given the lattitide and longitude of the region in New York city. 
 
 # Data source
Ge the data from : http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml (2016 data)
The data used in the attached datasets were collected and provided to the NYC Taxi and Limousine Commission (TLC) 

# Machine Learning Problem
Time-series forecasting and Regression.

To find number of pickups, given location cordinates(latitude and longitude) and time, in the query reigion and surrounding regions.
To solve the above we would be using data collected in Jan - Mar 2015 to predict the pickups in Jan - Mar 2016.

# Performance metrics
1. Mean Absolute percentage error(MAPE).
2. Mean Squared error(MSE).

# Data cleaning
Removed all the outlier points.
By outlier points we mean the following 
1. Pickups had lattitide and longitude outside New York .
2. The trip duration id greater than 12 hours.
3. The fare price is greater than 1000 dollars.
4. The trip distance is very long say more than 200 mile.
5. The average speed is very high say more than 60 miles/hour.

# Approach
1. First we divided the whole dataset into bins of 10 minutes .
2. We divided the whole dataset into 30 clusters which divided the whole New York city into 30 different sections based on the pickup density. We tried to keep the cluster center at a distance of 2 mile from each other.
3. We used the number of pickups in the last 5 bins as a feature and the  top 5 amplitide and their corresponding frequency of the waveform of the pickups of the prevoius bins as a feature.
4. We take the lattitude and longitude to decide the cluster for which we have to predict the pickups.

# Modelling
We tried various models such as exponential model which used prevoius 5 pickups in that region , linear regression, random forest and XgBoost.
The best model was random forest and XGBoost with MAPE of 11.8%.
