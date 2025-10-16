# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Start the program.

2.Import the required library numpy as np.

3.Create the coefficient matrix A and the constant vector b.

4.Use np.linalg.solve(A, b) to find the solution vector x.

5.Display the solution.

6.Stop the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Kanigavel M 
RegisterNumber: 212224240070
*/

import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')


```
<img width="1309" height="950" alt="image" src="https://github.com/user-attachments/assets/593fe010-389b-4a2f-bd82-cd49d4ff8f55" />

## Output:
<img width="1232" height="595" alt="image" src="https://github.com/user-attachments/assets/3b856f92-834d-45ef-ae06-0b28668620da" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

