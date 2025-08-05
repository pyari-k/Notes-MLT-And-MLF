### Continuity and Limits

A function $f(x)$ is **continuous at a point $c$** if and only if the following three conditions are met:

1.  The function value $f(c)$ is defined.
2.  The limit of the function as $x$ approaches $c$ exists. This means $\lim_{x \to c} f(x)$ is a finite number.
3.  The value of the limit is equal to the value of the function at that point. That is, $\lim_{x \to c} f(x) = f(c)$.

This definition means that there are no holes, jumps, or vertical asymptotes at the point $c$. The function's graph is an unbroken curve at that specific point.

### Question and Answer: Continuity of a Piecewise Function

**Question:** Is the function $f(x)$ continuous at $x = 0$?

The function is defined as:
$$
f(x) = \begin{cases}
    \frac{\sin(x)}{x} & \text{if } x \neq 0 \\
    1 & \text{if } x = 0
\end{cases}
$$

---

**Answer:** Yes, the function $f(x)$ is continuous at $x = 0$.

To determine this, we must check the three conditions for continuity at a point:

1.  **Is $f(0)$ defined?**
    Yes, the function explicitly states that $f(0) = 1$.

2.  **Does the limit of $f(x)$ as $x$ approaches $0$ exist?**
    We need to evaluate the limit for the part of the function where $x \neq 0$:
    $$ \lim_{x \to 0} \frac{\sin(x)}{x} $$
    This is a well-known trigonometric limit, and its value is 1.

3.  **Is the limit equal to the function's value at the point?**
    We compare the results from the previous two steps:
    $$ \lim_{x \to 0} f(x) = 1 \quad \text{and} \quad f(0) = 1 $$
    Since $\lim_{x \to 0} f(x) = f(0)$, all three conditions are met. Therefore, the function is continuous at $x = 0$.

---

### Directional Derviative

The directional derivative of a function measures its instantaneous rate of change at a specific point and in a specific direction.

For a differentiable function $f$ at a point $\vec{x_0}$ and along a direction vector $\vec{v}$, the directional derivative is given by:

$$D_{\vec{u}} f(\vec{x_0}) = \nabla f(\vec{x_0}) \cdot \vec{u}$$

Where:
* $D_{\vec{u}} f(\vec{x_0})$ is the directional derivative of $f$ at the point $\vec{x_0}$.
* $\nabla f(\vec{x_0})$ is the **gradient** of the function $f$, evaluated at the point $\vec{x_0}$.
* $\vec{u}$ is a **unit vector** in the direction of the desired change. If you are given a non-unit vector $\vec{v}$, you must first normalize it to find $\vec{u}$:
    $$\vec{u} = \frac{\vec{v}}{\|\vec{v}\|}$$
* The symbol $\cdot$ denotes the **dot product** between the gradient vector and the unit direction vector.

In simpler terms, the directional derivative is the dot product of the gradient vector and the unit direction vector.

### Notes
Steepest Ascend - means gradient
Direction of Steepest Ascend - means the unit vector in the direction of the gradient 