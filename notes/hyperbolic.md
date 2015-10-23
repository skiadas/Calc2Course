# Hyperbolic Functions

## Reading

Section 7.9

## Problems

Practice Exercises: 7.9 2-4, 6-8, 9-13, 17, 35-38, 41, 42, 45, 61-63, 73, 74

Exercises to turn in (along with those from 7.8): 7.9 8, 44

## Hyperbolic Functions

The hyperbolic functions are special combinations of $e^x$ and $e^{-x}$, and their names are meant to suggest relations to the trigonometric functions.

> The hyperbolic sine, cosine and tangent and secant are defined for all $x$ as:
> $$\sinh(x) = \frac{e^x - e^{-x}}{2}$$
> $$\cosh(x) = \frac{e^x + e^{-x}}{2}$$
> $$\tanh(x) = \frac{\sinh(x)}{\cosh(x)} = \frac{e^x - e^{-x}}{e^x+e^{-x}}$$
> $$\textrm{sech}(x) = \frac{1}{\cosh(x)} = \frac{2}{e^x+e^{-x}}$$

These functions satisfy a number of identities that are similar to the trigonometric identities:

> **Hyperbolic identities**
> $$\sinh(-x) = - \sinh(x)\textrm{ (sinh is an odd function)}$$
> $$\cosh(-x) = \cosh(x)\textrm{ (cosh is an even function)}$$
> $$\cosh^2(x) - \sinh^2(x) = 1$$
> $$\sinh(x+y) = \sinh(x)\cosh(y) + \cosh(x)\sinh(y)$$
> $$\cosh(x+y) = \cosh(x)\cosh(y) + \sinh(x)\sinh(y)$$

The hyperbolic functions have derivative formulas very similar to the trigonometric ones:

> $$\sinh'(x) = \cosh(x)$$
> $$\cosh'(x) = \sinh(x)$$
> $$\tanh'(x) = \textrm{sech}^2(x)$$
> $$\textrm{sech}'(x) = -\textrm{sech}(x)\tanh(x)$$

### Inverse hyperbolic functions

We can also define the inverse hyperbolic functions. For that we need to figure out the ranges for the various hyberbolic functions. There are two approaches we can take to the subject in general: One is to figure out what the derivatives would need to be based on the formula for the derivative of the inverse; the other is to solve the equations $y=f(x)$ for $x$.

We start with the derivative approach:

> $$\sinh^{-1}(x)' = \frac{1}{\sqrt{x^2+1}}$$
> $$\cosh^{-1}(x)' = \frac{1}{\sqrt{x^2-1}}$$
> $$\tanh^{-1}(x)' = \frac{1}{1-x^2}$$
> $$\textrm{sech}^{-1}(x)' = -\frac{1}{x\sqrt{1-x^2}}$$

Let us figure one of these out. The book shows the $\tanh$ case, and we will leave the $\cosh$ and $\textrm{sech}$ cases as exercises for the student. We will work out the $\sinh$ case here:

$$\sinh^{-1}(x)' = \frac{1}{\sinh'\left(\sinh^{-1}(x)\right)} = \frac{1}{\cosh\left(\sinh^{-1}(x)\right)}$$

If we let $t = \sinh^{-1}(x)$, then we would have $\sinh(t) = x$. Now since $\cosh^2(t) - \sinh^2(t) = 1$, so $\cosh^2(t) = 1 + x^2$. Since $\cosh(t)$ is always positive, we get $\cosh(t) = \sqrt{1+x^2}$, and plugging that in the derivative computation we get our result.

Exercise: Do the same work for $\cosh$ and $\textrm{sech}$.

The above formulas suggest some restrictions on the domains of the inverse trigonometric functions. We will arrive at similar conclusions by trying to directly compute the inverse by solving the $y=f(x)$ equations for $x$. First, here are the formulas we would end up with:

> $$\sinh^{-1}(y) = \ln\left(y+\sqrt{y^2+1}\right)\textrm{ for }y\in(-\infty,\infty)$$
> $$\cosh^{-1}(y) = \ln\left(y+\sqrt{y^2-1}\right)\textrm{ for }y > 1$$
> $$\tanh^{-1}(y) = \frac{1}{2}\ln\left(\frac{1+y}{1-y}\right)\textrm{ for }|y| < 1$$
> $$\textrm{sech}^{-1}(y) = \ln\left(\frac{1+\sqrt{1-y^2}}{y}\right)\textrm{ for }0< y\leq 1$$

Let us see how to figure out one of these: Say $y=\sinh(x)$, and we want to solve it for $x$. We start with the definition of $\sinh$:
$$y = \frac{e^x - e^{-x}}{2}$$
We want to express everything in terms of $w=e^x$. We would then have:
$$y = \frac{w - \frac{1}{w}}{2} = \frac{w^2 - 1}{2w}$$
We rewrite this equation as a quadratic in $w$:
$$w^2 -2yw - 1 = 0$$
The solution to this equation would be:
$$w = \frac{2y\pm\sqrt{4y^2 + 4}}{2} = y\pm\sqrt{y^2+1}$$
Since $w$ is an exponential, it must be positive, so we can reject one of the two solutions:
$$e^x = w = y + \sqrt{y^2+1}$$
Taking logarithms we find:
$$\sinh^{-1}(y) = x = \ln\left(y + \sqrt{y^2+1}\right)$$
And there were no restrictions on $y$ along the way.

Exercise: Do the same for the other 3 hyperbolic functions.
