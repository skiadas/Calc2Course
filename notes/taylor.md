# Taylor Polynomials

## Reading

Section 9.4

## Problems

Practice Exercises: 9.4 1, 3, 9, 11, 21, 23, 33

Exercises to turn in: 9.4 6, 24, 36, 48, 52

## Taylor Polynomials

### Taylor Polynomials

Taylor Polynomials stem from a desire to approximate a function near a point via polynomials. We have already seen this idea when we studied derivatives and the idea of linearization:
$$L(x) = f(a) + f'(a)(x-a)$$
This is in effect a polynomial of degree 1 that is fairly similar to the function near $x=a$.

We will extend this idea further:

> The **Taylor Polynomial** of degree $n$ **centered at** $x=a$ is defined as the unique polynomial of degree $n$ that **agrees with $f$ to order $n$ at $x=a$**.
>
> Two functions $f$, $g$ are said to agree to order $n$ at $x=a$ if their derivatives at $x=a$ match up to the $n$-th derivative, so if $f^{(k)}(a) = g^{(k)}(a)$ for all $k=0,\ldots,n$.
>
> The Taylor polynomial has formula:
> $$T_n(x) = f(a) + \frac{f'(a)}{1!}(x-a) + \frac{f''(a)}{2!}(x-a)^2+\cdots + \frac{f^{(n)}}{n!}(x-a)^n$$

We often abreviate this as:
$$T_n(x) = \sum_{j=0}^n \frac{f^{(j)}(a)}{j!}(x-a)^j$$

> The **Maclaurin polynomial** is the Taylor polynomial centered at $x=0$.

Practice:

1. Compute the Maclaurin polynomial of degree $5$ for $f(x) = x^4$. Use it to estimate $e^{0.1}$ and $e=e^1$.
2. Compute the Maclaurin polynomial of degree $4$ for $f(x) = \tan^{-1}x$, and use it to estimate $\frac{\pi}{4} = f(1)$.
3. Compute the Maclaurin polynomial of degree $3$ for $f(x) = \sin x$, and use it to estimate $\sin 0.2$.
4. Compute the Taylor polynomial of degree $4$ for $f(x) = \sqrt x$ at $x=1$, and use it to estimate $\sqrt{1.2}$.
5. Compute the Maclaurin polynomial of degree $5$ for $f(x) = \ln(1+x)$ and use it to estimate $\ln 1.2$.

### The Taylor remainder

In order to use Taylor polynomials effectively, we need a way to measure the error. The first step in that is the Taylor remainder:
$$R_n(x) = f(x) - T_n(x)$$

So the Taylor remainder measures how far the Taylor polynomial is from $f$.

Taylor's theorem gives us a more precise formulation of this remainder:

> **Taylor's Theorem**. If $f^{(n+1)}(x)$ exists and is continuous, then:
> $$R_n(x) = \frac{1}{n!}\int_a^x (x-u)^n f^{(n+1)}(u)du$$

Using Taylor's Theorem, we can obtain the following error bound:

> **Error Bound**. If $f^{(n+1)}(x)$ exists and is continuous, and $K$ is such that $\left|f^{(n+1)}(u)\right|\leq K$ for all $u$ between $a$ and $x$, then:
> $$\left|f(x) - T_n(x)\right| = \left|R_n(x)\right|\leq K \frac{|x-a|^{n+1}}{(n+1)!}$$

Practice: Compute the error bound where $f(x) = \sin(x)$, $a=0$, $n=5$, and at the point $x=0.4$.

### Proof of Taylor's Theorem

Taylor's theorem essentially follows from integration by parts. We start with the following simple observation:

$$f(x) = f(a) + \int_a^x f'(u)du$$
This is valid as long as $f'(u)$ exists and is continuous, and follows straight for the fundamental theorem of Calculus. We can in fact rewrite this as saying
$$f(x) = T_0(x) + R_0(x)$$
where
$$R_0(x) = \int_a^x f'(u)du = \frac{1}{0!}\int_a^x(x-u)^0 f^{(0+1)}(u)du$$
is exactly what is required by Taylor's theorem for $n=0$.

From that point on, we perform integration by parts on the previous term. We use as a second term the constant $1$, which we choose to integrate as **a function of $u$** to $-(x-u)$.
$$\int_a^x f'(u)du = \int_a^x f'(u)\cdot 1 du = \left.-f'(u)(x-u)\right|_a^x + \int_a^x f''(u)(x-u)du = f'(a)(x-a) + \int_a^x f''(u)(x-u)du$$
Putting this back in the original equation we find:
$$f(x) = f(a) + f'(a)(x-a) + \int_a^x f''(u)(x-u)du$$
This is exactly the formula in Taylor's theorem for $n=1$.

To obtain the next iteration of the theorem, we each time integrate the $(x-u)^k$ term:
$$\int_a^x f''(u)(x-u)du = \left.-\frac{1}{2}f''(u)(x-u)^2\right|_a^x + \frac{1}{2}\int_a^x f'''(u)(x-u)^2 du = \frac{1}{2}f''(a)(x-a)^2 + \frac{1}{2}\int_a^x f'''(u)(x-u)^2 du$$

Practice: Try the next step of this iteration.
