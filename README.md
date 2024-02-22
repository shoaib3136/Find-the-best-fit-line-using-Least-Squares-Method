# Implementation of Univariate Linear Regression
## AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula. 
<img width="231" alt="image" src="https://user-images.githubusercontent.com/93026020/192078527-b3b5ee3e-992f-46c4-865b-3b7ce4ac54ad.png">
4. Compute the y -intercept of the line by using the formula:
<img width="148" alt="image" src="https://user-images.githubusercontent.com/93026020/192078545-79d70b90-7e9d-4b85-9f8b-9d7548a4c5a4.png">
5. Use the slope m and the y -intercept to form the equation of the line.
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:
```
/*
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by:Shaik Shoaib Nawaz
RegisterNumber:212222240094 
*/
import numpy as np
import matplotlib.pyplot as plt

# initialization of x,y
x = np.array(eval(input()))
y = np.array(eval(input()))
print(x)
print(y)

# mean
x_mean = np.mean(x)
y_mean = np.mean(y)
print(x_mean)
print(y_mean)

# slope calculation
# b1=(xi-x')(yi-y')/(xi-x')**2
b1 = 0
num = 0
denom = 0
for i in range(len(x)):
    num = num + (x[i] - x_mean) * (y[i] - y_mean)
    denom = denom + ((x[i] - x_mean)**2)

b1 = num / denom
print(b1)

# b0=y'-b1x'
b0 = y_mean - (x_mean * b1)
print(b0)

# line equation
y_pred = b0 + (b1 * x)
print(y_pred)

# graph
plt.scatter(x, y)
plt.plot(x, y_pred, color='orange')
plt.show()
```

## Output:
![best fit line](sam.png)
![image](https://github.com/shoaib3136/Find-the-best-fit-line-using-Least-Squares-Method/assets/117919362/511c5243-5a90-4280-8742-48cdd9f8953c)
![image](https://github.com/shoaib3136/Find-the-best-fit-line-using-Least-Squares-Method/assets/117919362/d2f55c2a-39f5-43a4-a89a-fa2e2b4872e7)

## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
