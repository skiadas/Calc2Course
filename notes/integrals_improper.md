# Improper Integrals

## Reading

Section 8.6

## Problems

Practice Exercises: 8.6 1, 2, 3, 4, 9, 11, 19, 21, 27, 37, 41, 47, 53, 61

Exercises to turn in: 8.6 12, 16, 26, 38

Challenge: 86-89, 99, 100

## Improper Integrals

There are two types of "improper integrals":

- Integrals where at least one of the endpoints is $\pm\infty$.
- Integrals that cross over a point where the integrand becomes infinite.

We will consider both cases, starting with the case of infinite endpoints.

### Improper Integrals at infinity

So integrals in this category will fall into one of the following forms:

> $$\int_a^\infty f(t) dt$$
> $$\int_{-\infty}^a f(t) dt$$
> $$\int_{-\infty}^\infty f(t) dt$$

The idea in each of these cases is simple: We interpret the integral as a limit of definite integrals with finite endpoints, as one of those endpoints goes to infinity. So:

> $$\int_a^\infty f(t)dt = \lim_{R\to\infty}\int_a^R f(t)dt$$
> $$\int_{-\infty}^a f(t)dt = \lim_{R\to -\infty}\int_R^a f(t)dt$$
> $$\int_{-\infty}^\infty f(t) dt = \int_{-\infty}^0 f(t) dt + \int_0^\infty f(t) dt$$

Here is perhaps the most elementary example:
$$\int_0^\infty e^{-x}dx$$
In order to compute it, we would first compute:
$$\int_0^R e^{-x}dx = \left.\left(-e^{-x}\right)\right|_0^R = 1-e^{-R}$$
We then take the limit as $R\to\infty$:
$$\int_0^\infty e^{-x}dx = \lim_{R\to\infty}\int_0^R e^{-x}dx = \lim_{R\to\infty}1-e^{-R} = 1-e^{-\infty} = 1$$

So in this case the limit exists and is a finite number. We then say that the integral **converges**. It is worth pondering that for a minute: The area represented by this integral spans all the way to infinity. Yet it is actually a finite amount, namely $1$.

Let us look at another example:
$$\int_0^\infty\frac{1}{x}dx = \lim_{R\to\infty}\int_1^R\frac{1}{x}dx = \lim_{R\to\infty}\ln R = \infty$$
So in this case we say that the integral **diverges**.

This last example generalizes:

> **p-integral at infinity**. For $a > 0$, we have:
>
> - $\int_a^\infty \frac{1}{x^p}dx = \frac{a^{1-p}}{p-1}$ if $p > 1$.
> - $\int_a^\infty \frac{1}{x^p}dx$ diverges if $p <= 1$.

So the case of $\frac{1}{x}$ is kind of an edge case: functions that are any "smaller" ($p > 1$) go to $0$ fast enough as $x$ approaches infinity to have their integral converge, functions that are any like $\frac{1}{x}$ or "bigger" ($p<=1$) go to $0$ too slow and end up accumulating too much area, resulting in a divergent integral.

Exercise: Prove the above theorem.

Here is another general example:

> The integral
> $$\int_0^\infty x^n e^{-x}dx$$
> converges for all natural numbers $n$, and equals $n! = n(n-1)(n-2)\cdots 2\cdot 1$.

Let us start with some base cases.
$$\int_0^\infty xe^{-x}dx = \lim_{R\to\infty}\int_0^R xe^{-x}dx$$
Now we do integration by parts:
$$\int_0^R xe^{-x}dx = \left.-xe^{-x}\right|_0^R + \int_0^Re^{-x}dx=-Re^{-R} + \int_0^Re^{-x}dx$$
Now taking limits as $R\to\infty$, we have the integral we already did before, whose value is $1$, and also:
$$\lim_{R\to\infty}Re^{-R} = \lim_{R\to\infty}\frac{R}{e^R} = \lim_{R\to\infty}\frac{1}{e^R} = 0$$

Let's consider the more general case:
$$\int_0^R x^ne^{-x} = -\left.(x^ne^{-x})\right|_0^R + \int_0^R nx^{n-1}e^{-x}dx = -R^ne^{-R} + n\int_0^R x^{n-1}e^{-x}dx$$

We now want to take limits at infinity on both sides of this equation. The key observation would be that:
$$\lim_{R\to\infty}\frac{R^n}{e^R} = 0$$
So we have in general:
$$\int_0^\infty x^ne^{-x}dx = n\int_0^\infty x^{n-1}e^{-x}dx$$
By using this formula repeatedly, we would end up with:
$$\int_0^\infty x^ne^{-x}dx = n(n-1)\cdots \cdot 2\cdot 1$$

There are a lot of interesting functions that can be defined as improper integrals. For instance the Gamma function:

> Gamma function
> $$\Gamma(t) = \int_0^\infty x^{t - 1} e^{-x}dx$$

This turns out to converge as long as $t > 0$, and we already have seen its value when $t$ is an integer. It is a differentiable function with a number of interesting properties, whose examination is likely mostly beyond the scope of this course.

### Improper Integrals at finite points

Instead of having $x$ go to infinity, we now consider cases where the value of the function goes to infinity, but at a finite point. There are many variations on this:

> Improper Integrals of the form:
> $$\int_a^b f(x)dx$$
> where we assume that $a < b$ and:
>
> - $\lim_{x\to b^-}f(x) = \pm\infty$, or
> - $\lim_{x\to a^+}f(x) = \pm\infty$, or
> - $f$ becomes infinity at some point inbetween $a$ and $b$.

We approach such cases in similar vein as before: We integrate up to a point before the bad part, then take the limit. And for the third case we break the integral in two separate integrals belonging to the other two cases.

An example will make this clearer:
$$\int_0^1\frac{1}{\sqrt{x}}dx$$

So in this case the function that we are trying to integrate becomes infinity at $0$. We therefore would instead compute:
$$\int_b^1\frac{1}{\sqrt{x}}dx$$
for some generic $b>0$ that is close to $0$. We will then take the limit as $b\to 0$. So effectively we say that we define:
> $$\int_0^1\frac{1}{\sqrt{x}}dx = \lim_{b\to 0^+}\int_b^1\frac{1}{\sqrt{x}}dx$$

Let us now compute this integral:
$$\int_b^1\frac{1}{\sqrt{x}}dx = \int_b^1 x^{-1/2}dx = \left. 2 x^{1/2}\right|_b^1 = 2\left(1 - b^{1/2}\right)$$
We now take the limit as $b\to 0^+$, resulting in a limit of $2$. So we have:
$$\int_0^1\frac{1}{\sqrt{x}}dx = 2$$

We can generalize this to various powers:

> **p-integral at infinity**. For $a > 0$, we have:
>
> - $\int_0^a \frac{1}{x^p}dx = \frac{a^{1-p}}{1-p}$ if $p < 1$.
> - $\int_0^a \frac{1}{x^p}dx$ diverges if $p >= 1$.

Exercise: Show this!

### The Comparison Test for Improper Integrals

When dealing with improper integrals, some times explicitly computing the integral is not actually possible. In such cases, it is often worth it to simply know that it converges, i.e. so that there is in fact a number corresponding to it. The comparison test helps with that:

> **Comparison Test for Improper Integrals**
>
> If $f(x)\geq g(x)\geq 0$ for $x \geq a$, then:
>
> - If $\int_a^\infty f(x)dx$ converges, then $\int_a^\infty g(x)dx$ also converges.
> - If $\int_a^\infty g(x)dx$ diverges, then $\int_a^\infty f(x)dx$ also diverges.
>
> Similar results hold for improper integrals with infinite discontinuities at endpoints.

Let us look at an important example of this, which we discussed earlier as the Gamma function:

> The integral
> $$\int_0^\infty x^{t-1}e^{-x}dx$$
> converges for all $t > 0$.

This integral is interesting, among other reasons, because it actually exhibits both types of improper-ness: One of the endpoints is infinity, and the other endpoint may be a discontinuity of the function (as the $x^{t-1}$ might actually be a negative power if $0 < t < 1$).

There are two very different cases to consider: If $t\geq 1$ and if $0 < t < 1$. And in either case, we will want to further break our integral as the sum of two integrals:
$$\int_0^\infty x^{t-1}e^{-x}dx = \int_0^1 x^{t-1}e^{-x}dx + \int_1^\infty x^{t-1}e^{-x}dx$$

Now let us examine the case where $t\geq 1$. Then the first integral is just a normal integral of a continuous function, so it is going to be some (unknown) number. But it is definitely going to converge.

The second integral requires more work: The idea is simple however. Let us pick a natural number $n \geq t-1$. Then we have for $x \geq 1$ that:
$$0 \leq x^{t-1}e^{-x}\leq x^n e^{-x}$$
This is now set up perfectly for use of the comparison test. We know from our earlier work that when $n$ is an integer we can actually use integration by parts to directly compute:
$$\int_1^\infty x^n e^{-x}dx$$
and it converged to a number. Therefore, by the comparison theorem, we have that the integral:
$$\int_1^\infty x^{t-1} e^{-x}dx$$
also converges.

The reason we had to break this in two integrals is that the fact that $x^{t-1}\leq x^n$ only holds if $x\geq 1$.

Now let us consider the case where $0 < t < 1$. In this case $t-1$ is a negative power. We again look at the two integrals, now starting with:
$$\int_1^\infty x^{t-1} e^{-x}dx$$
Since that power is negative, we have that $x^{t-1}\leq 1$ for all $x\geq 1$. So we can compare that integral with the integral:
$$\int_1^\infty e^{-x}dx$$
which we know converges. Then since $x^{t-1}e^{-x}\leq e^{-x}$ when $x\geq 1$, we have by the comparison test that the integral $\int_1^\infty x^{t-1} e^{-x}dx$ would also have to converge.

We are now left with showing that when $0 < t < 1$ then the integral $\int_0^1 x^{t-1}e^{-x}dx$ converges. We can do this by comparing it to the integral $\int_0^1 x^{t-1}dx$, since when $x\geq 0$ then $e^{-x}\leq e^0 = 1$, and so $x^{t-1}e^{-x}\leq x^{t-1}$. So our integral would converge if the integral
$$\int_0^1 x^{t-1}dx$$
converges. This integral has the $p$-integral form we discussed earlier, with $p=1-t$. Those integrals converge when $p < 1$, or $1-t < 1$, i.e. $t > 0$. This is indeed the case.
