A complex number is a number that can be expressed in the form $a + bi$, where **$a$ and $b$ are real numbers**, and **$i$ is the imaginary unit** defined by $i^2 = -1$. The real number $a$ is the **real part**, and the real number $b$ is the **imaginary part**. Complex numbers extend the real number system, allowing for the solution of equations like $x^2 + 1 = 0$.

***


## Key Properties and Operations ➕➖✖️➗

* **Addition and Subtraction**: These operations are performed by adding or subtracting the corresponding real and imaginary parts.
    * $(a + bi) + (c + di) = (a + c) + (b + d)i$
    * $(a + bi) - (c + di) = (a - c) + (b - d)i$

* **Multiplication**: This is carried out using the distributive property, remembering that $i^2 = -1$.
    * $(a + bi)(c + di) = (ac - bd) + (ad + bc)i$

* **Conjugate**: The complex conjugate of a complex number $z = a + bi$ is $\bar{z} = a - bi$. Geometrically, it is the reflection of $z$ across the real axis.

* **Modulus**: The modulus (or absolute value) of a complex number $z = a + bi$ is its distance from the origin in the complex plane, denoted as $|z|$. It's calculated as $|z| = \sqrt{a^2 + b^2}$.

***

## The Conjugate and its Relation to the Modulus

The **conjugate** of a complex number $z = a + bi$ is $\bar{z} = a - bi$. The modulus of $z$ is $|z| = \sqrt{a^2 + b^2}$.

The key relationship is that **the product of a complex number and its conjugate is equal to the square of its modulus**:

$$z\bar{z} = |z|^2$$

This is shown by multiplying $z = a + bi$ and $\bar{z} = a - bi$:

$z\bar{z} = (a + bi)(a - bi) = a^2 - (bi)^2 = a^2 - b^2i^2 = a^2 + b^2$

Since $|z| = \sqrt{a^2 + b^2}$, squaring both sides gives $|z|^2 = a^2 + b^2$. This property is especially useful for dividing complex numbers, as multiplying the numerator and denominator by the conjugate of the denominator eliminates the imaginary part from the denominator.

---
### Polar Form of Complex Numbers

A complex number can be expressed in **polar form** as $z = r(\cos\theta + i\sin\theta)$, where $r$ is the **modulus** (distance from the origin) and $\theta$ is the **argument** (angle from the positive real axis). This form is particularly useful for multiplication, division, and finding powers of complex numbers.

---
### Euler's formula & Exponential Form of Complex Numbers

A complex number can be expressed in terms of the number **$e$** using **Euler's formula**, which states:

$$e^{i\theta} = \cos\theta + i\sin\theta$$

This allows the **polar form** $z = r(\cos\theta + i\sin\theta)$ to be written concisely as the **exponential form**:

$$z = re^{i\theta}$$

In this form, $r$ is the **modulus** and $\theta$ is the **argument**. This is a very powerful representation for performing multiplication, division, and finding powers of complex numbers.

---
### Conjugate Transpose 

The **conjugate transpose**, denoted as $A^*$, is the operation applied to a complex matrix $A$ where each entry is replaced by its **complex conjugate**, and the resulting matrix is then **transposed**. It is also commonly known as the **Hermitian conjugate** or **Hermitian transpose**. This operation is the complex number equivalent of the standard transpose for real matrices.

### Square of the Modulus of a Complex Vector ($||\boldsymbol{v}||^2$) 📝

The square of the modulus of a complex vector is its squared length. It's calculated by multiplying the vector's conjugate transpose by the vector itself, which is equivalent to summing the squares of the moduli of its individual components.

For **real vectors**, the square of the modulus is $\boldsymbol{v}^T \boldsymbol{v}$.

For **complex vectors**, the square of the modulus is $\boldsymbol{v}^* \boldsymbol{v}$.

---
### Hermitian Matrix 📝

A **Hermitian matrix** is a square complex matrix that is equal to its own **conjugate transpose** ($A = A^*$). All elements on the main diagonal of a Hermitian matrix must be **real numbers**.

#### Properties

* For **real matrices**, the equivalent is a **symmetric matrix**, where the matrix is equal to its own transpose ($A = A^T$).
* The **eigenvalues** of a Hermitian matrix are always **real numbers**.
* The **eigenvectors** corresponding to distinct eigenvalues are **orthogonal**. This means their inner product is zero.


**Example:**
$A = \begin{bmatrix} 2 & 3+4i \\ 3-4i & 5 \end{bmatrix}$

In this example, the diagonal elements are $2$ and $5$, which are real numbers. The off-diagonal element $3+4i$ is the complex conjugate of $3-4i$. Therefore, $A=A^*$, and the matrix is Hermitian.

---

### Unitary Matrix 📝

A **unitary matrix** is a square complex matrix $U$ whose conjugate transpose is also its inverse.

$U^*U = UU^* = I$

* **Comparison to Orthogonal Matrices:** A unitary matrix is the complex equivalent of an **orthogonal matrix** ($Q^T = Q^{-1}$) on the real side. If a unitary matrix has only real entries, it is an orthogonal matrix.

**Example:**
$U = \frac{1}{\sqrt{2}}\begin{bmatrix} 1 & i \\ i & 1 \end{bmatrix}$

To check if it's unitary, we find $U^*$:

$U^* = \frac{1}{\sqrt{2}}\begin{bmatrix} 1 & -i \\ -i & 1 \end{bmatrix}$

Now, we multiply $U^*U$:

$U^*U = \frac{1}{2}\begin{bmatrix} 1 & -i \\ -i & 1 \end{bmatrix}\begin{bmatrix} 1 & i \\ i & 1 \end{bmatrix} = \frac{1}{2}\begin{bmatrix} 1(1)+(-i)(i) & 1(i)+(-i)(1) \\ -i(1)+1(i) & -i(i)+1(1) \end{bmatrix}$

$U^*U = \frac{1}{2}\begin{bmatrix} 1+1 & i-i \\ -i+i & 1+1 \end{bmatrix} = \frac{1}{2}\begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} = I$

Since $U^*U = I$, the matrix $U$ is a unitary matrix.