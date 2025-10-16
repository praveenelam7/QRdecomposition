# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```

import numpy as np
#write your code 
def g(a):
    a=np.array(a,dtype=float)
    m,n=a.shape
    q=np.zeros((m,n))
    r=np.zeros((n,n))
    for j in range (n):
        v=a[:,j]
        for i in range (j):
            r[i,j]=np.dot(q[:,i],a[:,j])
            v=v-r[i,j]*q[:,i]
        r[j,j]=np.linalg.norm(v)
        q[:,j]=v/r[j,j]
    return q,r
a=np.array(eval(input()))
q,r=g(a)
print("The Q Matrix is\n",q)
print("The R Matrix is\n",r)
    






```

## Output
```

```
<img width="850" height="492" alt="{DD946B74-198B-489D-A95D-FD99AE79914F}" src="https://github.com/user-attachments/assets/4e3e63d9-ca85-47a9-8948-629606e46f12" />
<img width="427" height="469" alt="{93F54B3C-F95E-43B3-BCA8-7B92C06CBFA7}" src="https://github.com/user-attachments/assets/5d9bb850-67da-4f1d-8408-15f41a9c9e0a" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
