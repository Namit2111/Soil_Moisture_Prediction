Soil Moisture Prediction Model

This script performs data cleaning and machine learning operations on two datasets from user1 and user2, and merges them into a new dataset. The merged dataset is then cleaned and preprocessed for use in a multiple linear regression model. The script calculates the Root Mean Squared Error (RMSE) between the predicted and actual values of the test set.

Dependencies:
-Python 3.0 or higher
*pandas
*numpy
*matplotlib
*seaborn
*scikit-learn

#Explanation of each process

Data Files
The script assumes that the following files are present in the working directory:
user1_data.csv: Data from user1
user2_data.csv: Data from user2


Data Operations
The first part of the script involves loading and cleaning the data. Two CSV files, 'user1_data.csv' and 'user2_data.csv', are loaded into two data frames, df1 and df2, respectively. The 'timestamp' column in both data frames is converted to datetime format using the pd.to_datetime() function. The original 'ttime' columns are then dropped, and the data frames are resampled to a common time interval of 5 minutes using the resample() function. The two data frames are then merged based on the timestamp column using the merge() function, and the resulting data frame is saved to a new CSV file named 'new_data.csv'.

Data Cleaning
In the next part of the script, the 'new_data.csv' file is loaded into a new data frame, df. The 'timestamp' column is converted to Unix timestamp format using the pd.Timestamp() and timestamp() functions, and then dropped from the data frame. Any -99 values in the data frame are replaced with NaN using the replace() function, and rows with NaN values are dropped using the dropna() function. The 'sm_x' column is then set as the dependent variable, 'y', and all other columns are used as independent variables, 'x'. The data set is then split into training and test sets using the train_test_split() function from scikit-learn, with a test size of 25% and a random state of 0.

Feature Scaling
Before fitting the model, the independent variables are standardized using the StandardScaler() function from scikit-learn, which subtracts the mean and scales the variables to unit variance.

Fitting the Model
The final part of the script involves fitting a multiple linear regression model to the training set using the LinearRegression() function from scikit-learn. The fit() method is called on the classifier object with the training data set as the argument. The model is then used to predict the soil moisture levels for the test set using the predict() method, and the root mean squared error (RMSE) between the predicted and actual soil moisture values is calculated using the rmse() function defined earlier. The script then outputs the predicted soil moisture value for the first row of the test set.
