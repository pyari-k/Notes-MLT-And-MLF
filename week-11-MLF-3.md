### Notes on Uniform Distribution

--- 
### Discrete Uniform Distribution 

A **discrete uniform distribution** is a probability distribution where a finite number of outcomes are all equally likely.

The **Probability Mass Function (PMF)** for this type of distribution is:

$$P(X=x) = \frac{1}{n}$$

- $X$ is the random variable.
- $x$ is a specific outcome.
- $n$ is the total number of possible outcomes.

#### Example: Rolling a fair six-sided die

The possible outcomes are $\{1, 2, 3, 4, 5, 6\}$, so $n=6$. The PMF for any single outcome is:

$$P(X=x) = \frac{1}{6} \quad \text{for } x \in \{1, 2, 3, 4, 5, 6\}$$

---

### Continuous Uniform Distribution

For a **continuous uniform distribution**, we use a **Probability Density Function (PDF)**, not a PMF.

The PDF for a continuous variable over the interval $[a, b]$ is:

$$f(x) = \frac{1}{b-a} \quad \text{for } a \le x \le b$$



# 📘 Expected Value of a Uniform Distribution

## 🔹 Definition: Continuous Uniform Distribution on \([a, b]\)

A random variable \( X \) is said to follow a **uniform distribution** on the interval \([a, b]\), written as:

$$
X \sim \text{Uniform}(a, b)
$$

This means that the probability density function (PDF) of \( X \) is:

$$
f(x) = 
\begin{cases}
\frac{1}{b - a}, & \text{if } a \leq x \leq b \\
0, & \text{otherwise}
\end{cases}
$$

---

## 🔹 Expected Value (Mean)

The **expected value** of a continuous random variable is given by:

$$
\mathbb{E}[X] = \int_{-\infty}^{\infty} x \cdot f(x) \, dx
$$

For the uniform distribution:

$$
\mathbb{E}[X] = \int_a^b x \cdot \frac{1}{b - a} \, dx
$$

Let’s compute it:

$$
\mathbb{E}[X] = \frac{1}{b - a} \int_a^b x \, dx = \frac{1}{b - a} \left[ \frac{x^2}{2} \right]_a^b
= \frac{1}{b - a} \cdot \left( \frac{b^2 - a^2}{2} \right)
= \frac{a + b}{2}
$$

✅ **Result**:  
The expected value of \( X \sim \text{Uniform}(a, b) \) is:

$$
\mathbb{E}[X] = \frac{a + b}{2}
$$

---

## 🎯 Interpretation

- The expected value is simply the **midpoint** of the interval \([a, b]\).
- Since the distribution is symmetric, the average outcome over many samples will tend toward the center.

---

## 🧪 Example

Let $X \sim \text{Uniform}(2, 8)$. Then:

$$
\mathbb{E}[X] = \frac{2 + 8}{2} = 5
$$

✅ On average, the values of \( X \) will center around **5**.
