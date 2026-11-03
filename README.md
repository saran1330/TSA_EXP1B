# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Read the dataset
df = pd.read_csv('temperature.csv')

# Remove empty rows
df = df.dropna(how='all')

# Select annual temperature
data = pd.to_numeric(df['ANNUAL'], errors='coerce').dropna()

# 1. Original Data
plt.figure(figsize=(10, 5))
plt.plot(df.loc[data.index, 'YEAR'], data)
plt.title('Original Annual Temperature')
plt.xlabel('YEAR')
plt.ylabel('TEMPERATURE')
plt.grid()
plt.show()

# 2. Regular Differencing
regular_diff = data.diff()

plt.figure(figsize=(10, 5))
plt.plot(df.loc[data.index, 'YEAR'], regular_diff)
plt.title('Regular Differencing')
plt.xlabel('YEAR')
plt.ylabel('TEMPERATURE DIFFERENCE')
plt.grid()
plt.show()

# 3. Seasonal Adjustment
seasonal_diff = data.diff(12)

plt.figure(figsize=(10, 5))
plt.plot(df.loc[data.index, 'YEAR'], seasonal_diff)
plt.title('Seasonal Differencing')
plt.xlabel('YEAR')
plt.ylabel('SEASONAL DIFFERENCE')
plt.grid()
plt.show()

# 4. Log Transformation
log_data = np.log(data)

plt.figure(figsize=(10, 5))
plt.plot(df.loc[data.index, 'YEAR'], log_data)
plt.title('Log Transformation')
plt.xlabel('YEAR')
plt.ylabel('LOG TEMPERATURE')
plt.grid()
plt.show()

# Display results
print("Regular Differencing:")
print(regular_diff.head())

print("\nSeasonal Adjustment:")
print(seasonal_diff.head())

print("\nLog Transformation:")
print(log_data.head())
```


### OUTPUT:


REGULAR DIFFERENCING:

<img width="1070" height="600" alt="image" src="https://github.com/user-attachments/assets/e446ff7c-bd9b-40af-99c3-4c5931fe1c14" />



SEASONAL ADJUSTMENT:

<img width="1067" height="611" alt="image" src="https://github.com/user-attachments/assets/524f04b9-f5b5-4925-b273-8b09ee5c4902" />



LOG TRANSFORMATION:

<img width="1062" height="587" alt="image" src="https://github.com/user-attachments/assets/b7b57598-70f5-4a77-96d4-22478edf8627" />




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
