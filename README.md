# Soil_Moisture_Prediction
This code loads and processes user data from two CSV files named user1_data.csv and user2_data.csv. It resamples the data to a common time interval of every 5 minutes, cleans the data by dropping NaN values and removes unnecessary columns. The cleaned data is then split into a training set and a test set, which are used to train a linear regression model. The root mean squared error (RMSE) is calculated to evaluate the performance of the model.

Files
user1_data.csv: contains data from user 1.
user2_data.csv: contains data from user 2.
new_data.csv: contains the merged and resampled data from user1_data.csv and user2_data.csv.
Dependencies
This code requires the following dependencies:

numpy
pandas
matplotlib
sklearn
