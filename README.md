# Changes made to CS229 Solar Power Prediction Project

1. The makers of the original project had not considered the data in sequential order. They had further randomzied the data by spliting it randomly.I wanted to build the LSTM model on sequential data instead of random data. I was unable to find the original dataset that was used to split into weather_train, weather_test and weather_dev so I merged these three files into one file called merged_weather in Python and sorted it by year, month, date and hour. Then I spilt it by the ratio 80% 10% 10% while mainting the sequence of the data. This step is essential because LSTM models are designed to capture temporal dependencies in sequential data. By maintaining the sequence, the model can learn patterns and relationships over time, which is essential for accurate predictions in time series forecasting.

2. The makers had normalised the dataset before training the model. The assists LSTM to read underlying patterns easily. But they had not denormalized the output data to give actual values of output. I created a function to denormalize the data using original data_min and data_max values of the training set, hence revealing true output values.
   
3. To keep a track of all the MSE values, I introduced CSVLogger to download the loss values as a CSV.
   
4. I plotted graphs to compare the actual and predicted values of all three datasets.
