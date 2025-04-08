# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 08-04-2025

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import matplotlib.pyplot as plt

import numpy as np

data = [3, 16, 156, 47, 246, 176, 233, 140, 130,
101, 166, 201, 200, 116, 118, 247,
209, 52, 153, 232, 128, 27, 192, 168, 208,
187, 228, 86, 30, 151, 18, 254,
76, 112, 67, 244, 179, 150, 89, 49, 83, 147, 90,
33, 6, 158, 80, 35, 186, 127]

lags = range(35)
N = len(data)

#Pre-allocate autocorrelation table
autocorr_values = []
#Mean
mean_data = np.mean(data)
#Variance
variance_data = np.var(data)

#Go through lag components one-by-one

for lag in lags:
  if lag == 0:
    autocorr_values.append(1) # Autocorrelation at lag 0 is 1
  else:
    # Calculate autocovariance for the current lag
    auto_cov = np.sum((data[:-lag] - mean_data) * (data[lag:] - mean_data)) / N
    # Calculate autocorrelation and append to the list
    autocorr_values.append(auto_cov / variance_data)

#display the graph
plt.figure(figsize=(10, 6))
plt.stem(lags, autocorr_values)
plt.title('Autocorrelation of Data')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()

```
### OUTPUT:

![Screenshot 2025-04-08 092829](https://github.com/user-attachments/assets/1d618d6c-bc66-4128-9264-4b1322d9c231)

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
