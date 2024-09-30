# Ex.No: 1 B                    CONVERSION OF NON STATIONARY TO STATIONARY DATA

## AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data

## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
   
## PROGRAM:
### Importing the necessary Packages:
```
PRAGATHEESVARAN A B
212221240039
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

### Loading the dataset:
```
data=pd.read_csv('/content/international-airline-passengers.csv')
```

### Plot the data without Conversion:
```
x=data['Month']
y=data['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
plt.plot(x,y)
```

### REGULAR DIFFERENCING
```
data3=data
data3['diff']=data3['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60'].diff(periods=1)
data3=data3.dropna()
x=data3['Month']
y=data3['diff']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
plt.plot(x,y)
```

### SEASONAL ADJUSTMENT
```
data1=data
data1['SeasonalAdjustment'] = data1['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60'] - data1['International airline passengers: monthly totals in thousands. Jan 49 ? Dec 60'].shift(12)
data1['SeasonalAdjustment'].dropna()
x=data1['Month']
y=data1["SeasonalAdjustment"]
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
plt.plot(x,y)
```

### LOG TRANSFORMATION
```
data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Month']
y=data2['log']
plt.xlabel('Month')
plt.ylabel('International airline passengers: monthly totals in thousands.')
# plt.figure(figsize=(8, 6)) 
plt.plot(x,y)
```

## OUTPUT:
### WITHOUT CONVERSION:
![t1](https://github.com/Ishu-Vasanth/TSA_EXP1B/assets/94154614/c6110233-a143-44fc-8055-73256231bdb1)

### REGULAR DIFFERENCING:
![t2](https://github.com/Ishu-Vasanth/TSA_EXP1B/assets/94154614/f13bc5b1-f547-4a2e-b52e-53bee0ba4166)

### SEASONAL ADJUSTMENT:
![t3](https://github.com/Ishu-Vasanth/TSA_EXP1B/assets/94154614/9e15eef9-4278-486b-9fa6-766b373ecc73)

### LOG TRANSFORMATION:
![t4](https://github.com/Ishu-Vasanth/TSA_EXP1B/assets/94154614/75a84c2a-e8d5-4e98-b88e-26e6da9d5d9d)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
