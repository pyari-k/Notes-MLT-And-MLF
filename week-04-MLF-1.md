## Characteristic Equation

The **characteristic equation**, represented as $|A - \lambda I| = 0$, is a polynomial equation used to find the **eigenvalues** ($\lambda$) of a square matrix $A$, which in turn reveal essential properties of the linear transformation defined by the matrix.


# Eigenvalues – Quick Note

## What are Eigenvalues?

Given a square matrix **A**, a scalar **λ** is an eigenvalue of **A** if there exists a non-zero vector **v** such that:

$$
A \mathbf{v} = \lambda \mathbf{v}
$$

- **λ** is the eigenvalue  
- **v** is the corresponding eigenvector

---

## Special Case: Triangular and Diagonal Matrices

For the following types of matrices:

- **Diagonal matrix**  
- **Upper triangular matrix**  
- **Lower triangular matrix**

✅ The eigenvalues are simply the **diagonal elements** of the matrix.

---

### Why?

The eigenvalues of a matrix **A** are found by solving:

$$
\det(A - \lambda I) = 0
$$

For triangular or diagonal matrices, the determinant simplifies easily because the matrix remains triangular.

### Example: Upper Triangular Matrix

Let:

$$
A = \begin{bmatrix}
3 & 2 & 1 \\
0 & 5 & 4 \\
0 & 0 & 7
\end{bmatrix}
$$

Then:

$$
\det(A - \lambda I) = 
\det\begin{bmatrix}
3 - \lambda & 2 & 1 \\
0 & 5 - \lambda & 4 \\
0 & 0 & 7 - \lambda
\end{bmatrix}
= (3 - \lambda)(5 - \lambda)(7 - \lambda)
$$

So the eigenvalues are:

$$
\lambda_1 = 3,\quad \lambda_2 = 5,\quad \lambda_3 = 7
$$

---

## Summary

- For **diagonal**, **upper triangular**, and **lower triangular** matrices:  
  🔸 **Eigenvalues = Diagonal elements**

This makes such matrices particularly easy to analyze in linear algebra.

- For **any square matrix**:  
  🔸 **Trace = Sum of eigenvalues**  
  🔸 **Determinant = Product of eigenvalues**


  # Orthogonal Matrices and Diagonalization

## Orthogonal Matrices

A square matrix **Q** is called **orthogonal** if its transpose is equal to its inverse:

$$
Q^\top = Q^{-1}
$$

Equivalently:

$$
Q Q^\top = Q^\top Q = I
$$

🔹 This means the columns (and rows) of **Q** are **orthonormal vectors** — i.e., they are:
- **Unit vectors** (length = 1)
- **Mutually perpendicular**

---

## Orthogonal Diagonalization

A matrix **A** is **orthogonally diagonalizable** if there exists an orthogonal matrix **Q** such that:

$$
Q^\top A Q = D
$$

Where:
- **D** is a diagonal matrix
- The columns of **Q** are the **orthonormal eigenvectors** of **A**

---

## Real Symmetric Matrices

A matrix **A** is **real symmetric** if:

$$
A^\top = A \quad \text{and all entries are real}
$$

✅ **Important Theorem:**

> Every real symmetric matrix is **orthogonally diagonalizable**.

That is, for any real symmetric matrix **A**, there exists an orthogonal matrix **Q** such that:

$$
Q^\top A Q = D
$$

Where **D** contains the real eigenvalues of **A**.

---

## Summary

- A matrix **Q** is **orthogonal** if:  
  🔸 $Q^\top = Q^{-1}$  
  🔸 $Q Q^\top = I$

- A real symmetric matrix **A** satisfies:  
  🔸 $A^\top = A$  
  🔸 It is always **orthogonally diagonalizable**  
  🔸 Eigenvalues are real  
  🔸 Eigenvectors can be chosen to be orthonormal


# Spectral Theorem (Real Symmetric Matrices)

## Statement

> **The Spectral Theorem** for real matrices states:

If $A \in \mathbb{R}^{n \times n}$ is a **real symmetric matrix**, then:

- All eigenvalues of \( A \) are **real**.
- There exists an **orthogonal matrix** \( Q \in \mathbb{R}^{n \times n} \) and a **diagonal matrix** \( D \in \mathbb{R}^{n \times n} \) such that:

$$
A = Q D Q^\top
$$

---

## Meaning

- $Q^\top = Q^{-1}$ ⇒ $Q$ is an **orthogonal matrix**.
- The columns of \( Q \) are **orthonormal eigenvectors** of \( A \).
- The diagonal entries of \( D \) are the **real eigenvalues** of \( A \).

---

## Key Points

- ✅ **Real symmetric matrices are always orthogonally diagonalizable.**
- ✅ Their eigenvectors can be chosen to be **orthonormal**.
- ✅ This makes them particularly easy to work with in applications like:
  - Principal Component Analysis (PCA)
  - Quantum mechanics
  - Vibration analysis
  - Numerical linear algebra

---

## Example

Let:

$$
A = \begin{bmatrix}
4 & 1 \\
1 & 3
\end{bmatrix}
$$

This is a real symmetric matrix.  
It has:

- Real eigenvalues
- An orthonormal basis of eigenvectors
- An orthogonal matrix \( Q \) such that:

$$
A = Q D Q^\top
$$

---
