### What is a Convex Set?

In mathematics, a **convex set** is a set of points where, for any two points within the set, the entire line segment connecting those points is also contained within the set. Geometrically, this means there are no "dents" or "holes" in the set. A solid circle or a square are examples of convex sets. A crescent shape or a donut, however, are not.

---

### Mathematical Definition using $\lambda$

The mathematical definition of a convex set, $S$, in a vector space is given by the following condition:

For any two points $x_1$ and $x_2$ in $S$, the point defined by the expression:
$$\lambda x_1 + (1 - \lambda)x_2$$
must also be in $S$ for all values of $\lambda$ such that $0 \le \lambda \le 1$.

In this expression:
* $\lambda$ is a scalar that varies from 0 to 1.
* The term $\lambda x_1 + (1 - \lambda)x_2$ represents a **convex combination** of the points $x_1$ and $x_2$.

### Geometric Interpretation of $\lambda$

The value of $\lambda$ determines the specific point on the line segment between $x_1$ and $x_2$:
* When $\lambda = 0$, the expression simplifies to $x_2$, which is one of the endpoints.
* When $\lambda = 1$, the expression simplifies to $x_1$, the other endpoint.
* When $\lambda = 0.5$, the expression gives the midpoint of the line segment.

As $\lambda$ continuously varies from 0 to 1, the expression $\lambda x_1 + (1 - \lambda)x_2$ traces out every single point on the straight line segment connecting $x_1$ and $x_2$. The formal definition of a convex set ensures that this entire path remains within the set.

---

### Convexity of Hyperplanes and Half-Spaces

#### Hyperplanes

A **hyperplane** in an n-dimensional space ($R^n$) is a flat, n-1 dimensional subspace. It is defined by the equation:
$$ \mathbf{w}^T \mathbf{x} + b = 0 $$
where $\mathbf{w}$ is a non-zero normal vector, $\mathbf{x}$ is a vector of coordinates, and $b$ is a scalar bias term.

To prove a hyperplane is convex, consider any two points $\mathbf{x}_1$ and $\mathbf{x}_2$ that lie on the hyperplane. By definition, they satisfy the equation:
$$ \mathbf{w}^T \mathbf{x}_1 + b = 0 \quad \text{and} \quad \mathbf{w}^T \mathbf{x}_2 + b = 0 $$
For any point on the line segment connecting $\mathbf{x}_1$ and $\mathbf{x}_2$, the point can be written as $\mathbf{x}_\lambda = \lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2$ for $0 \le \lambda \le 1$.
Let's check if this point also lies on the hyperplane:
$$ \mathbf{w}^T (\lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2) + b = \lambda(\mathbf{w}^T \mathbf{x}_1) + (1 - \lambda)(\mathbf{w}^T \mathbf{x}_2) + b $$
Since $\mathbf{w}^T \mathbf{x}_1 = -b$ and $\mathbf{w}^T \mathbf{x}_2 = -b$, the expression becomes:
$$ \lambda(-b) + (1 - \lambda)(-b) + b = -b(\lambda + 1 - \lambda) + b = -b(1) + b = 0 $$
Since the entire line segment lies on the hyperplane, it is a convex set.

---

#### Half-Spaces

A **half-space** is one of the two regions created by a hyperplane. It is defined by an inequality:
$$ \mathbf{w}^T \mathbf{x} + b \ge 0 \quad \text{or} \quad \mathbf{w}^T \mathbf{x} + b \le 0 $$
To prove a half-space is convex, let's consider the first inequality and take two points, $\mathbf{x}_1$ and $\mathbf{x}_2$, from this half-space. This means:
$$ \mathbf{w}^T \mathbf{x}_1 + b \ge 0 \quad \text{and} \quad \mathbf{w}^T \mathbf{x}_2 + b \ge 0 $$
Let's take a point on the line segment connecting them, $\mathbf{x}_\lambda = \lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2$, where $0 \le \lambda \le 1$. We need to show that this point is also in the half-space:
$$ \mathbf{w}^T \mathbf{x}_\lambda + b = \mathbf{w}^T (\lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2) + b $$
$$ = \lambda(\mathbf{w}^T \mathbf{x}_1) + (1 - \lambda)(\mathbf{w}^T \mathbf{x}_2) + b $$
$$ = \lambda(\mathbf{w}^T \mathbf{x}_1 + b) + (1 - \lambda)(\mathbf{w}^T \mathbf{x}_2 + b) $$
Since $\lambda \ge 0$, $(1 - \lambda) \ge 0$, and both $(\mathbf{w}^T \mathbf{x}_1 + b) \ge 0$ and $(\mathbf{w}^T \mathbf{x}_2 + b) \ge 0$, the entire expression must be greater than or equal to zero.
$$ \mathbf{w}^T \mathbf{x}_\lambda + b \ge 0 $$
This proves that the entire line segment lies within the half-space, so it is a convex set.