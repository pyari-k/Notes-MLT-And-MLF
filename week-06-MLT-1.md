### Single Value Decomposition (SVD)

SVD is a fundamental matrix factorization technique that decomposes any matrix $A$ into the product of three other matrices:

$A = U\Sigma V^T$

Some sources may also define it as $A = V\Sigma U^T$, but the first form is more standard. Both are mathematically equivalent.

* $U$: An **orthogonal matrix** whose columns are the **left singular vectors**.
* $\Sigma$: A **diagonal matrix** whose non-negative entries on the diagonal are the **singular values**.
* $V^T$: The **transpose of an orthogonal matrix** whose rows are the **right singular vectors**.

***

### What is a Singular Value?

The singular values are the square roots of the eigenvalues of the matrix $A^TA$ (or $AA^T$). This is where the name "singular value" comes from—it's a value associated with the singular (unique) properties of the matrix derived from its eigenvalues.

***

### How to Find U, Σ, and V

Finding the matrices $U$, $\Sigma$, and $V$ involves three main steps:

1.  **Find V**: Compute the matrix $A^TA$. The normalized eigenvectors of $A^TA$ become the columns of the matrix **$V$**.
2.  **Find Σ**: The singular values ($\sigma$) are the square roots of the eigenvalues of $A^TA$. These singular values are arranged in descending order along the diagonal of the matrix **Σ**. This matrix has the same dimensions as the original matrix $A$.
3.  **Find U**: The columns of the matrix **$U$** are the left singular vectors. Each column $u_i$ is calculated using the formula: $u_i = \frac{1}{\sigma_i} Av_i$, where $v_i$ is the corresponding column vector from $V$ and $\sigma_i$ is the singular value from $\Sigma$.

***

### Example

Let's find the SVD of the matrix $A = \begin{bmatrix} 3 & 2 & 2 \\ 2 & 3 & -2 \end{bmatrix}$.

#### Step 1: Find V and Σ

First, we compute $A^TA$:
$A^TA = \begin{bmatrix} 3 & 2 \\ 2 & 3 \\ 2 & -2 \end{bmatrix} \begin{bmatrix} 3 & 2 & 2 \\ 2 & 3 & -2 \end{bmatrix} = \begin{bmatrix} 13 & 12 & 2 \\ 12 & 13 & -2 \\ 2 & -2 & 8 \end{bmatrix}$

Next, we find the eigenvalues and eigenvectors of $A^TA$. The eigenvalues are $\lambda_1 = 25$, $\lambda_2 = 9$, and $\lambda_3 = 0$.

* **Find Σ**: The singular values are the square roots of the non-zero eigenvalues:
    $\sigma_1 = \sqrt{25} = 5$ and $\sigma_2 = \sqrt{9} = 3$.
    The $\Sigma$ matrix is constructed with these values on the diagonal and is the same size as $A$:
    $\Sigma = \begin{bmatrix} 5 & 0 & 0 \\ 0 & 3 & 0 \end{bmatrix}$

* **Find V**: The normalized eigenvectors corresponding to the eigenvalues are:
    * For $\lambda_1 = 25$: $v_1 = \begin{bmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \\ 0 \end{bmatrix}$
    * For $\lambda_2 = 9$: $v_2 = \begin{bmatrix} 1/\sqrt{18} \\ -1/\sqrt{18} \\ 4/\sqrt{18} \end{bmatrix}$
    * For $\lambda_3 = 0$: $v_3 = \begin{bmatrix} 2/3 \\ -2/3 \\ -1/3 \end{bmatrix}$
    The matrix $V$ is formed by these eigenvectors as its columns:
    $V = \begin{bmatrix} 1/\sqrt{2} & 1/\sqrt{18} & 2/3 \\ 1/\sqrt{2} & -1/\sqrt{18} & -2/3 \\ 0 & 4/\sqrt{18} & -1/3 \end{bmatrix}$

#### Step 2: Find U

We use the formula $u_i = \frac{1}{\sigma_i} Av_i$ to find the columns of $U$.
* $u_1 = \frac{1}{5} A v_1 = \frac{1}{5} \begin{bmatrix} 3 & 2 & 2 \\ 2 & 3 & -2 \end{bmatrix} \begin{bmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \\ 0 \end{bmatrix} = \begin{bmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \end{bmatrix}$
* $u_2 = \frac{1}{3} A v_2 = \frac{1}{3} \begin{bmatrix} 3 & 2 & 2 \\ 2 & 3 & -2 \end{bmatrix} \begin{bmatrix} 1/\sqrt{18} \\ -1/\sqrt{18} \\ 4/\sqrt{18} \end{bmatrix} = \begin{bmatrix} 1/\sqrt{2} \\ -1/\sqrt{2} \end{bmatrix}$

The matrix $U$ is formed by these vectors as its columns:
$U = \begin{bmatrix} 1/\sqrt{2} & 1/\sqrt{2} \\ 1/\sqrt{2} & -1/\sqrt{2} \end{bmatrix}$

#### Final SVD Format

The complete SVD for the matrix $A$ is:

$A = U\Sigma V^T$

$\begin{bmatrix} 3 & 2 & 2 \\ 2 & 3 & -2 \end{bmatrix} = \begin{bmatrix} 1/\sqrt{2} & 1/\sqrt{2} \\ 1/\sqrt{2} & -1/\sqrt{2} \end{bmatrix} \begin{bmatrix} 5 & 0 & 0 \\ 0 & 3 & 0 \end{bmatrix} \begin{bmatrix} 1/\sqrt{2} & 1/\sqrt{2} & 0 \\ 1/\sqrt{18} & -1/\sqrt{18} & 4/\sqrt{18} \\ 2/3 & -2/3 & -1/3 \end{bmatrix}$

***

### Tips for Exams ✍️

To identify the correct SVD decomposition from a given set of matrices, remember these key properties:

1.  **Check the diagonal of Σ**: The non-zero diagonal elements of the $\Sigma$ matrix must be the **square roots of the non-zero eigenvalues of $A^TA$**. You can quickly verify this by calculating the eigenvalues of $A^TA$ and comparing them to the squares of the values on the diagonal of $\Sigma$.
2.  **Check for orthonormality**: The columns of both $U$ and $V$ must be **orthonormal**. This means that each column vector has a length of 1 (is a unit vector), and the dot product of any two different column vectors within the same matrix is 0.
3.  **Verify the relationship**: A final, and very reliable, check is to confirm the relationship $u_i = \frac{1}{\sigma_i} Av_i$ for each column pair. This is the definition of the left singular vectors and a crucial part of the decomposition.