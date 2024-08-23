### Name : Naveen Kumar S
### Reg.No : 212221240033
### Date : 23/08/2024

# Ex.No: 01A PLOT A TIME SERIES DATA

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
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

# Load the data from the CSV file
data = pd.read_csv('G:/sem7/TSA/migrations.csv')

# Count the occurrences of each technology in the "to" column per year
trend_data = data.groupby(['year', 'to']).size().unstack().fillna(0)

# Plotting the trends over time for each technology
plt.figure(figsize=(14, 8))
sns.lineplot(data=trend_data)
plt.title('Technology Migration Trends Over the Years')
plt.xlabel('Year')
plt.ylabel('Number of Migrations')
plt.legend(title='Technologies', bbox_to_anchor=(1, 1), loc='upper left')
plt.grid(True)
plt.show()
```

# OUTPUT:
![image](https://github.com/user-attachments/assets/f0c6e6d7-5172-4108-823e-039fdfde7a3b)

# Reult:
Hence the TimeSeries data forecasting plotted succesfully to help the decision-makers in understanding current technology trends, informing strategic decisions about adopting or phasing out specific technologies based on industry movements.



