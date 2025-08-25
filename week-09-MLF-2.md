### Properties of Convex Sets

#### 1. Intersection of Convex Sets

The **intersection** of any collection of convex sets is also a convex set.

To prove this, let's consider two convex sets, $C_1$ and $C_2$. Their intersection is $C = C_1 \cap C_2$.

Let $\mathbf{x}_1$ and $\mathbf{x}_2$ be any two points in $C$.
By the definition of intersection, this means:
* $\mathbf{x}_1 \in C_1$ and $\mathbf{x}_1 \in C_2$
* $\mathbf{x}_2 \in C_1$ and $\mathbf{x}_2 \in C_2$

Since $C_1$ is a convex set, the line segment between $\mathbf{x}_1$ and $\mathbf{x}_2$ must lie entirely within $C_1$.
$$ \lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2 \in C_1 \quad \text{for all } \lambda \in [0, 1] $$
Similarly, since $C_2$ is a convex set, the same line segment must also lie entirely within $C_2$.
$$ \lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2 \in C_2 \quad \text{for all } \lambda \in [0, 1] $$
Because the line segment is in both $C_1$ and $C_2$, it must also be in their intersection, $C$.
$$ \lambda \mathbf{x}_1 + (1 - \lambda)\mathbf{x}_2 \in C_1 \cap C_2 \quad \text{for all } \lambda \in [0, 1] $$
Therefore, the intersection $C_1 \cap C_2$ is a convex set. This property extends to the intersection of any number of convex sets.

---

#### 2. Union of Convex Sets

The **union** of two convex sets is **not necessarily convex**.

For example, consider two disjoint convex sets, a circle $C_1$ and another circle $C_2$. The union of these two circles is not a convex set, as the line segment connecting a point in $C_1$ to a point in $C_2$ would pass through the space between them, which is not part of the union.

---

#### 3. Scaling and Translation

If $C$ is a convex set, then scaling it by a positive scalar $\alpha > 0$ or translating it by a vector $\mathbf{v}$ results in a new set that is also convex.

* **Scaling:** $\alpha C = \{\alpha\mathbf{x} \mid \mathbf{x} \in C\}$
* **Translation:** $C + \mathbf{v} = \{\mathbf{x} + \mathbf{v} \mid \mathbf{x} \in C\}$

The proof for both follows a similar logic to the intersection proof, by applying the transformation to the convex combination of two points and showing the resulting point remains in the new set.


#### 4. Solutions to linear system of equations
Solutions to linear system of equations are convex sets 