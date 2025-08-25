### Orthogoal vectors 

Orthogonal vectors are those whose dot product or inner product is zero 

---
### Orthonormal vectors 

Orthonormal vectors are orthogonal vectors of unit length 

---

### Orthogonal Subspaces

Two subspaces, $U$ and $V$, are called **orthogonal** if every vector in $U$ is orthogonal to every vector in $V$.

This means the inner product of every vector $\vec{u}$ in $U$ and every vector $\vec{v}$ in $V$ is zero.

For vectors in $\mathbb{R}^n$, the condition is:
$$ \vec{u} \cdot \vec{v} = 0 \quad \text{for every } \vec{u} \in U \text{ and } \vec{v} \in V $$
Using matrix notation, the dot product can be written as $\vec{u}^T\vec{v}$, so the condition is:
$$ \vec{u}^T\vec{v} = 0 \quad \text{for every } \vec{u} \in U \text{ and } \vec{v} \in V $$

### Orthogonality w.r.t the 4 fundamental subspaces 
1. Row space of A is orthognal to null space of A
2. Column space of $A^T$ is orthogonal to null space of A
3. Column space of A is orthogonal to null space of $A^T$

--

### Vector Projection: Length and Direction

The vector projection of $\mathbf{v_2}$ onto $\mathbf{v_1}$ is a vector that lies along the direction of $\mathbf{v_1}$ and represents the component of $\mathbf{v_2}$ that points in that direction. This vector is created by combining two key parts: a **scalar component** that defines its length and a **unit vector** that defines its direction.

---

#### 1. The Scalar Component (Length)

The length of the projection is called the **scalar projection** of $\mathbf{v_2}$ onto $\mathbf{v_1}$. It's calculated using the dot product and the magnitude of $\mathbf{v_1}$.

The formula for the scalar projection is:
$$ \text{comp}_{\mathbf{v_1}}\mathbf{v_2} = \frac{\mathbf{v_2} \cdot \mathbf{v_1}}{\|\mathbf{v_1}\|} $$
This value tells you how "far" $\mathbf{v_2}$ extends along $\mathbf{v_1}$. It's positive if the vectors point in a similar direction and negative if they point in opposite directions.

---

#### 2. The Direction (Unit Vector)

The direction of the projection is simply the direction of the vector we're projecting onto, which is $\mathbf{v_1}$. To get a pure direction without any magnitude, we use the **unit vector** for $\mathbf{v_1}$. A unit vector is a vector with a length of 1.

The formula for the unit vector of $\mathbf{v_1}$ is:
$$ \hat{\mathbf{v_1}} = \frac{\mathbf{v_1}}{\|\mathbf{v_1}\|} $$

---

#### 3. The Full Vector Projection

By multiplying the scalar projection (length) by the unit vector (direction), we get the full **vector projection**.

$$ \text{proj}_{\mathbf{v_1}}\mathbf{v_2} = \left( \frac{\mathbf{v_2} \cdot \mathbf{v_1}}{\|\mathbf{v_1}\|} \right) \left( \frac{\mathbf{v_1}}{\|\mathbf{v_1}\|} \right) = \left( \frac{\mathbf{v_2} \cdot \mathbf{v_1}}{\|\mathbf{v_1}\|^2} \right) \mathbf{v_1} $$

This formula gives you the final vector that represents the shadow of $\mathbf{v_2}$ on $\mathbf{v_1}$.

---

### Alternative Notation

In matrix notation, the dot product of two vectors, $\mathbf{v_2} \cdot \mathbf{v_1}$, can also be written as a matrix multiplication: $\mathbf{v_1}^T \mathbf{v_2}$. This is a common convention in linear algebra, especially when dealing with column vectors.

Therefore, the formula for the vector projection can also be expressed as:
$$ \text{proj}_{\mathbf{v_1}}\mathbf{v_2} = \left( \frac{\mathbf{v_1}^T \mathbf{v_2}}{\|\mathbf{v_1}\|^2} \right) \mathbf{v_1} = \left( \frac{\mathbf{v_1}^T \mathbf{v_2}}{\mathbf{v_1}^T \mathbf{v_1}} \right) \mathbf{v_1} $$
This version is particularly useful in proofs and calculations involving matrices.

---

### Least Squares

`AᵀAx = Aᵀb` is the **normal equation** for the least squares problem. The solution `x` to this equation is the one that minimizes the squared Euclidean norm of the residual vector, `‖Ax - b‖²`.

---
### Example problem - on projection of a vector 
#### Problem

i. Find the projection matrix for $a = \begin{bmatrix} 2 \\ -1 \\ 2 \\ 3 \end{bmatrix}$.

ii. Obtain the projection of $b = \begin{bmatrix} 1 \\ 3 \\ -2 \\ 5 \end{bmatrix}$ onto $a$ and compute the error.


#### Solution

### i. Find the projection matrix for $a$

The projection matrix onto a single vector $a$ is given by the formula:

$P = \frac{aa^T}{a^Ta}$

Given $a = \begin{bmatrix} 2 \\ -1 \\ 2 \\ 3 \end{bmatrix}$

First, we calculate $a^Ta$:
$a^Ta = \begin{bmatrix} 2 & -1 & 2 & 3 \end{bmatrix} \begin{bmatrix} 2 \\ -1 \\ 2 \\ 3 \end{bmatrix} = (2)(2) + (-1)(-1) + (2)(2) + (3)(3) = 4 + 1 + 4 + 9 = 18$

Next, we calculate $aa^T$:
$aa^T = \begin{bmatrix} 2 \\ -1 \\ 2 \\ 3 \end{bmatrix} \begin{bmatrix} 2 & -1 & 2 & 3 \end{bmatrix} = \begin{bmatrix} 4 & -2 & 4 & 6 \\ -2 & 1 & -2 & -3 \\ 4 & -2 & 4 & 6 \\ 6 & -3 & 6 & 9 \end{bmatrix}$

Finally, we find the **projection matrix** $P$:
$P = \frac{1}{18} \begin{bmatrix} 4 & -2 & 4 & 6 \\ -2 & 1 & -2 & -3 \\ 4 & -2 & 4 & 6 \\ 6 & -3 & 6 & 9 \end{bmatrix}$

---

### ii. Obtain the projection of $b$ onto $a$ and compute the error.

The projection of vector $b$ onto vector $a$ is given by the formula:
$p = P b = \frac{aa^T}{a^Ta} b = \frac{a^Tb}{a^Ta}a$

Given $b = \begin{bmatrix} 1 \\ 3 \\ -2 \\ 5 \end{bmatrix}$

First, we calculate $a^Tb$:
$a^Tb = \begin{bmatrix} 2 & -1 & 2 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 3 \\ -2 \\ 5 \end{bmatrix} = (2)(1) + (-1)(3) + (2)(-2) + (3)(5) = 2 - 3 - 4 + 15 = 10$

We already calculated $a^Ta = 18$.

Now we find the **projection** $p$:
$p = \frac{10}{18} a = \frac{5}{9} \begin{bmatrix} 2 \\ -1 \\ 2 \\ 3 \end{bmatrix} = \begin{bmatrix} 10/9 \\ -5/9 \\ 10/9 \\ 15/9 \end{bmatrix} = \begin{bmatrix} 10/9 \\ -5/9 \\ 10/9 \\ 5/3 \end{bmatrix}$

The **error vector** is the difference between $b$ and its projection $p$:
$e = b - p = \begin{bmatrix} 1 \\ 3 \\ -2 \\ 5 \end{bmatrix} - \begin{bmatrix} 10/9 \\ -5/9 \\ 10/9 \\ 15/9 \end{bmatrix} = \begin{bmatrix} 9/9 - 10/9 \\ 27/9 - (-5/9) \\ -18/9 - 10/9 \\ 45/9 - 15/9 \end{bmatrix} = \begin{bmatrix} -1/9 \\ 32/9 \\ -28/9 \\ 30/9 \end{bmatrix}$

The magnitude of the error (the error) is its norm, $||e||$:
$||e||^2 = (-\frac{1}{9})^2 + (\frac{32}{9})^2 + (-\frac{28}{9})^2 + (\frac{30}{9})^2$
$||e||^2 = \frac{1}{81} (1 + 1024 + 784 + 900) = \frac{2709}{81} = \frac{301}{9}$
$||e|| = \sqrt{\frac{301}{9}} = \frac{\sqrt{301}}{3}$

---

### Example problem on least squares method 

#### Problem

Build a model that studies the relationship between $x$ and $y$ given in the Table below using the least squares method.

| x | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| y | 2.6 | 3.4 | 7.1 | 10.2 | 13.5 |

---

#### Solution

We are looking for a linear model of the form $y = c + mx$ that best fits the given data. This can be represented as a system of linear equations in the form $Ax = b$:

$c + 1m = 2.6$
$c + 2m = 3.4$
$c + 3m = 7.1$
$c + 4m = 10.2$
$c + 5m = 13.5$

This gives us the matrices:
$A = \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \\ 1 & 4 \\ 1 & 5 \end{bmatrix}$, $x = \begin{bmatrix} c \\ m \end{bmatrix}$, and $b = \begin{bmatrix} 2.6 \\ 3.4 \\ 7.1 \\ 10.2 \\ 13.5 \end{bmatrix}$

To find the least squares solution, we solve the **normal equation**, $A^TAx = A^Tb$.

First, calculate $A^TA$ and $A^Tb$:

$A^TA = \begin{bmatrix} 1 & 1 & 1 & 1 & 1 \\ 1 & 2 & 3 & 4 & 5 \end{bmatrix} \begin{bmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \\ 1 & 4 \\ 1 & 5 \end{bmatrix} = \begin{bmatrix} 5 & 15 \\ 15 & 55 \end{bmatrix}$

$A^Tb = \begin{bmatrix} 1 & 1 & 1 & 1 & 1 \\ 1 & 2 & 3 & 4 & 5 \end{bmatrix} \begin{bmatrix} 2.6 \\ 3.4 \\ 7.1 \\ 10.2 \\ 13.5 \end{bmatrix} = \begin{bmatrix} 36.8 \\ 139.0 \end{bmatrix}$

Now, we solve the system:
$\begin{bmatrix} 5 & 15 \\ 15 & 55 \end{bmatrix} \begin{bmatrix} c \\ m \end{bmatrix} = \begin{bmatrix} 36.8 \\ 139.0 \end{bmatrix}$

Using matrix inversion:
$\begin{bmatrix} c \\ m \end{bmatrix} = \frac{1}{55(5) - 15(15)} \begin{bmatrix} 55 & -15 \\ -15 & 5 \end{bmatrix} \begin{bmatrix} 36.8 \\ 139.0 \end{bmatrix} = \frac{1}{50} \begin{bmatrix} 55 & -15 \\ -15 & 5 \end{bmatrix} \begin{bmatrix} 36.8 \\ 139.0 \end{bmatrix}$

$c = \frac{1}{50}(55 \times 36.8 - 15 \times 139.0) = \frac{1}{50}(2024 - 2085) = \frac{-61}{50} = -1.22$

$m = \frac{1}{50}(-15 \times 36.8 + 5 \times 139.0) = \frac{1}{50}(-552 + 695) = \frac{143}{50} = 2.86$

The resulting linear model is:
**$y = 2.86x - 1.22$**