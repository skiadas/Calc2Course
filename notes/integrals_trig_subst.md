# Trigonometric Substitutions

## Reading

Section 8.3

## Problems

Practice Exercises: 8.3 1, 2, 4, 5, 7, 9, 10, 16, 19, 37, 38, 39

Exercises to turn in (along with 8.2): 8.3 6, 8

## Trigonometric Substitutions

Trigonometric substitutions are used to handle certain integrals containing square roots. There are roughly 3 forms to consider:

> $$\sqrt{a^2 - x^2}$$
> $$\sqrt{x^2 + a^2}$$
> $$\sqrt{x^2 - a^2}$$

Each case is handled by a corresponding substitution, which allows us to eliminate the square root and gives us a trigonometric integral like those discussed in the previous section.

### The sine transform

The sine transform is used to handle integrals involving $\sqrt{a^2 - x^2}$. It is based on the following:

> $$x = a\sin(\theta)$$
> $$dx = a\cos(\theta)d\theta$$
> $$\sqrt{a^2-x^2} = \sqrt{a^2\cos^2(x)} = a\cos(x)$$

where we assume $a > 0$, and we can assume that $\cos(x) > 0$ because the variable $\theta$ is basically restricted to the domain of $\sin^{-1}(x)$.

Let us see this method in action for the integral:
$$\int \frac{x^4}{\sqrt{9-x^2}^5}dx$$

In this case $a=3$, so we set $x=3\sin(\theta)$, or if you prefer $\theta = \sin^{-1}\left(\frac{x}{3}\right)$. The integral them becomes:
$$\int \frac{3^4\sin^4(\theta)}{\left(3\cos(\theta)\right)^5} 3\cos(\theta)d\theta = \int \frac{1}{3}\tan^4(\theta)d\theta$$

We would then compute this integral using the methods shown in the section on trigonometric integrals.

### The tangent transform

The tangent transform is used for integrals of the form $\sqrt{a^2+x^2}$. It is based on:

> $$x = a\tan(\theta)$$
> $$dx = a\sec^2(\theta)d\theta$$
> $$\sqrt{x^2+a^2} = \sqrt{a^2\sec^2(\theta)} = a\sec(\theta)$$

For example, if we had to deal with $\int\sqrt{4x^2+9}^3dx$, we would do $x = \frac{3}{2}\tan(\theta)$. Then $\sqrt{4x^2+9} = 3\sec(\theta)$, so the integral becomes:
$$\int 3^5\sec^5(\theta)\frac{3}{2}\sec^2(\theta)d\theta = \frac{3^6}{2}\int\sec^7(\theta)d\theta$$

### The secant transform

The secant transform is used for integrals of the form $\sqrt{a^2-x^2}$. It is based on:

> $$x = a\sec(\theta)$$
> $$dx = a\sec(\theta)\tan(\theta)d\theta$$
> $$\sqrt{x^2-a^2} = \sqrt{a^2\tan^2(\theta)} = a\tan(\theta)$$

For example, consider the integral $\int \frac{x^2}{\sqrt{x^2-4}}dx$. We would let $x=2\sec(\theta)$, and then we would have:
$$\int \frac{4\sec^2(\theta)}{2\tan(\theta)}2\sec(\theta)\tan(\theta)d\theta = 4\int\sec^3(\theta)d\theta$$

### Completing the square

Cases where the quantity under the square root is a general quadratic can always be brought into one of the forms above via a method of computing the square. Here is an example:
$$\int x^2\sqrt{x^2 -4x + 5}$$

We start with by rewriting:
$$x^2-4x+5 = x^2 - 2\cdot 2x + 2^2 + 1 = (x-2)^2 + 1$$

So the role of $x$ is played by $x-2$. And $a=1$, so we would do a substitution:
$$x - 2 = \tan(\theta)$$
$$dx = \sec(\theta)\tan(\theta)d\theta$$
$$(x-2)^2 + 1 = \sec^2(\theta)$$

The integral therefore becomes:
$$\int \left(2 + \tan(\theta)\right)^2\sqrt{\sec^2(\theta)}\sec(\theta)\tan(\theta)d\theta = \int \left(2 + \tan(\theta)\right)^2\sec^2(\theta)\tan(\theta)d\theta$$

