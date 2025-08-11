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

### Projection of a vector b on vector a 

The projection of a vector $\vec{b}$ onto a vector $\vec{a}$ is given by the formula:
$$\text{proj}_{\vec{a}}\vec{b} = \frac{\vec{a} \cdot \vec{b}}{\|\vec{a}\|^2} \vec{a}$$
However, the expression for the **projection matrix**, $P$, is what allows you to get this result with a matrix multiplication. The projection matrix projects any vector in the space onto the line spanned by vector $\vec{a}$.

Your formula for the projection matrix, $P = \frac{\vec{a}\vec{a}^T}{\vec{a}^T\vec{a}}$, is correct. Let's break down why this works.

### Explanation of the Formula

1.  **The Projection Vector, $\vec{p}$:**
    The projection of $\vec{b}$ onto $\vec{a}$ is a vector, often called $\vec{p}$.
    $$\vec{p} = P\vec{b}$$

2.  **The Denominator: $(\vec{a}^T\vec{a})$**
    The term $\vec{a}^T\vec{a}$ is the inner product (dot product) of $\vec{a}$ with itself. For a column vector $\vec{a}$, this is a scalar equal to the squared magnitude of $\vec{a}$.
    $$\vec{a}^T\vec{a} = \vec{a} \cdot \vec{a} = \|\vec{a}\|^2$$
    This is the same denominator as in the standard projection formula.

3.  **The Numerator: $(\vec{a}\vec{a}^T)$**
    The term $\vec{a}\vec{a}^T$ is the outer product of $\vec{a}$ with itself. This operation results in a matrix, not a scalar. This matrix is what "acts" on $\vec{b}$.

4.  **Putting it all together:**
    When you multiply the projection matrix $P$ by the vector $\vec{b}$, you get:
    $$\vec{p} = P\vec{b} = \left( \frac{\vec{a}\vec{a}^T}{\vec{a}^T\vec{a}} \right)\vec{b}$$
    Since $\vec{a}^T\vec{a}$ is a scalar, we can move it to the side:
    $$\vec{p} = \frac{1}{\vec{a}^T\vec{a}}(\vec{a}\vec{a}^T)\vec{b}$$
    Matrix multiplication is associative, so we can group it as $\vec{a}(\vec{a}^T\vec{b})$. The term $\vec{a}^T\vec{b}$ is the dot product of $\vec{a}$ and $\vec{b}$, which is a scalar.
    $$\vec{p} = \frac{1}{\|\vec{a}\|^2}\vec{a}(\vec{a}^T\vec{b}) = \frac{\vec{a} \cdot \vec{b}}{\|\vec{a}\|^2} \vec{a}$$
    This is the standard formula for the projection of $\vec{b}$ onto $\vec{a}$, confirming that your expression for the projection matrix is correct.