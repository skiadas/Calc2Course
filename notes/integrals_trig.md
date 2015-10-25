# Trigonometric Integrals

## Reading

Section 8.2

## Problems

Practice Exercises: 8.2 3, 5, 9, 11, 13, 15, 17, 23, 28, 29, 49, 33, 50, 64, 66, 67, 69

Exercises to turn in (along with 8.3): 8.2 14, 16

Challenge (optional): 8.2 78, 79

## Trigonometric Integrals

In this section we will consider the general problem of solving integrals of the form:

> $$\int \sin^m(x)\cos^n(x)dx$$

The book also discusses integrals involving tangents and secants, with similar methods for their solution. See the outline on the sidenote of page 422.

We have 2 distinct cases to consider:

### Case of one odd power

If one of the powers involved is odd, then we can set up the integral for a $u$-substitution:

> $$\int \sin^{2k+1}(x)\cos^n(x)dx = \int\left(\sin^2(x)\right)^k\cos^n(x)\sin(x)dx =$$
> $$\int\left(1-\cos^2(x)\right)^k\cos^n(x)\left(\sin(x)dx\right) = -\int\left(1-u^2\right)^k u^n du$$
> where $u = \cos(x)$, $du = -\sin(x)dx$.

and

> $$\int \sin^m(x)\cos^{2k+1}(x)dx = \int\sin^m(x)\left(\cos^2(x)\right)^k\cos(x)dx =$$
> $$\int\sin^m(x)\left(1-\sin^2(x)\right)^k\left(\cos(x)dx\right) = \int u^m\left(1-u^2\right)^k du$$
> where $u = \sin(x)$, $du = \cos(x)dx$.

For example, suppose we look at $\sin^5(x)$, i.e. $m=5$ and $n=0$. Then we have:

$$\int \sin^5(x)dx = \int \left(1-\cos^2(x)\right)^2 \sin(x)dx = -\int \left(1-u^2\right)^2du$$
where $u=\cos(x)$. Expanding that polynomial gives us:
$$-\int 1 - 2u^2+u^4du = -u + \frac{2}{3}u^3 - \frac{1}{5}u^5 + C$$
Finally, we plug in $u=\cos(x)$:
$$\int \sin^5(x)dx = -\cos(x) + \frac{2}{3}\cos^3(x) - \frac{1}{5}\cos^5(x) + C$$

Practice: Compute $\int \sin^3(x)\cos^2(x)dx$.

### Case of both powers even

There are two ways to approach these integrals. one is to use the double-angle formulas:

> $$\cos(2x) = \cos^2(x) - \sin^2(x) = 2\cos^2(x) - 1 = 1 - 2\sin^2(x)$$
> $$\cos^2(x) = \frac{1 + \cos(2x)}{2}$$
> $$\sin^2(x) = \frac{1 - \cos(2x)}{2}$$

This gives rise to an integral of trigonometric functions of smaller degrees, albeit involving an angle of $2x$ rather than $x$ (so be careful when you do $u=\cos(2x)$!!).

For example, let us work out the integral $\int \sin^2(x)\cos^2(x)dx$ using this method:

$$\int \sin^2(x)\cos^2(x)dx = \int \frac{1 - \cos(2x)}{2} \frac{1 + \cos(2x)}{2}dx = \frac{1}{4} \int 1 - \cos^2(2x)dx = \frac{1}{4} x - \frac{1}{4}\int\cos^2(2x)dx$$

We again have a square of a cosine, so we use the double angle formula a second time:
$$\int\cos^2(2x)dx = \int \frac{1 + \cos(4x)}{2}dx = \frac{1}{2}x + \frac{1}{8}\sin(4x) + C$$

Substituting back in the original equation we get:
$$\int \sin^2(x)\cos^2(x)dx = \frac{1}{4}x -\frac{1}{8}x - \frac{1}{32}\sin(4x) + C = \frac{1}{8}x - \frac{1}{32}\sin(4x) + C$$

An alternative way for these integrals is to convert them all into integrals of various powers of $\sin^m(x)$ (or equivalently of $\cos^m(x)$). So for our example we would do:

$$\int \sin^2(x)\cos^2(x)dx = \int \sin^2(x)\left(1-\sin^2(x)\right)dx = \int \sin^2(x) - \sin^4(x) dx$$

We would then use the following reduction formulas:

> $$\int \sin^n(x) dx = - \frac{1}{n} \sin^{n-1}(x)\cos(x) + \frac{n-1}{n}\int \sin^{n-2}(x)dx$$
> $$\int \cos^n(x) dx = \frac{1}{n} \cos^{n-1}(x)\sin(x) + \frac{n-1}{n}\int \cos^{n-2}(x) dx$$

This brings it all down to the integrals $\sin^2(x)$, $\cos^2(x)$, $\sin(x)$, $\cos(x)$.

The above reduction formulas can be proven using integration by parts, and are left as exercises.

### Integral of secant power

In this section we deduce the useful formula:

> $$\int \sec^n(x)dx= \frac{1}{m-1}\tan(x)\sec^{n-2}(x) + \frac{n-2}{n-1}\int\sec^{n-2}(x)dx$$

This is a somewhat tricky integration by parts:

$$\int \sec^n(x)dx = \int\sec^{n-2}(x)\sec^2(x)dx = \int\sec^{n-2}(x)\tan'(x)dx=$$
$$=\sec^{n-2}(x)\tan(x) - (n-2)\int\sec^{n-3}(x)\sec'(x)\tan(x)dx =$$
$$=\sec^{n-2}(x)\tan(x) - (n-2)\int\sec^{n-3}(x)\sec(x)\tan^2(x)dx =$$
$$=\sec^{n-2}(x)\tan(x) - (n-2)\int\sec^{n-2}(x)\left(\sec^2(x) - 1\right)dx =$$
$$=\sec^{n-2}(x)\tan(x) - (n-2)\int\sec^{n}(x) + (n-2)\int\sec^{n-2}(x)dx$$

If we move the middle term to the left side, we get:

$$(n-1)\int\sec^n(x)dx = \sec^{n-2}(x)\tan(x) + (n-2)\int\sec^{n-2}(x)dx$$

Dividing by $n-1$ gives us the desired formula.

A similar method gives us a reduction formula for tangent (left as exercise):

> $$\int\tan^n(x)dx = \frac{1}{n-1}\tan^{n-1}(x) - \int\tan^{n-2}(x)dx$$
