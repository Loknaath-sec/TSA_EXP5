# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11/25/2026
### Name: Loknaath P
### Reg No: 212223240080

## AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

## PROGRAM:
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/drive/MyDrive/COLAB PROJECTS/Time Series/nasa_exoplanet_intelligence.csv',parse_dates=['disc_year'],index_col='disc_year')

data = data.sort_values('disc_year')

X = data['n_planets']

decomposition = seasonal_decompose(data['n_planets'], model='additive',period=12)

# Adjust the figure size for a square shape
# decomposition.plot() this plots all four of teh following graphs
# Original Data
plt.subplot(411)
plt.plot(data['n_planets'], label='Number of Planets')
plt.legend(loc='upper left')
plt.title('Number of Planets')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```

## OUTPUT:
ORIGINAL TIME SERIES DATA:
<img width="1493" height="285" alt="image" src="https://github.com/user-attachments/assets/7d94b276-7c98-484e-aa8a-e1282a5fc5e0" />


LINEAR TREND PLOT:
<img width="1489" height="278" alt="image" src="https://github.com/user-attachments/assets/fba2eb7f-a394-4d6a-bbf9-2a323506f044" />


SEASONALITY PLOT:
<img width="1489" height="272" alt="image" src="https://github.com/user-attachments/assets/59b6c73e-c485-496d-b662-c1a94a45433f" />


RESIDUAL PLOT:
<img width="1481" height="275" alt="image" src="https://github.com/user-attachments/assets/4056266c-0150-4f0b-b6c6-71e41ffa14eb" />



## RESULT:
Thus we have created the python code for the time series analysis and decomposition.
