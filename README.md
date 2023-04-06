# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook
```
## Algorithm
1. Get the independent variable X and dependent variable Y.
2.Calculate the mean of the X -values and the mean of the Y -values.
3.Find the slope m of the line of best fit using the formula.
4. Compute the y -intercept of the line by using the formula
5. Use the slope m and the y -intercept to form the equation of the line. 
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.
```
## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: divakar R
RegisterNumber:  212222240026
*/
```
```
import numpy as np
import matplotlib.pyplot as plt
X=np.array(eval(input("x: ")))
Y=np.array(eval(input("y: ")))
X_mean=np.mean(X)
Y_mean=np.mean(Y)
num=0
denum=0
for i in range(len(X)):
  num+=(X[i]-X_mean)*(Y[i]-Y_mean)
  denum+=(X[i]-X_mean)**2

#calculate slope
m=num/denum
print("Slope")
print(m)
#calculate intercept
b=Y_mean - m*X_mean
print("Y-intercept")
print(b)
# line equation
Y_pred=m*X+b
# condtion if x=number 
Y_expect=m*3+b
print(Y_pred)
print(Y_expect)

# to plot graph
plt.scatter(X,Y,color='blue')
plt.plot(X,Y_pred,color='red') 
plt.show() 
```

## Output:
Text(0.5, 1.0, 'Profit Prediction')
![image](https://user-images.githubusercontent.com/121932143/230440368-4654142d-1358-4c93-9fb4-01c6f3750139.png)

Text(0.5, 1.0, 'Cost function using Gradient Descent')

![image](https://user-images.githubusercontent.com/121932143/230440764-6b025f30-f75d-41f3-b85d-ef2989c95de6.png)


## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
