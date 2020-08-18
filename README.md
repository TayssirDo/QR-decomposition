# QR_decomposition
We can compute the QR decomposition by Householder transformations, Givens transformations or by Gram Schmidt orthogonalization.
Here, we compute Householder QR.

**Theorem:**

If <img src="https://render.githubusercontent.com/render/math?math=A \in \mathbb{R}^{m \times n}"> has full column rank, i.e, Rank(<img src="https://render.githubusercontent.com/render/math?math=A">)=<img src="https://render.githubusercontent.com/render/math?math=n"> then <img src="https://render.githubusercontent.com/render/math?math=A"> has the QR decomposition:

<img src="https://render.githubusercontent.com/render/math?math=A = Q \begin{bmatrix}R \\0 \end{bmatrix} = Q_1 R">

where <img src="https://render.githubusercontent.com/render/math?math=Q=[Q_1, Q_2] \in \mathbb{R}^{m \times m}"> is orthogonal and <img src="https://render.githubusercontent.com/render/math?math=R \in \mathbb{R}^{n \times n}"> is nonsingular upper triangular.

## Example
```python
np.random.seed(20)
A = np.random.randn(5, 3)
print('----- Matrix A: -----\n'+ str(A)+'\n')

#compute the QR decomposition
Q, R = qr_householder(A)

print('\033[1;31;31m Compute A=QR: \033[1;m \n'+ str(Q @ R))
print(np.allclose(A, Q @ R))
```

## Notes
1. G.H. Golub and C.F. Van Loan. Matrix Computations. The Johns Hopkins University Press, Baltimore, Maryland, 4th edition, 2013.
