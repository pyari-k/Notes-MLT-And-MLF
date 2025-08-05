## Derivative - Defintion (First Principles)
The formula for the **derivative** of a function $f(x)$ at a point $x^*$ is given by:

$$f'(x^*) = \lim_{x \to x^*} \frac{f(x) - f(x^*)}{x - x^*}$$

## Linear Approximation
The **definition of the derivative** of a function $f(x)$ at a point $x^*$ is:

$$f'(x^*) = \lim_{x \to x^*} \frac{f(x) - f(x^*)}{x - x^*}$$

When $x$ is very close to $x^*$, the fraction $\frac{f(x) - f(x^*)}{x - x^*}$ is approximately equal to $f'(x^*)$. We can express this as:

$$\frac{f(x) - f(x^*)}{x - x^*} \approx f'(x^*)$$

This implies:

$$f(x) \approx f(x^*) + f'(x^*)(x - x^*)$$

We define the linear approximation, denoted as $L(x)$, using this approximation:

$$L(x) = f(x^*) + f'(x^*)(x - x^*)$$

Note: This formula represents the equation of the tangent line to the function $f(x)$ at the point $(x^*, f(x^*))$. For values of $x$ close to $x^*$, the tangent line provides a good approximation of the function's value.

## Linear Approximation Examples

### Example 1: Linear Approximation of $(1+x)^r$ near $x=0$

Let $f(x) = (1+x)^r$. We want to find its linear approximation around $x^* = 0$.

First, find the function value at $x^*=0$:
$f(0) = (1+0)^r = 1^r = 1$

Next, find the derivative of $f(x)$:
$f'(x) = \frac{d}{dx}(1+x)^r = r(1+x)^{r-1} \cdot 1 = r(1+x)^{r-1}$

Now, evaluate the derivative at $x^*=0$:
$f'(0) = r(1+0)^{r-1} = r(1)^{r-1} = r$

Substitute these values into the linear approximation formula:
$L(x) = f(0) + f'(0)(x - 0)$
$L(x) = 1 + r(x)$
$L(x) = 1 + rx$

So, the linear approximation for $(1+x)^r$ when $x$ is close to 0 is $1 + rx$.
This is a very common and useful approximation, especially for small values of $x$.

---

### Example 2: Approximating $0.99^7$ using Linear Approximation

We want to approximate $0.99^7$. This can be rewritten as $(1 - 0.01)^7$.
This fits the form $(1+x)^r$ from the previous example, where:
* $x = -0.01$ (which is close to 0)
* $r = 7$

Using the linear approximation formula derived in Example 1:
$(1+x)^r \approx 1 + rx$

Substitute $x = -0.01$ and $r = 7$:
$0.99^7 = (1 + (-0.01))^7 \approx 1 + (7)(-0.01)$
$0.99^7 \approx 1 - 0.07$
$0.99^7 \approx 0.93$

Let's compare this to the exact value:
Using a calculator, $0.99^7 \approx 0.932065355$

As you can see, the linear approximation $0.93$ is a very good estimate for $0.99^7$.

## Higher Order Approximations
The Taylor polynomial of degree $n$ for a function $f(x)$ centered at a point $x^*$ is given by:

$$P_n(x) = \sum_{k=0}^{n} \frac{f^{(k)}(x^*)}{k!}(x-x^*)^k$$

Expanded, the formula is:

$$P_n(x) = f(x^*) + f'(x^*)(x-x^*) + \frac{f''(x^*)}{2!}(x-x^*)^2 + \frac{f'''(x^*)}{3!}(x-x^*)^3 + \dots + \frac{f^{(n)}(x^*)}{n!}(x-x^*)^n$$

### Some notes on Higher Order Approximations

### Is quadratic approximation better?

Quadratic approximation or higher order approximation is theoritically better. But considering the complexities, linear approximation is usually sufficient. *Most machine learning problems can be managed with linear approximations. But, there are cases where higher order approximations are better.* Below is one such case. 

Approximating $1.1^7$ using a linear vs. a quadratic approximation centered at $x^*=1$ demonstrates a key advantage of higher-order approximations: improved accuracy.

We can analyze this with the function $f(x) = (1+x)^7$.

---

This is a first-order approximation that matches the function's value and slope at the center point $x^*=1$. As derived above, the common formula used for this is:
 $(1+x)^r \approx 1+rx$.

* **Formula:** $P_1(x) \approx 1+rx$ where $x$ is the change from 1.
* **Values:** $r=7$, $x=0.1$
* **Approximation:** $1+7(0.1) = 1.7$

This approximation is a straight line that only accounts for the initial direction of the function. It fails to account for the increasing steepness of the curve as $x$ moves away from 1.

---

#### 2. Quadratic Approximation ($P_2(x)$)

This is a second-order approximation that adds a new term to account for the function's **concavity** or curvature. It matches the function's value, slope, and curvature at $x^*=1$.

* **Formula:** $P_2(x) = f(1) + f'(1)(x-1) + \frac{f''(1)}{2!}(x-1)^2$
* **Values:** $f(1)=1$, $f'(1)=7$, $f''(1)=42$
* **Approximation:** $P_2(1.1) = 1 + 7(1.1-1) + \frac{42}{2}(1.1-1)^2 = 1.91$

The extra term, $21(x-1)^2$, effectively "bends" the straight line into a parabola, which provides a much closer fit to the original curve of $f(x) = x^7$.

---

#### 3. Comparison

* **Actual Value:** $1.1^7 \approx 1.9487$
* **Linear Error:** $|1.9487 - 1.7| \approx 0.2487$
* **Quadratic Error:** $|1.9487 - 1.91| \approx 0.0387$

The quadratic approximation is better because its error is significantly smaller. It captures more information about the function's behavior (its curvature) than the linear approximation, which only captures its initial direction. As a result, the quadratic approximation stays closer to the true function value over a wider range.






