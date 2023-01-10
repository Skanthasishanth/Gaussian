# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1 : 
Import the numpy module to use the built-in functions for calculation.

### Step 2 :
Get input from the user for number of rows and add it by 1 for number of columns.

### Step 3 : 
Using np.zeros() set the matrix as null matrix.

### Step 4 : 
Using nested for loop get input from the user for each element in the matrix.

### Step 5 :
Using nested for loop find the ratio and perform the elementary row operations and find the final matrix.

### Step 6 : 
Use back substitution method to find the value of the variables and print it.

### Step 7 : 
End the program.

## Program:
```
#Program to find the solution of a matrix using Gaussian Elimination.
#Developed by: S Kantha Sishanth
#RegisterNumber: 22007660
import numpy as np
n=int(input())
arr=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        arr[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=arr[j][i]/arr[i][i]
        for k in range(n+1):
            arr[j][k]=arr[j][k]-ratio*arr[i][k]
x[n-1]=arr[n-1][n]/arr[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=arr[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-arr[i][j]*x[j]
    x[i]=x[i]/arr[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")   #X0 = 53.35 X1 = -8.88 X2 = -4.40

```

## Output:
!['output](/Gaussian.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

