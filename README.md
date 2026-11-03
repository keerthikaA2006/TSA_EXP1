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
```

import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv("/content/gld_price_data(1).csv")

df.head()

df['Date'] = pd.to_datetime(df['Date'])

df.dtypes

df.set_index('Date', inplace=True)

df_resampled = df['GLD'].resample('D').interpolate(method='time')

df_resampled.plot(kind='line', label='Gold Price', color='black')

plt.title('Time Series Plot of Gold Prices')
plt.xlabel('Date')
plt.ylabel('Gold Price')
plt.legend()
plt.grid(True)
plt.show()
```

# OUTPUT:
<img width="743" height="580" alt="TS EX1 2" src="https://github.com/user-attachments/assets/e3b29fe3-e778-42ca-a643-aff790fad391" />

# RESULT:
Thus we have created the python code for plotting the time series of given data.
