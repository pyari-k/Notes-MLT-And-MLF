# Conditional Probability

### **Question:** Let $X$ and $Y$ be two random variables with the joint PMF given in the table below. Calculate the conditional probability $f_{Y|X=2}(2)$.

| | y=1 | y=2 | y=3 |
|---|---|---|---|
| x=1 | 0.25 | 0.25 | 0 |
| x=2 | 0.125 | a₁ | 0.125 |

### **Answer:** The conditional probability $f_{Y|X=2}(2)$ is **0.50**.

***

### **Step-by-Step Solution**

The formula for conditional probability is:
$f_{Y|X=2}(y) = \frac{P(Y=y, X=2)}{P(X=2)}$

#### 1. Find the value of $a_1$
The sum of all probabilities in a joint PMF table must equal 1.
$0.25 + 0.25 + 0 + 0.125 + a_1 + 0.125 = 1$
$0.75 + a_1 = 1$
$a_1 = 1 - 0.75 = 0.25$

#### 2. Find the marginal probability of $X=2$, $P(X=2)$
Sum the probabilities in the row where $X=2$.
$P(X=2) = P(X=2, Y=1) + P(X=2, Y=2) + P(X=2, Y=3)$
$P(X=2) = 0.125 + a_1 + 0.125 = 0.125 + 0.25 + 0.125 = 0.5$

#### 3. Calculate the conditional probability
Using the formula, substitute the joint probability $P(Y=2, X=2)$, which is $a_1=0.25$, and the marginal probability $P(X=2)=0.5$.
$f_{Y|X=2}(2) = \frac{P(Y=2, X=2)}{P(X=2)} = \frac{0.25}{0.5} = 0.5$

Rounding to two decimal places, the answer is 0.50.

### **Key Probability Relationship**

The relationship between joint, conditional, and marginal probability is fundamental for understanding how events relate to one another.

* **Formula:** Joint Probability = Conditional Probability × Marginal Probability

* **In symbols:** $P(A \cap B) = P(A|B) \cdot P(B)$

* **Explanation:** The probability of both event A and event B occurring ($P(A \cap B)$) is equal to the probability of event A given that event B has occurred ($P(A|B)$), multiplied by the marginal (unconditional) probability of event B ($P(B)$).