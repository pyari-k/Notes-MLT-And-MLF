# Multi-variable Functions

### 1. Line through point $u \in R^d$ along the direction of $v$

A line that passes through a specific point `u` and in the direction of a given vector can be described parametrically. Any point on the line, represented by $x$, is a combination of the initial point and a scaled version of the direction vector.

The equation is:
$$x = u + \alpha\mathbf{v}$$

Where:
* $x$ is any point on the line.
* $u$ is the position vector of a known point on the line.
* $\mathbf{v}$ is the direction vector of the line. It is a non-zero vector.
* $\alpha$ is a scalar parameter (a real number, $\alpha \in R$). By varying $\alpha$, you can reach every point on the line. For $\alpha=0$, you are at point $u$.

### 2. A line through point $u$ and $u'$

When you have two distinct points, $u$ and $u'$, you can find the equation of the line by first determining the direction vector. The vector from $u$ to $u'$ serves as a valid direction vector for the line.

The direction vector, $\mathbf{v}$, is given by the difference between the two points:
$$\mathbf{v} = u' - u$$

Then, you can use either $u$ or $u'$ as the initial point in the first equation. Choosing $u$ as the starting point, the equation of the line is:
$$x = u + \alpha(u' - u)$$

This can also be written in a more symmetrical form:
$$x = (1-\alpha)u + \alpha u'$$

Please note that the last two equations also corresponds to:
equation of a line along `u` and in the direction of `(u' - u)` or equation of a line along `u' - u` and in the direction of `u'`