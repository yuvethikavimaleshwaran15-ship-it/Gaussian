# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start and read the order of the matrix n and the augmented matrix elements.
2. Perform forward elimination to convert the augmented matrix into an upper triangular matrix using Gaussian elimination without partial pivoting.
3. Perform back substitution to calculate the unknown values \(X_1, X_2, \ldots, X_n\)
4. Display the solutions of the variables and stop.
## Program
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Yuvethika V
RegisterNumber: 26016105
'''

import os

os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np

import sys

n=int(input())

a=np.zeros((n,n+1))

x=np.zeros(n)

for i in range(n):

    for j in range(n+1):
    
        a[i][j] = float(input())

for i in range(n):

    if a[i][j] == 0.0:
    
       sys.exit('Divide by zero detected!')

    for j in range(i+1,n):
    
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
        
            a[j][k] = a[j][k]-ratio*a[i][k]

x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):

    x[i] = a[i][n]
   
    for j in range(i+1,n):
    
        x[i] = x[i]-a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]

for i in range(n):

    print('X%d = %0.2f' % (i,x[i]), end=' ')

    

## Output:

<img width="956" height="878" alt="image" src="https://github.com/user-attachments/assets/66f5cf90-07bb-4737-8fd2-3a00133e0398" />
<img width="831" height="577" alt="image" src="https://github.com/user-attachments/assets/18fcd4a7-4310-4f48-9be7-a306c2bda5e9" />




## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

