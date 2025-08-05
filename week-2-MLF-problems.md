## Some problems - Week 2 - MLF

### Gradient of a Multivariable Function

**Question:**
Given the function $f(x,y) = x^2 + 2y^3$, what is the gradient of the function at the point $(1, 2)$?

---

**Answer:**
The gradient of a multivariable function is a vector containing its partial derivatives.

1.  **Find the general gradient vector, $\nabla f(x,y)$:**
    * The partial derivative with respect to $x$ is: $\frac{\partial f}{\partial x} = 2x$
    * The partial derivative with respect to $y$ is: $\frac{\partial f}{\partial y} = 6y^2$

    The general gradient vector is:
    $$\nabla f(x,y) = \begin{bmatrix} 2x \\ 6y^2 \end{bmatrix}$$

2.  **Evaluate the gradient at the point $(1, 2)$:**
    Substitute the coordinates of the point ($x=1$ and $y=2$) into the gradient vector:
    $$\nabla f(1, 2) = \begin{bmatrix} 2(1) \\ 6(2)^2 \end{bmatrix} = \begin{bmatrix} 2 \\ 6(4) \end{bmatrix} = \begin{bmatrix} 2 \\ 24 \end{bmatrix}$$

The gradient of the function at the point $(1, 2)$ is $\begin{bmatrix} 2 \\ 24 \end{bmatrix}$.

---

### Linear Approximation - Multivariate problem 

**Question:**
Using the gradient-based formula for linear approximation, find the linear approximation of the function $f(x,y) = x^2 + y^2$ around the point $(1,1)$.

The formula to use is:
$$L(x,y) = f(a,b) + \nabla f(a,b) \cdot \begin{bmatrix} x-a \\ y-b \end{bmatrix}$$

---

**Answer:**
**1. Find the value of the function at the point $(1,1)$:**
$$f(1,1) = (1)^2 + (1)^2 = 2$$

**2. Find the gradient of the function at the point $(1,1)$:**
The partial derivatives are:
$$\frac{\partial f}{\partial x} = 2x \quad \text{and} \quad \frac{\partial f}{\partial y} = 2y$$

Evaluating at $(1,1)$:
$$\frac{\partial f}{\partial x}(1,1) = 2(1) = 2 \quad \text{and} \quad \frac{\partial f}{\partial y}(1,1) = 2(1) = 2$$

The gradient vector at $(1,1)$ is:
$$\nabla f(1,1) = \begin{bmatrix} 2 & 2 \end{bmatrix}$$

**3. Substitute the values into the formula and compute the dot product:**
$$L(x,y) = f(1,1) + \nabla f(1,1) \cdot \begin{bmatrix} x-1 \\ y-1 \end{bmatrix}$$
$$L(x,y) = 2 + \begin{bmatrix} 2 & 2 \end{bmatrix} \cdot \begin{bmatrix} x-1 \\ y-1 \end{bmatrix}$$
$$L(x,y) = 2 + 2(x-1) + 2(y-1)$$

**4. Simplify the expression:**
$$L(x,y) = 2 + 2x - 2 + 2y - 2$$
$$L(x,y) = 2x + 2y - 2$$

The linear approximation of $f(x,y) = x^2 + y^2$ at the point $(1,1)$ is $L(x,y) = 2x + 2y - 2$.

---

### Example problem - Directional Derivative

**Question:**
Find the directional derivative of the function $f(x,y,z) = x^2 + 3y + z^2$ at the point $(1,2,1)$ along the unit vector in the direction of the vector $\langle 1, -2, 1 \rangle$.

---

**Answer:**
To find the directional derivative, we use the formula:
$$D_{\vec{u}} f(\vec{x_0}) = \nabla f(\vec{x_0}) \cdot \vec{u}$$

**Step 1: Find the Gradient of the function, $\nabla f$**
The gradient is the vector of the partial derivatives.
$$ \nabla f(x,y,z) = \left\langle \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} \right\rangle = \langle 2x, 3, 2z \rangle $$

**Step 2: Evaluate the Gradient at the point $(1,2,1)$**
Substitute the coordinates into the gradient vector:
$$ \nabla f(1,2,1) = \langle 2(1), 3, 2(1) \rangle = \langle 2, 3, 2 \rangle $$

**Step 3: Find the Unit Vector, $\vec{u}$**
The given direction vector is $\vec{v} = \langle 1, -2, 1 \rangle$. We must normalize it to get the unit vector $\vec{u}$.
First, find the magnitude of $\vec{v}$:
$$ \|\vec{v}\| = \sqrt{1^2 + (-2)^2 + 1^2} = \sqrt{1+4+1} = \sqrt{6} $$
Now, divide the vector by its magnitude:
$$ \vec{u} = \frac{\vec{v}}{\|\vec{v}\|} = \frac{1}{\sqrt{6}} \langle 1, -2, 1 \rangle = \left\langle \frac{1}{\sqrt{6}}, -\frac{2}{\sqrt{6}}, \frac{1}{\sqrt{6}} \right\rangle $$

**Step 4: Compute the Dot Product**
Finally, we calculate the dot product of the gradient at the point and the unit vector:
$$ D_{\vec{u}} f(1,2,1) = \langle 2, 3, 2 \rangle \cdot \left\langle \frac{1}{\sqrt{6}}, -\frac{2}{\sqrt{6}}, \frac{1}{\sqrt{6}} \right\rangle $$
$$ D_{\vec{u}} f(1,2,1) = (2)\left(\frac{1}{\sqrt{6}}\right) + (3)\left(-\frac{2}{\sqrt{6}}\right) + (2)\left(\frac{1}{\sqrt{6}}\right) $$
$$ D_{\vec{u}} f(1,2,1) = \frac{2 - 6 + 2}{\sqrt{6}} = \frac{-2}{\sqrt{6}} = -\frac{2\sqrt{6}}{6} = -\frac{\sqrt{6}}{3} $$

The directional derivative is $-\frac{\sqrt{6}}{3}$.

---

### Example problem - Directional Derivative

### Question and Answer: Direction of Steepest Ascent

### Question and Answer: Direction of Steepest Ascent (Unit Vector)

**Question:**
Find the direction of steepest ascent for the function $f(x,y,z) = x^2 + y^3 + z^4$ at the point $(1,1,1)$.

---

**Answer:**
The direction of steepest ascent is given by the unit vector in the direction of the gradient.

**1. Find the Gradient of the Function**
The gradient is the vector of the partial derivatives:
$$ \nabla f(x,y,z) = \begin{bmatrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \\ \frac{\partial f}{\partial z} \end{bmatrix} = \begin{bmatrix} 2x \\ 3y^2 \\ 4z^3 \end{bmatrix} $$

**2. Evaluate the Gradient at the Point $(1,1,1)$**
Substitute the coordinates of the point ($x=1$, $y=1$, $z=1$) into the gradient vector:
$$ \nabla f(1,1,1) = \begin{bmatrix} 2(1) \\ 3(1)^2 \\ 4(1)^3 \end{bmatrix} = \begin{bmatrix} 2 \\ 3 \\ 4 \end{bmatrix} $$

**3. Normalize the Gradient Vector to Find the Unit Direction Vector**
First, find the magnitude of the gradient vector at the point:
$$ \|\nabla f(1,1,1)\| = \sqrt{2^2 + 3^2 + 4^2} = \sqrt{4 + 9 + 16} = \sqrt{29} $$
Now, divide the gradient vector by its magnitude to get the unit vector, $\vec{u}$:
$$ \vec{u} = \frac{\nabla f(1,1,1)}{\|\nabla f(1,1,1)\|} = \frac{1}{\sqrt{29}} \begin{bmatrix} 2 \\ 3 \\ 4 \end{bmatrix} = \begin{bmatrix} \frac{2}{\sqrt{29}} \\ \frac{3}{\sqrt{29}} \\ \frac{4}{\sqrt{29}} \end{bmatrix} $$

The direction of steepest ascent for the function $f(x,y,z)$ at the point $(1,1,1)$ is the unit vector $\left\langle \frac{2}{\sqrt{29}}, \frac{3}{\sqrt{29}}, \frac{4}{\sqrt{29}} \right\rangle$.