# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

step 1:Start the program and read the number of unknowns and the augmented matrix.

step 2:Convert the matrix into upper triangular form using Gaussian Elimination.

step 3:Find the values of the unknowns using back substitution.

step 4:Display the solution of the given system of equations and stop the program.

## Program:
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by:Gopinath n
RegisterNumber:26007691
'''

import os

os.environ["OPENBLAS_NUM_THREADS"] = "1"

import numpy as np

import sys

n=int(input())

a=np.zeros((n,n+1))

x=np.zeros(n)

for i in range(n):

    for j in range(n+1):
    
        a[i][j]=float(input())

for i inrange(n):

    if a[i][i]==0.0:
    
        sys.exit('Divide by zero detected!')
    
    for j in range(i+1,n):
    
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
        
            a[j][k]=a[j][k]-ratio*a[i][k]

x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):

    x[i]=a[i][n]
    
    for j in range(i+1,n):
    
         x[i]=x[i]-a[i][j]*x[j]
    
    x[i]=x[i]/a[i][i]

for i in range(n):
    
    print('X%d = %0.2f' %(i,x[i]),end=' ')

## Output:
![gaussian elimination]()
<img width="857" height="672" alt="image" src="https://github.com/user-attachments/assets/85eeab8e-85ae-4549-978e-59dfbc7ebc3f" />
<img width="892" height="437" alt="image" src="https://github.com/user-attachments/assets/0a85eb23-574b-4328-bacc-849acbd06af0" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

