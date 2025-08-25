# Single Variable Functions
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


## More examples on linear approximations - using product rule and chain rule 

---

### Question 1

1. Find an approximation for the function $f(x) = \frac{e^{3x}}{\sqrt{1+x}}$

Linear approximation is built from the function's value and its derivative at a specific point, which we'll choose as $x^* = 0$ for convenience.

The linear approximation formula centered at $x^*=0$ is:
$$f(x) \approx f(0) + f'(0)(x-0)$$

We need to calculate $f(0)$ and $f'(0)$.

#### Step 1: Find the value of the function at $x=0$

First, let's find the value of the original function at $x=0$:
$$f(x) = \frac{e^{3x}}{\sqrt{1+x}}$$
$$f(0) = \frac{e^{3(0)}}{\sqrt{1+0}} = \frac{e^0}{\sqrt{1}} = \frac{1}{1} = 1$$

#### Step 2: Find the derivative of the function, $f'(x)$

To find the derivative of $f(x)$, we must use the **quotient rule**, which states:
$$\frac{d}{dx}\left(\frac{u}{v}\right) = \frac{u'v - uv'}{v^2}$$

Here, we define our numerator and denominator and their derivatives:

* **Numerator:** $u = e^{3x}$
    To find $u'$, we use the **chain rule**. The outer function is $e^z$ and the inner function is $3x$.
    $u' = e^{3x} \cdot (3x)' = 3e^{3x}$

* **Denominator:** $v = \sqrt{1+x} = (1+x)^{1/2}$
    To find $v'$, we use the **chain rule**. The outer function is $z^{1/2}$ and the inner function is $1+x$.
    $v' = \frac{1}{2}(1+x)^{-1/2} \cdot (1+x)' = \frac{1}{2}(1+x)^{-1/2} \cdot 1 = \frac{1}{2\sqrt{1+x}}$

Now, substitute these components into the quotient rule formula:
$$f'(x) = \frac{(3e^{3x})(\sqrt{1+x}) - (e^{3x})\left(\frac{1}{2\sqrt{1+x}}\right)}{(\sqrt{1+x})^2}$$

To simplify, let's find a common denominator in the numerator:
$$f'(x) = \frac{\frac{3e^{3x}\sqrt{1+x} \cdot 2\sqrt{1+x}}{2\sqrt{1+x}} - \frac{e^{3x}}{2\sqrt{1+x}}}{1+x}$$
$$f'(x) = \frac{\frac{6e^{3x}(1+x) - e^{3x}}{2\sqrt{1+x}}}{1+x} = \frac{6e^{3x}(1+x) - e^{3x}}{2(1+x)^{3/2}}$$

#### Step 3: Evaluate the derivative at $x=0$

Now we find the value of the derivative at $x=0$:
$$f'(0) = \frac{6e^{3(0)}(1+0) - e^{3(0)}}{2(1+0)^{3/2}} = \frac{6(1)(1) - 1}{2(1)^{3/2}} = \frac{6-1}{2} = \frac{5}{2}$$

### Step 4: Construct the linear approximation

Finally, we plug the values $f(0)=1$ and $f'(0)=\frac{5}{2}$ into the linear approximation formula:
$$f(x) \approx f(0) + f'(0)x$$
$$f(x) \approx 1 + \frac{5}{2}x$$

This linear approximation, $L(x) = 1 + \frac{5}{2}x$, provides a good estimate for the original function $f(x) = \frac{e^{3x}}{\sqrt{1+x}}$ for values of $x$ close to 0. For example, to approximate $f(0.1)$, we can use:
$$f(0.1) \approx 1 + \frac{5}{2}(0.1) = 1 + 2.5(0.1) = 1 + 0.25 = 1.25$$
The actual value is $f(0.1) \approx 1.259...$, showing our approximation is quite close.

---

**Note:** This linear approximation, $L(x) = 1 + \frac{5}{2}x$, provides a good estimate for the original function $f(x) = \frac{e^{3x}}{\sqrt{1+x}}$ for values of $x$ close to 0. For example, to approximate $f(0.1)$, we can use:
$$f(0.1) \approx 1 + \frac{5}{2}(0.1) = 1 + 2.5(0.1) = 1 + 0.25 = 1.25$$
The actual value is $f(0.1) \approx 1.259...$, showing our approximation is quite close.

---

### Question 2

2. Find the linear approximation of the function $f(x) = e^{\sqrt{1+x}}$ around the point $x=1$

We use the formula:
$$L(x) = f(x^*) + f'(x^*)(x-x^*)$$
In this case, $x^*=1$.

### Step 1: Find the value of the function and its derivative at $x=1$

* **Function value at $x=1$:**
    $$f(1) = e^{\sqrt{1+1}} = e^{\sqrt{2}}$$
    The numerical value is approximately $4.113$.

* **Derivative of the function:**
    We use the chain rule to find the derivative of $f(x)$. The outer function is $e^u$ and the inner function is $u = \sqrt{1+x}$.
    $$f'(x) = \frac{d}{dx}\left(e^{\sqrt{1+x}}\right) = e^{\sqrt{1+x}} \cdot \frac{d}{dx}(\sqrt{1+x})$$
    $$f'(x) = e^{\sqrt{1+x}} \cdot \frac{1}{2\sqrt{1+x}} = \frac{e^{\sqrt{1+x}}}{2\sqrt{1+x}}$$

* **Derivative value at $x=1$:**
    $$f'(1) = \frac{e^{\sqrt{1+1}}}{2\sqrt{1+1}} = \frac{e^{\sqrt{2}}}{2\sqrt{2}}$$
    The numerical value is approximately $1.454$.

### Step 2: Construct the linear approximation

Now, we substitute the values we found into the linear approximation formula:
$$L(x) = f(1) + f'(1)(x-1)$$
$$L(x) = e^{\sqrt{2}} + \frac{e^{\sqrt{2}}}{2\sqrt{2}}(x-1)$$

Using the numerical values we calculated, the linear approximation can be written as:
$$L(x) \approx 4.113 + 1.454(x-1)$$

### Critical Points of Single-Variable Functions

A **critical point** of a single-variable function $f(x)$ is a point $c$ in the domain where the function's derivative is either zero or undefined. These are the only points where a local maximum, local minimum, or a saddle point can occur.

#### Types of Critical Points

The type of critical point is determined by analyzing the sign of the first derivative, $f'(x)$, on either side of the point.

* **Local Maximum:**
    The critical point $c$ is a local maximum if the derivative $f'(x)$ changes sign from **positive to negative** as $x$ increases through $c$. This means the function is **increasing** before $c$ and **decreasing** after it.

* **Local Minimum:**
    The critical point $c$ is a local minimum if the derivative $f'(x)$ changes sign from **negative to positive** as $x$ increases through $c$. This means the function is **decreasing** before $c$ and **increasing** after it.

* **Saddle Point (or horizontal inflection point):**
    The critical point $c$ is a saddle point if the derivative $f'(x)$ **does not change sign** as $x$ passes through $c$. This means the function is either increasing on both sides of $c$ or decreasing on both sides.

### Examples

* **Local Maximum:**
    Consider the function $f(x) = -x^2$.
    * $f'(x) = -2x$.
    * The critical point is at $x=0$.
    * For $x < 0$, $f'(x) > 0$ (increasing).
    * For $x > 0$, $f'(x) < 0$ (decreasing).
    * Since the sign of the derivative changes from **+ to -**, $x=0$ is a **local maximum**.

* **Local Minimum:**
    Consider the function $f(x) = x^2$.
    * $f'(x) = 2x$.
    * The critical point is at $x=0$.
    * For $x < 0$, $f'(x) < 0$ (decreasing).
    * For $x > 0$, $f'(x) > 0$ (increasing).
    * Since the sign of the derivative changes from **- to +**, $x=0$ is a **local minimum**.

* **Saddle Point:**
    Consider the function $f(x) = x^3$.
    * $f'(x) = 3x^2$.
    * The critical point is at $x=0$.
    * For $x < 0$, $f'(x) > 0$ (increasing).
    * For $x > 0$, $f'(x) > 0$ (increasing).
    * Since the sign of the derivative **does not change**, $x=0$ is a **saddle point**.