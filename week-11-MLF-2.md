# 📘 Expectation (Expected Value)

The **expectation** (or **expected value**) of a random variable is a measure of its **average or central tendency**. It represents the value you would expect **on average** if you repeated the experiment many times.

---

## 🔹 1. Expectation for a Discrete Random Variable

If $X$ is a **discrete** random variable taking values $x_1, x_2, \dots$ with corresponding probabilities $P(X = x_i)$, then the **expected value** is:

$$
\mathbb{E}[X] = \sum_{i} x_i \cdot P(X = x_i)
$$

---

### 🎲 Example: Roll a fair 6-sided die

Let $X$ be the number that appears on a fair die. Possible outcomes: $1, 2, 3, 4, 5, 6$  
Each with equal probability $\frac{1}{6}$.

$$
\mathbb{E}[X] = \sum_{i=1}^{6} i \cdot \frac{1}{6} = \frac{1 + 2 + 3 + 4 + 5 + 6}{6} = \frac{21}{6} = 3.5
$$

✅ **Interpretation:** The average value you'd expect over many rolls is **3.5**.

---

## 🔹 2. Expectation for a Continuous Random Variable

If $X$ is a **continuous** random variable with probability density function (PDF) $f(x)$, then:

$$
\mathbb{E}[X] = \int_{-\infty}^{\infty} x \cdot f(x) \, dx
$$

---

### 🌊 Example: Uniform distribution on $[0, 1]$

Let $X \sim \text{Uniform}(0, 1)$ ⇒ $f(x) = 1$ for $x \in [0, 1]$.

$$
\mathbb{E}[X] = \int_0^1 x \cdot 1 \, dx = \left[ \frac{x^2}{2} \right]_0^1 = \frac{1}{2}
$$

✅ **Interpretation:** The average value drawn from a uniform distribution on $[0, 1]$ is **0.5**.

---

## 🧠 Notes

- The expected value may **not** be a possible outcome (e.g., 3.5 on a die).
- Expectation is **linear**:  
  If $X$ and $Y$ are random variables, and $a, b$ are constants:

  $$
  \mathbb{E}[aX + bY] = a \cdot \mathbb{E}[X] + b \cdot \mathbb{E}[Y]
  $$

- Expectation does **not** depend on the spread/variance — only on the average.

---

## ✅ Summary

| Type of Variable   | Formula for Expectation                |
|--------------------|-----------------------------------------|
| Discrete           | $\mathbb{E}[X] = \sum x_i \cdot P(X = x_i)$ |
| Continuous         | $\mathbb{E}[X] = \int x \cdot f(x) \, dx$   |

Use expectation to understand the **long-run average outcome** of a random process.


# 📘 Variance – A Measure of Spread

## 🔹 What is Variance?

The **variance** of a random variable measures how much the values of the variable **deviate from the mean** on average. It tells you about the **spread or dispersion** of a distribution.

---

## 🔸 Definition

For a random variable $X$ with expected value $\mu = \mathbb{E}[X]$, the variance is defined as:

$$
\mathrm{Var}(X) = \mathbb{E}\left[(X - \mu)^2\right]
$$

It can also be expressed using the shortcut formula:

$$
\mathrm{Var}(X) = \mathbb{E}[X^2] - \left(\mathbb{E}[X]\right)^2
$$

---

## 🔹 1. Variance of a Discrete Random Variable

If $X$ takes values $x_1, x_2, \dots, x_n$ with probabilities $P(X = x_i)$, then:

$$
\mathrm{Var}(X) = \sum_{i=1}^n (x_i - \mu)^2 \cdot P(X = x_i)
$$

Or using the shortcut:

$$
\mathrm{Var}(X) = \sum_{i=1}^n x_i^2 \cdot P(X = x_i) - \left( \sum_{i=1}^n x_i \cdot P(X = x_i) \right)^2
$$

---

### 🎲 Example (Discrete): Rolling a fair 6-sided die

Let $X$ be the outcome of rolling a fair die. Then:

- $\mathbb{E}[X] = 3.5$
- $\mathbb{E}[X^2] = \frac{1^2 + 2^2 + 3^2 + 4^2 + 5^2 + 6^2}{6} = \frac{91}{6}$

So,

$$
\mathrm{Var}(X) = \mathbb{E}[X^2] - \left(\mathbb{E}[X]\right)^2 = \frac{91}{6} - (3.5)^2 = \frac{91}{6} - \frac{49}{4} = \frac{35}{12} \approx 2.92
$$

---

## 🔹 2. Variance of a Continuous Random Variable

If $X$ is a continuous random variable with PDF $f(x)$:

$$
\mathrm{Var}(X) = \int_{-\infty}^{\infty} (x - \mu)^2 \cdot f(x) \, dx
$$

Or using the shortcut:

$$
\mathrm{Var}(X) = \int_{-\infty}^{\infty} x^2 \cdot f(x) \, dx - \left( \int_{-\infty}^{\infty} x \cdot f(x) \, dx \right)^2
$$

---

### 🌊 Example (Continuous): Uniform distribution on $[a, b]$

Let $X \sim \text{Uniform}(a, b)$. Then:

- $\mathbb{E}[X] = \frac{a + b}{2}$
- $\mathrm{Var}(X) = \frac{(b - a)^2}{12}$

#### Example: $X \sim \text{Uniform}(2, 8)$

- $\mathbb{E}[X] = \frac{2 + 8}{2} = 5$
- $\mathrm{Var}(X) = \frac{(8 - 2)^2}{12} = \frac{36}{12} = 3$

✅ Interpretation: The values of $X$ tend to vary around the mean (5) with a typical squared deviation of 3.

---

## 🔹 Key Properties of Variance

- **Always non-negative:** $\mathrm{Var}(X) \geq 0$
- **Variance of a constant:** $\mathrm{Var}(c) = 0$
- **Scaling property:**

  If $Y = aX + b$, then:

  $$
  \mathrm{Var}(Y) = a^2 \cdot \mathrm{Var}(X)
  $$

- **Standard Deviation** is the square root of variance:

  $$
  \sigma_X = \sqrt{\mathrm{Var}(X)}
  $$

---

## ✅ Summary

| Concept               | Formula                                      |
|-----------------------|----------------------------------------------|
| Variance (definition) | $\mathrm{Var}(X) = \mathbb{E}[(X - \mu)^2]$  |
| Shortcut formula      | $\mathrm{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$ |
| Discrete example      | Die roll: $\mathrm{Var}(X) = \frac{35}{12}$  |
| Uniform $[a,b]$       | $\mathrm{Var}(X) = \frac{(b - a)^2}{12}$     |

Use variance to measure the **spread** or **uncertainty** in a random variable!
