## Derivative - Definition (First Principles)

The formula for the **derivative** of a function \( f(x) \) at a point \( x^* \) is given by:

\[
f'(x^*) = \lim_{x \to x^*} \frac{f(x) - f(x^*)}{x - x^*}
\]

---

## Linear Approximation

The **definition of the derivative** of a function \( f(x) \) at a point \( x^* \) is:

\[
f'(x^*) = \lim_{x \to x^*} \frac{f(x) - f(x^*)}{x - x^*}
\]

When \( x \) is very close to \( x^* \), the fraction \( \frac{f(x) - f(x^*)}{x - x^*} \) is approximately equal to \( f'(x^*) \). We can express this as:

\[
\frac{f(x) - f(x^*)}{x - x^*} \approx f'(x^*)
\]

This implies:

\[
f(x) \approx f(x^*) + f'(x^*)(x - x^*)
\]

We define the linear approximation, denoted as \( L(x) \), using this approximation:

\[
L(x) = f(x^*) + f'(x^*)(x - x^*)
\]

> **Note:** This formula represents the equation of the tangent line to the function \( f(x) \) at the point \( (x^*, f(x^*)) \). For values of \( x \) close to \( x^* \), the tangent line provides a good approximation of the function's value.

---

## Linear Approximation Examples

### Example 1: Linear Approximation of \( (1+x)^r \) near \( x = 0 \)

Let \( f(x) = (1+x)^r \). We want to find its linear approximation around \( x^* = 0 \).

1. **Function value at** \( x = 0 \):

\[
f(0) = (1+0)^r = 1^r = 1
\]

2. **Derivative**:

\[
f'(x) = \frac{d}{dx}(1+x)^r = r(1+x)^{r-1}
\]

3. **Evaluate at** \( x = 0 \):

\[
f'(0) = r(1+0)^{r-1} = r
\]

4. **Linear approximation**:

\[
L(x) = f(0) + f'(0)(x - 0) = 1 + rx
\]

So, the linear approximation for \( (1+x)^r \) when \( x \) is close to 0 is:

\[
(1+x)^r \approx 1 + rx
\]

This is a very common and useful approximation, especially for small values of \( x \).

---

### Example 2: Approximating \( 0.99^7 \) using Linear Approximation

We want to approximate \( 0.99^7 \). This can be rewritten as \( (1 - 0.01)^7 \), which fits the form \( (1+x)^r \), where:

- \( x = -0.01 \)
- \( r = 7 \)

Using the formula from Example 1:

\[
(1+x)^r \approx 1 + rx
\]

Substitute the values:

\[
0.99^7 = (1 - 0.01)^7 \approx 1 + 7(-0.01) = 1 - 0.07 = 0.93
\]

Let’s compare this to the exact value:

\[
0.99^7 \approx 0.932065355
\]

As you can see, the linear approximation \( 0.93 \) is a very good estimate for \( 0.99^7 \).
