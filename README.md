# Algorithm for QR Decomposition
# Date : 27.04.2024
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
### Step 1 :
1. import the NumPy library using the statement import numpy as np.
### Step 2 :
2. Define the given matrix A
### Step 3 :
3. Compute the QR Decomposition using np.linalg.inv()
### Step 4 :
4. print and end the program



## Program:
### To find QR Decomposition
```


'''program to find L and U matrix using QR decompostition.
Develeped by : Divya.A
RegisterNumber:2305002007
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]
    for i in range(1,n):
        u[:,1]=A[:,i]
        for j in range(i):
            u[:,i] -= (A[:,i] @ Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)




```

## Output

![image](https://github.com/divyaanbu-143/QRdecomposition/assets/155506447/1a4ae7d4-89c4-4b82-8fcb-887370647dfc)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
