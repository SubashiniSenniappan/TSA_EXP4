# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES
# Developed by:SUBASHINI S
# Date: 



### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
# Import necessary libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
df = pd.read_csv('/content/weather_classification_data.csv')  # Adjust path if necessary
data = df['Temperature'].dropna()  # Drop missing values
dataset_length = len(data)
ar1 = np.array([1, -0.5])  # AR(1) coefficient
ma1 = np.array([1, 0.4])   # MA(1) coefficient
ARMA_1_1_process = ArmaProcess(ar1, ma1)
simulated_data_1_1 = ARMA_1_1_process.generate_sample(nsample=dataset_length)
plt.figure()
plt.plot(simulated_data_1_1)
plt.title("Simulated ARMA(1,1) Process")
plt.xlabel("Time")
plt.ylabel("Simulated Value")
plt.xlim([0, 100])
plt.show()
plt.figure()
plot_acf(simulated_data_1_1, lags=20)
plt.title("Autocorrelation of ARMA(1,1)")
plt.show()
plt.figure()
plot_pacf(simulated_data_1_1, lags=20)
plt.title("Partial Autocorrelation of ARMA(1,1)")
plt.show()
ar2 = np.array([1, -0.5, 0.25])  # AR(2) coefficients
ma2 = np.array([1, 0.4, -0.3])   # MA(2) coefficients
ARMA_2_2_process = ArmaProcess(ar2, ma2)
simulated_data_2_2 = ARMA_2_2_process.generate_sample(nsample=dataset_length)
plt.figure()
plt.plot(simulated_data_2_2)
plt.title("Simulated ARMA(2,2) Process")
plt.xlabel("Time")
plt.ylabel("Simulated Value")
plt.xlim([0, 100])
plt.show()
plt.figure()
plot_acf(simulated_data_2_2, lags=20)
plt.title("Autocorrelation of ARMA(2,2)")
plt.show()
plt.figure()
plot_pacf(simulated_data_2_2, lags=20)
plt.title("Partial Autocorrelation of ARMA(2,2)")
plt.show()
```
OUTPUT:
SIMULATED ARMA(1,1) PROCESS:


![Screenshot 2024-09-14 183307](https://github.com/user-attachments/assets/3b55640d-4752-46dd-83ee-d66d9b00bfda)

Partial Autocorrelation
![Screenshot 2024-09-14 203519](https://github.com/user-attachments/assets/ae31eb0f-a052-452e-bdbb-bb490026c30c)

Autocorrelation

![Screenshot 2024-09-14 183345](https://github.com/user-attachments/assets/1cb30c9b-7853-4e5d-8cc4-041b148abe41)


SIMULATED ARMA(2,2) PROCESS:

![Screenshot 2024-09-14 203535](https://github.com/user-attachments/assets/2f63ee51-c4f4-4a2c-9df8-9001a02d7d56)

Partial Autocorrelation

![Screenshot 2024-09-14 203604](https://github.com/user-attachments/assets/a540ae90-69f1-4e91-bc3b-7638fdbf18de)


Autocorrelation

![Screenshot 2024-09-14 203546](https://github.com/user-attachments/assets/d0e41c36-8971-454d-83d0-cf5cea1ab23d)


# RESULT:

Thus, a python program is created to fir ARMA Model successfully.
