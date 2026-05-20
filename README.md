# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input matrix dimensions and initialize augmented matrix and solution vector.
2.Populate the augmented matrix with user inputs.
3.Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.
4.Back substitute to compute solution values for the variables.
5.Print the solution vector formatted to two decimal places.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: MOHAMED AATHIL M 
RegisterNumber: 212225040246
*/
```
```

import os 
os.environ["OPENBLAS_NUM_THREADS"] = "1"

import numpy as np

# Number of unknowns
n = int(input())

# Augmented matrix input
A = np.zeros((n, n + 1))

for i in range(n):
    for j in range(n + 1):
        A[i][j] = float(input())

# Gaussian Elimination without Partial Pivoting
for i in range(n):

    for j in range(i + 1, n):
        ratio = A[j][i] / A[i][i]

        for k in range(n + 1):
            A[j][k] = A[j][k] - ratio * A[i][k]

# Back Substitution
X = np.zeros(n)

X[n - 1] = A[n - 1][n] / A[n - 1][n - 1]

for i in range(n - 2, -1, -1):
    sum_val = 0

    for j in range(i + 1, n):
        sum_val += A[i][j] * X[j]

    X[i] = (A[i][n] - sum_val) / A[i][i]

# Output
for i in range(n):
    print(f"X{i} = {X[i]:.2f}", end=" ")

*/
```
## Output:
![gaussian elimination]()
<img width="783" height="409" alt="594560853-fa95a4c1-7c0c-413f-b120-bcc1ce079e89" src="https://github.com/user-attachments/assets/f23c918f-3d4f-4bae-ba23-c94ae8561230" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

