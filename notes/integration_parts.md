# Integration by Parts

## Reading

Section 8.1

## Problems

Practice Exercises: 8.1 9, 11, 13, 16, 27, 28, 33, 41, 42, 43, 51, 53, 55, 57, 67, 71

Exercises to turn in: 8.1 10, 14, 36, 38, 52

## Integration by Parts

The overall theme of this chapter is various techniques of integration, that are used to reach the more complex integrals. We have already seen one such technique, the $u$-substitution:

> **u-substitution**
>
> $$\int f(g(x))g'(x)dx = \int f(u)du$$
> where $u = g(x)$.
>
> $$\int_a^b f(g(x))g'(x)dx = \int_{g(a)}^{g(b)} f(u)du$$
>
> This follows directly from the chain rule: If $F'(u) = f(u)$, then $F(g(x))' = F'(g(x))g'(x) = f(g(x))g'(x)$ and we have an antiderivative for $f(g(x))g'(x)$.

Just as the $u$-substitution is based on the chain rule, the technique we will see here is based on another derivative rule, namely the product rule:

> $$\left(u(x)v(x)\right)' = u'(x) v(x) + u(x) v'(x)$$

If we integrate both sides, we get:

> $$u(x)v(x) = \int u'(x) v(x) + \int u(x) v'(x)$$

Moving things around leads us to:

> **Integration by parts**
>
> $$\int u(x) v'(x) dx = u(x) v(x) - \int u'(x) v(x) dx$$
> $$\int_a^b u(x) v'(x) dx = \left.\left(u(x) v(x)\right)\right|_a^b - \int_a^b u'(x) v(x) dx$$
>

We use this method when:

- Our integrand can be naturally written as the product of a function $u(x)$ and the derivative of a function $v(x)$, and
- Integrating $\int_a^b u'(x) v(x) dx$ is easier than $\int_a^b u(x) v'(x) dx$.

Let us look at an example. Say we want to compute:
$$\int_0^\pi x\sin(x)dx$$

Here we have two terms, $x$ and $\sin(x)$. We will make one of them the $u(x)$ and the other the $v'(x)$. Let's let $u(x) = x$ and $v(x) = -\cos(x)$. Then $v'(x) = \sin(x)$. So we have:
$$\int_0^\pi x\sin(x)dx = \left.\left(x(-\cos(x))\right)\right|_0^\pi - \int_0^\pi (x)'(-\cos(x))dx = -\pi\cos(\pi) + 0 \cos(0)  + \int_0^\pi \cos(x)dx$$

Now the $x$ is gone and all we have left is integrating the cosine, which is easy to do:
$$\int_0^\pi\cos(x)dx = \sin(\pi) - \sin(0) = 0 - 0 = 0$$

So the overall integral is:
$$-\pi\cos(\pi) + 0 \cos(0)  + 0 = \pi$$

Exercise: Use the same idea to compute $\int_0^1 x e^x dx$ and $\int_0^1 xe^{-x}dx$.

In general, this allows us to deal with any situation where we have the product of a polynomial with some function like $e^x$ or $\cos(x)$ whose integral is easy to work with (so we can think of them as the $v'$ part). Then integration by parts gives us a problem where the polynomial involved has a lower degree.

### Special cases

There some special cases where we use integration by parts even though we don't have two terms. A good example is the integral $\int\ln(x)dx$, which you can see in the book. We will do a similar example here, namely:
$$\int \tan^{-1}(x)dx$$

The idea is this: we can always artificially create a $v'(x)$ by using the number $1$, so $v(x) = x$ and $v'(x) = 1$. This can be beneficial if differentiating the remaining expression makes things easier. So in this case we would do:
$$\int \tan^{-1}(x)\cdot 1 dx = \int \tan^{-1}(x)\cdot (x)' dx = x\tan^{-1}(x) - \int\left(\tan^{-1}(x)\right)' x dx = x\tan^{-1}(x) - \int \frac{x}{1+x^2}dx$$

The advantage we gained is that we do not have to worry about $\tan^{-1}$ any more, it went away when we differentiated. In the process however we obtained an extra $x$ in the numerator. We are now left with computing this new integral, which we can do with a $u=1+x^2$ substitution:
$$\int \frac{x}{1+x^2}dx = \frac{1}{2} \int \frac{1}{u}du = \frac{1}{2} \ln(u) = \frac{1}{2} \ln\left(1+x^2\right)$$

So overall we have:
$$\int \tan^{-1}(x)dx = x\tan^{-1}(x) - \frac{1}{2}\ln\left(1+x^2\right)$$

Compute the derivative of this expression and verify that you do end up with $\tan^{-1}(x)$.
