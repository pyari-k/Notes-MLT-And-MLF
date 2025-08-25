# Covariance of Two Discrete Variables

### **Question:** Given the joint probability mass function (PMF) of two discrete random variables, $X$ and $Y$, in the table below, what is the covariance between $X$ and $Y$?

|  | y=1 | y=2 | y=3 |
|---|---|---|---|
| x=1 | 0.25 | 0.25 | 0 |
| x=2 | 0 | 0.25 | 0.25 |

### **Answer:** The covariance between $X$ and $Y$ is **0.25**.

***

### **Step-by-Step Solution**

The formula for covariance is:
$\text{Cov}(X,Y) = E[XY] - E[X]E[Y]$

#### 1. Calculate the Expected Value of X, $E[X]$
First, find the marginal probabilities for $X$ by summing the probabilities in each row.
* $P(X=1) = 0.25 + 0.25 + 0 = 0.5$
* $P(X=2) = 0 + 0.25 + 0.25 = 0.5$

Then, calculate $E[X]$:
$E[X] = (1)(0.5) + (2)(0.5) = 0.5 + 1 = 1.5$

#### 2. Calculate the Expected Value of Y, $E[Y]$
Find the marginal probabilities for $Y$ by summing the probabilities in each column.
* $P(Y=1) = 0.25 + 0 = 0.25$
* $P(Y=2) = 0.25 + 0.25 = 0.5$
* $P(Y=3) = 0 + 0.25 = 0.25$

Then, calculate $E[Y]$:
$E[Y] = (1)(0.25) + (2)(0.5) + (3)(0.25) = 0.25 + 1 + 0.75 = 2$

#### 3. Calculate the Expected Value of XY, $E[XY]$
Multiply each $x$ and $y$ value by their joint probability and sum the results.
$E[XY] = (1 \cdot 1 \cdot 0.25) + (1 \cdot 2 \cdot 0.25) + (1 \cdot 3 \cdot 0) + (2 \cdot 1 \cdot 0) + (2 \cdot 2 \cdot 0.25) + (2 \cdot 3 \cdot 0.25)$
$E[XY] = 0.25 + 0.5 + 0 + 0 + 1 + 1.5 = 3.25$

#### 4. Calculate the Covariance
Finally, substitute the values into the covariance formula.
$\text{Cov}(X,Y) = 3.25 - (1.5)(2)$
$\text{Cov}(X,Y) = 3.25 - 3 = 0.25$