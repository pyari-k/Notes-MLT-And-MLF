## Four Fundamental Subspaces

### 1. What is the Column Space?

The **column space** of a matrix $A$ is the set of all possible linear combinations of its column vectors.

Formally, for an $m \times n$ matrix $A$, its column space, denoted as $Col(A)$, is a subspace of $\mathbb{R}^m$. It represents all the vectors $\vec{b}$ for which the matrix equation $A\vec{x} = \vec{b}$ has a solution.

In simpler terms, the column space is the span of the column vectors of the matrix.

### Example

Consider the matrix $A$:
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{bmatrix}$$

The column vectors are:
$$\vec{c}_1 = \begin{bmatrix} 1 \\ 4 \end{bmatrix}, \quad \vec{c}_2 = \begin{bmatrix} 2 \\ 5 \end{bmatrix}, \quad \vec{c}_3 = \begin{bmatrix} 3 \\ 6 \end{bmatrix}$$

The column space of $A$ is the set of all vectors that can be written as:
$$c_1\begin{bmatrix} 1 \\ 4 \end{bmatrix} + c_2\begin{bmatrix} 2 \\ 5 \end{bmatrix} + c_3\begin{bmatrix} 3 \\ 6 \end{bmatrix}$$
for any real numbers $c_1, c_2, c_3$.

---

### 2. What is the Null Space?

The **null space** of a matrix $A$ is the set of all vectors $\vec{x}$ that satisfy the homogeneous equation $A\vec{x} = \vec{0}$.

Formally, for an $m \times n$ matrix $A$, the null space (or kernel), denoted $Nul(A)$, is a subspace of $\mathbb{R}^n$. It consists of all vectors that are "sent to zero" by the linear transformation defined by $A$.

The null space always contains the zero vector, as $A\vec{0} = \vec{0}$ for any matrix.

### Example

Consider the matrix $A$:
$$ A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \end{bmatrix} $$

To find the null space, we solve the homogeneous system $A\vec{x} = \vec{0}$ by row-reducing the augmented matrix or using Gaussian Elimination:
$$ \begin{bmatrix} 1 & 2 & 3 & 0 \\ 2 & 4 & 6 & 0 \end{bmatrix} \sim \begin{bmatrix} 1 & 2 & 3 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix} $$
This gives the single equation $x_1 + 2x_2 + 3x_3 = 0$.
Here, $x_2$ and $x_3$ are free variables. We express $x_1$ in terms of the free variables:
$$ x_1 = -2x_2 - 3x_3 $$
We can now write the solution vector $\vec{x}$ in parametric form:
$$ \vec{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} -2x_2 - 3x_3 \\ x_2 \\ x_3 \end{bmatrix} = x_2 \begin{bmatrix} -2 \\ 1 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} -3 \\ 0 \\ 1 \end{bmatrix} $$
The vectors $\begin{bmatrix} -2 \\ 1 \\ 0 \end{bmatrix}$ and $\begin{bmatrix} -3 \\ 0 \\ 1 \end{bmatrix}$ form a basis for the null space. The null space of matrix $A$ is the span of these two vectors, which is a plane in $\mathbb{R}^3$.

---

### 3. Rank of a matrix 
Rank stands the number of independent rows or columns in a matrix 
To find it, row-reduce the matrix using Gaussian elimination to a row echelon form. 
Recall: To be in a row echelon form, 

(a) staircase shape - leading elements. For a row below another, the leading element should be to the right of the one above it. 

(b) all rows with only zeros are in the bottom of the matrix 

(c) the leading entry or pivot (first non zero element) is always one. 

Rank = number of non-zero rows in the row-echelon form 

---

### 4. Nullity of a matrix 
Nullity is the dimension of the null space of a matrix 
Rank Nullity theorem : Rank + Nullity = n 
To find the nullity, find Rank and subtract it from n 

**Question:**
What is the nullity of the following matrix?
$$A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \end{bmatrix}$$

---

**Answer:**

**Step 1: Find the Rank of the Matrix**
We row-reduce matrix $A$ to its row echelon form:
$$ \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \end{bmatrix} \xrightarrow{R_2 - 2R_1 \to R_2} \begin{bmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \end{bmatrix} $$
The row echelon form has one non-zero row, so the rank of the matrix is **1**.

**Step 2: Find the Number of Columns**
The matrix $A$ has **3** columns.

**Step 3: Apply the Rank-Nullity Theorem**
$$ 1 + Nullity(A) = 3 $$
$$ Nullity(A) = 3 - 1 $$
$$ Nullity(A) = 2 $$

The nullity of the matrix is **2**.

---

### Row space - Definition 
Row space of a matrix A = column space of A transpose 

---

### What is the Left Null Space?

The **left null space** of a matrix $A$ is the set of all vectors $\vec{y}$ that satisfy the equation $\vec{y}^T A = \vec{0}^T$. It is also defined as the **null space of the transpose** of the matrix, $Nul(A^T)$. This is because the equation $\vec{y}^T A = \vec{0}^T$ is equivalent to $A^T\vec{y} = \vec{0}$.

The left null space is a subspace of $\mathbb{R}^m$, where $m$ is the number of rows in $A$. A key property is that it is orthogonal to the column space of $A$.

### Example

Let's find the left null space of the matrix:
$$A = \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix}$$

**Step 1: Set up the equation $A^T\vec{y} = \vec{0}$**
First, we find the transpose of $A$:
$$A^T = \begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix}$$
The system we need to solve is:
$$\begin{bmatrix} 1 & 3 \\ 2 & 6 \end{bmatrix} \begin{bmatrix} y_1 \\ y_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

**Step 2: Solve the system by row-reducing the augmented matrix**
$$ \begin{bmatrix} 1 & 3 & 0 \\ 2 & 6 & 0 \end{bmatrix} \xrightarrow{R_2 - 2R_1 \to R_2} \begin{bmatrix} 1 & 3 & 0 \\ 0 & 0 & 0 \end{bmatrix} $$

**Step 3: Write the solution in parametric form**
The row-reduced matrix gives the equation $y_1 + 3y_2 = 0$, which means $y_1 = -3y_2$.
The solution vector $\vec{y}$ can be written as:
$$ \vec{y} = \begin{bmatrix} y_1 \\ y_2 \end{bmatrix} = \begin{bmatrix} -3y_2 \\ y_2 \end{bmatrix} = y_2 \begin{bmatrix} -3 \\ 1 \end{bmatrix} $$
The left null space of $A$ is the span of the vector $\begin{bmatrix} -3 \\ 1 \end{bmatrix}$.

## Summary - 4 fundamental subspaces
(a) column space
(b) null space 
(c) row space 
(d) left null space 