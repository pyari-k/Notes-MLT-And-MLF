# PMF and CDF – Explained with a 3-Coin Toss Example

## 🧠 What is a PMF?

A **Probability Mass Function (PMF)** gives the probability that a **discrete random variable** takes on a specific value.

Formally, for a discrete random variable $X$:

$$
\text{PMF:} \quad P(X = x)
$$

---

## 🧠 What is a CDF?

A **Cumulative Distribution Function (CDF)** gives the probability that a random variable is **less than or equal to** a certain value.

Formally:

$$
\text{CDF:} \quad F(x) = P(X \leq x)
$$

---

## 🎲 Example: Tossing a Fair Coin 3 Times

Let’s define the random variable:

> $X$ = number of heads in 3 tosses of a fair coin.

---

### 🎯 Possible Outcomes:

| Outcome     | Number of Heads ($X$) |
|-------------|------------------------|
| T T T       | 0                      |
| H T T       | 1                      |
| T H T       | 1                      |
| T T H       | 1                      |
| H H T       | 2                      |
| H T H       | 2                      |
| T H H       | 2                      |
| H H H       | 3                      |

---

### 📊 PMF of $X$:

Let’s compute the PMF of $X$:

| $x$ | $P(X = x)$ | Explanation                       |
|-----|------------|------------------------------------|
| 0   | 1/8        | Only TTT                           |
| 1   | 3/8        | HTT, THT, TTH                      |
| 2   | 3/8        | HHT, HTH, THH                      |
| 3   | 1/8        | HHH                                |

This defines the PMF:

$$
P(X = x) = 
\begin{cases}
\frac{1}{8} & \text{if } x = 0 \\
\frac{3}{8} & \text{if } x = 1 \\
\frac{3}{8} & \text{if } x = 2 \\
\frac{1}{8} & \text{if } x = 3 \\
0 & \text{otherwise}
\end{cases}
$$

---

### 📈 CDF of $X$:

Now compute the CDF $F(x) = P(X \leq x)$:

| $x$ | $F(x)$         |
|-----|----------------|
| 0   | 1/8            |
| 1   | 1/8 + 3/8 = 4/8 = 0.5 |
| 2   | 0.5 + 3/8 = 7/8 |
| 3   | 1              |

Written as a piecewise function:

$$
F(x) =
\begin{cases}
0 & \text{if } x < 0 \\
\frac{1}{8} & \text{if } 0 \leq x < 1 \\
\frac{4}{8} & \text{if } 1 \leq x < 2 \\
\frac{7}{8} & \text{if } 2 \leq x < 3 \\
1 & \text{if } x \geq 3
\end{cases}
$$

---

## ✅ Summary

- The **PMF** gives the probability for exact outcomes.
- The **CDF** gives the cumulative probability up to a value.
- In this example, $X$ (number of heads in 3 tosses) is a **discrete random variable** with known PMF and CDF.

This is a **Binomial Distribution** with parameters $n = 3$ and $p = 0.5$.
