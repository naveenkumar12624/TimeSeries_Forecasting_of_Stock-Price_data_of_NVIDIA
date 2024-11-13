### Name : Naveen Kumar S
### Reg.No : 212221240033
### Date : 

# Ex.No: 01A PLOT A TIME SERIES DATA

# AIM:
To Develop a python program to Plot a time series data of NVIDIA's Stock Price.
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
   
# PROGRAM:
```py
import pandas as pd
import matplotlib.pyplot as plt
from pandas.plotting import register_matplotlib_converters
import seaborn as sns

# Register matplotlib converters (optional for some environments)
register_matplotlib_converters()

# Load the NVIDIA dataset
data = pd.read_csv('C:/Users/lenovo/Downloads/archive (2)/NVIDIA/NvidiaStockPrice.csv')

# Convert 'Date' column to datetime format and set it as the index
data['Date'] = pd.to_datetime(data['Date'])
data.set_index('Date', inplace=True)

# Resample data to yearly frequency and take mean of 'Close' prices
yearly_data = data['Close'].resample('Y').mean().reset_index(name='Close')

# Prepare data for plotting
trend_data = yearly_data.pivot_table(index='Date', values='Close')

# Plotting the trends over time for the 'Close' price
plt.figure(figsize=(14, 8))
sns.lineplot(data=yearly_data, x='Date', y='Close')
plt.title('NVIDIA Stock Price Trends Over the Years')
plt.xlabel('Year')
plt.ylabel('Average Close Price')
plt.grid(True)
plt.show()
```

# OUTPUT:
<img src="https://github.com/user-attachments/assets/f68da2ef-b4c4-443d-91ba-593e255c2c22" width=600/>


# Reult:
Hence the TimeSeries data forecasting plotted succesfully to help the decision-makers in understanding current stock trends of NVIDIA, informing strategic decisions about adopting or phasing out specific investments based on industry movements.



