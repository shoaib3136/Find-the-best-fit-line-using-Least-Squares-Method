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
x=[2,9,5,5,3,7,1,8,6,2]
y=[69,98,82,77,71,84,55,94,84,64]
diff_x=[0,0,0,0,0,0,0,0,0,0]
diff_y=[0,0,0,0,0,0,0,0,0,0]
total_data=10
xsum=0
ysum=0
for i in range(0,len(x)):
  xsum=x[i]+xsum
  ysum=y[i]+ysum

print(xsum)
print(ysum)

xmean=xsum/total_data
ymean=ysum/total_data

print(xmean)
print(ymean)

for i in range(0,len(x)):
  diff_x[i]=x[i]-xmean
  diff_y[i]=y[i]-ymean

print(diff_x)
print(diff_y)

mul_diff=0
sq_diff_x=0

for i in range(0,len(x)):
  mul_diff=(diff_x[i]*diff_y[i])+mul_diff
  sq_diff_x=(diff_x[i]*diff_x[i])+sq_diff_x

print(mul_diff)
print(sq_diff_x)

b1=mul_diff/sq_diff_x
print(b1)
b0=ymean-(b1*xmean)
print(b0)

print("y=",b0,"+",b1,"x")

import matplotlib.pyplot as plt
import numpy as np
plt.scatter(x,y)
yfit = [b0 + b1* xi for xi in x]
plt.plot(x, yfit)
plt.show()
```

## Output:
![best fit line](sam.png)
![image](https://github.com/shoaib3136/Find-the-best-fit-line-using-Least-Squares-Method/assets/117919362/50eac31d-aae8-4313-96b7-f7de247f78a6)
![image](https://github.com/shoaib3136/Find-the-best-fit-line-using-Least-Squares-Method/assets/117919362/8f955059-e8e6-4473-b044-2e2222cea05c)



## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
