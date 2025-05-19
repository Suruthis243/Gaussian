# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1: Input

Start the program.

Input the number of unknowns n.

Create an augmented matrix A of size n x (n+1) to store the coefficients and constants of the equations.

### Step 2: Read the Augmented Matrix

Use nested loops to input all the elements of the augmented matrix from the user.

### Step 3: Forward Elimination (Convert to Upper Triangular Matrix)

For each pivot row i from 0 to n-1:

For each row j below row i (i.e., j = i+1 to n-1):

Calculate the ratio = A[j][i] / A[i][i]

For each column k from 0 to n:

Update A[j][k] = A[j][k] - ratio * A[i][k]

This eliminates the elements below the pivot and converts the matrix to upper triangular form.

### Step 4: Back Substitution

Initialize a solution array x of size n with zeros.

Solve for the last variable:
x[n-1] = A[n-1][n] / A[n-1][n-1]

For each row i from n-2 down to 0:

Set x[i] = A[i][n]

For each column j from i+1 to n-1:

Subtract A[i][j] * x[j] from x[i]

Divide x[i] by A[i][i]

### Step 5: Output the Result

Print the solution array x, displaying each unknown variable with its value.

### Step 6: End

The program terminates after displaying the solution.


Create an augmented matrix A of size n x (n+1) to store the coefficients and constants of the equations.
## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:SURUTHI S 
RegisterNumber:212224220114 
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())

for i in range(n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]

x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=" ")
```

## Output:
![Screenshot 2025-04-29 212208](https://github.com/user-attachments/assets/48fd6e8c-d238-4214-a7bb-14955471eeca)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

