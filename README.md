# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook


## Algorithm
1.Import pandas, numpy and mathplotlib.pyplot


2.Trace the best fit line and calculate the cost function


3.Calculate the gradient descent and plot the graph for it


4.Predict the profit for two population sizes.

## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: DIVAKAR R
RegisterNumber: 212222240026

import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data=pd.read_csv("/ex1.txt",header=None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")

def computeCost(X,y,theta):
  """
  Take in a numpy array X, y , theta and generate the cost fuction in a linear regression model
  """
  m=len(y)
  h=X.dot(theta)  # length of training data
  square_err=(h-y)**2 

  return 1/(2*m) * np.sum(square_err)  
  
  data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))

computeCost(X,y,theta)   # function call

def gradientDescent(X,y,theta,alpha,num_iters):
  
  m=len(y)
  J_history=[]

  for i in range(num_iters):
    predictions=X.dot(theta)
    error=np.dot(X.transpose(),(predictions - y))
    descent=alpha * 1/m * error
    theta-=descent
    J_history.append(computeCost(X,y,theta))

  return theta, J_history
  
theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1")

plt.plot(J_history)
plt.xlabel("Iternations")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")

plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Polpulation of City (10,000s)")
plt.ylabel("Profit (10,000s)")
plt.title("Profit Prediction")

def predict(x,theta):
  predictions= np.dot(theta.transpose(),x)
  return predictions[0]
  
 predict1=predict(np.array([1,3.5]),theta)*10000
print("For population = 35,000, we predict a profit of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*10000
print("For population = 70,000, we predict a profit of $"+str(round(predict2,0)))
*/
```

## Output:
PROFIT PREDICTION:
![ML-301](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/aadbf8a2-87a7-4450-8da6-8352755c7dd5)



COST FUNCTION:

![ML-302](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/4b5d7a4e-3331-4e8d-be8d-5dbde14a4728)


GRADIENT DESCENT:



![ML-303](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/dcfd8c3e-44b9-4f49-ba4f-f3f93ddd526e)



COST FUNCTION USING GRADIENT DESCENT:



![ML-304](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/6df17683-1004-499c-940a-230fbd934204)


GRAPH WITH BEST FIT LINE (PROFIT PREDICTION):


![ML-305](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/c9e3b0a2-bac6-4441-9651-2a0731ced41f)


PROFIT PREDICTION FOR A POPULATION OF 35,000:

![ML-306](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/60b71ec9-6a9c-4098-8f10-01ec1b96e156)



PROFIT PREDICTION FOR A POPULATION OF 70,000:


![ML-307](https://github.com/divakar618/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/121932143/de2717bb-034c-45e5-bb2e-65e2221595b2)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
