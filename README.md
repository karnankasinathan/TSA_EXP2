### Developed by:Karnan K
### Reg no:212222230062
### Date:
# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
1. Import necessary libraries 
2. Load the dataset
3. Convert dates to a numeric format for analysis.
4. Perform linear regression to find the line of best fit.
5. Fit a polynomial (degree 2) to the data.
6. Create a plot showing the original data and the linear trend line and the ploynomial trend line.
7. Show the plot with labels and a title.

End the program
### PROGRAM:
A - LINEAR TREND ESTIMATION
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import linregress
df = pd.read_csv('/content/baggagecomplaints.csv')
df['Date'] = pd.to_datetime(df['Date'])
df.set_index('Date', inplace=True)
X = np.array(range(len(df)))
Y = df['Baggage']
slope, intercept, r, p, std_err = linregress(X, Y)
linear_trend = slope * X + intercept
plt.figure(figsize=(10,6))
plt.plot(df['Baggage'], label='Original')
plt.plot(linear_trend, label='Linear Trend')
plt.legend(loc='best')
plt.title('Linear Trend Estimation')
plt.show()
```
B- POLYNOMIAL TREND ESTIMATION
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import linregress
df = pd.read_csv('/content/baggagecomplaints.csv')
df['Date'] = pd.to_datetime(df['Date'])
df.set_index('Date', inplace=True)
coeffs = np.polyfit(X, Y, 2)
poly_trend = np.polyval(coeffs, X)
plt.figure(figsize=(10,6))
plt.plot(df['Baggage'], label='Original')
plt.plot(poly_trend, label='Polynomial Trend (degree 2)')
plt.legend(loc='best')
plt.title('Polynomial Trend Estimation')
plt.show()
```
### OUTPUT
A - LINEAR TREND ESTIMATION

![Screenshot 2024-08-25 011610](https://github.com/user-attachments/assets/c668e9c4-e60d-4d12-a7d0-5072a1d4616d)

B- POLYNOMIAL TREND ESTIMATION

![Screenshot 2024-08-25 011623](https://github.com/user-attachments/assets/5e4bc7b9-0224-47ac-9e36-285242a07c64)

### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
