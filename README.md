# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 

 AIM:
 
To Compute the AutoCorrelation Function (ACF) of the covid data for the first 35 lags to determine the model
type to fit the data.

 ALGORITHM:
 
1. Import the necessary packages
   
2. Find the mean, variance and then implement normalization for the data.
 
3. Implement the correlation using necessary logic and obtain the results
 
4. Store the results in an array
 
5. Represent the result in graphical representation as given below.
    
 PROGRAM:
```
import pandas as pd
from statsmodels.graphics.tsaplots import plot_acf
import matplotlib.pyplot as plt

# Load the dataset (adjust the file path as needed)
file_path = '/mnt/data/Covid Data - Asia.csv'
data = pd.read_csv(file_path)

# Extract the 'Total Cases' for all countries and convert it to a numeric type
# Removing commas from the data for proper numeric conversion
total_cases_all_countries = pd.to_numeric(data['Total Cases'].str.replace(',', ''), errors='coerce')

# Plot the ACF for the first 35 lags using the total cases of all countries
plt.figure(figsize=(10, 6))
plot_acf(total_cases_all_countries.dropna(), lags=35)
plt.title('ACF for Total Cases of All Countries (First 35 Lags)')
plt.show()
```
### OUTPUT:

![Screenshot (634)](https://github.com/user-attachments/assets/771cf4bc-651b-416f-9035-ee5a4722833b)

### RESULT:
        Thus we have successfully implemented the auto correlation function in covid dataset.
