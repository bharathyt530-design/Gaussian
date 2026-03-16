# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Start the program and read the number of equations (n) and the augmented matrix [A∣B]. 
2.Convert the matrix to upper triangular form
For each row i, eliminate the elements below the pivot by performing row operations. 
3.Apply back substitution
Start from the last equation and substitute the values upward to find each variable. 
4.Display the solution of the variables and stop the program. 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:BHARATH V 
RegisterNumber:212225220017
*/
import sys
n=int(input())
A=[[0]*(n+1) for _ in range(n)]
X=[0]*n
for i in range(n):
    for j in range(n+1):
        A[i][j]=float(input())
for i in range(n):
    if A[i][i]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        r=A[j][i]/A[i][i]
        for k in range(n+1):
            A[j][k]-=r*A[i][k]
X[n-1]=A[n-1][n]/A[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i]=A[i][n]
    for j in range(i+1,n):
        X[i]-=A[i][j]*X[j]
    X[i]/=A[i][i]
for i in range(n):
    print('X%d = %.2f'%(i,X[i]),end=" ")
```

## Output:



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

