# Review of Calculus 1 Concepts

This will be a review of topics and concepts from Calculus 1, along with a list of suggested problems.

## Practice Problems

- 2.4 4, 2.8 7
- 3.1 26, 3.2 17, 3.3 18, 3.5 26, 3.6 28, 3.7 44
- 4.1 19, 4.2 8, 4.2 32, 4.4 38, 4.6 9, 4.8 17
- 5.2 9, 5.2 44, 5.3 11, 5.3 38, 5.4 13, 5.4 16, 5.6 30, 5.6 71

## Limits and Continuity

> The **limit** of a function $f(x)$ at a point $a$, denoted:
> $$\lim_{x\to a}f(x)$$
> is the number that the values $f(x)$ approach as the points $x$ get closer and closer to (but are distinct from) the point $a$.

This is the important thing to remember, that the limit talks about the behavior of the function *near a point*, and *not at the point*.

When the behavior near a point agrees with the value at the point, we have continuity:

> The function $f(x)$ is **continuous** at the point $a$ exactly when the limit at $a$ agrees with the value there:
> $$\lim_{x\to a}f(x) = f(a)$$

Intuitively, the value at the point $a$ is what is *expected* by looking at the behavior of the function nearby.

> Various types of discontinuities:
>
> - Removable discontinuity: The value $f(a)$ is simply not defined, but the limit exists. We can fix the discontinuity by defining the value $f(a)$ via the limit.
> - Jump discontinuity: The *left limit* and the *right limit* both exist but differ.
> - Infinite discontinuity: The left limit and/or right limit are infinite.

An important property of continuous functions is the **intermediate value theorem**:

> If $f(x)$ is a continuous function on an interval $[a,b]$, and $L$ is a value anywhere between $f(a)$ and $f(b)$, then $L$ can be obtained from $f$, i.e. there is a value $c\in[a,b]$ such that $f(c) = L$.

This has tremendous consequences, amongst them the fact that the square roots of numbers exist, by applying the intermediate value theorem on power functions.

![Proof that square root of 2 exists (IVT)](images/squareroot2.png)

## Derivatives

> The **derivative** of a function $f(x)$ at a point $a$ is defined as a *limit of slopes of secant lines*:
> $$\frac{df}{dx} = f'(x) = \lim_{x\to a} \frac{f(x) - f(a)}{x - a} = \lim_{h\to 0}\frac{f(a+h) - f(a)}{h}$$

When computing derivatives, we typically rely on a number of rules:

> **Derivative Rules:**
>
> $$(f\pm g)'(a) = f'(a) \pm g'(a)$$
> $$(cf)'(a) = cf'(a)$$
> $$(fg)'(a) = f'(a)g(a) + f(a)g'(a)$$
> $$\left(\frac{f}{g}\right)'(a) = \frac{f'(a)g(a) - f(a)g'(a)}{g^2(a)}$$
> $$\left(x^n\right)' = nx^{n-1}$$
> $$\sin'(x) = \cos(x),\quad \cos'(x) = -\sin(x)$$
> $$\tan'(x) = \sec^2(x),\quad \sec'(x) = \sec(x)\tan(x)$$
> $$\left(f(g(x))\right)' = f'(g(x))g'(x)$$

Derivatives tell us about the behavior of a function near a point, approximated as a line, namely the **tangent line**:

> **Tangent Line** for $f(x)$ at a point $x=a$:
> $$y - f(a) = f'(a)(x-a)$$

This can in particular be used to obtain an approximation for $f(x)$ near a point $a$:

> Approximation for $x=a$:
> $$f(x) \approx f(a) + f'(a)(x-a)$$

One of the main applications of derivatives is in locating **maxima and minima for functions**:

> If $f(x)$ is continuous on $[a,b]$, then:
>
> - There is a maximum and a minimum for $f(x)$ on $[a, b]$
> - Those extremal values occur at one of the following:
>
>     - the endpoints $a$, $b$
>     - points where $f'(c) = 0$
>     - points, if any, where $f'(c)$ does not exist.
>
>     These last two categories are called **critical points**

The mean value theorem for derivatives is one of the main results, with important consequences:

> **Mean Value Theorem**
>
> If $f$ is continuous on $[a, b]$ and differentiable on $(a, b)$, then there is a point $c\in (a, b)$ where:
> $$f'(c) = \frac{f(b) - f(a)}{b - a}$$

> Consequences of MVT:
>
> - If $f'(x) > 0$ on an open interval, then $f$ is increasing there
> - If $f'(x) < 0$ on an open interval, then $f$ is decreasing there
> - If $f'(x) = 0$ on an open interval, then $f$ is constant there

### Integrals

The **integral** of a continuous function $f(x)$ on an interval $[a, b]$ is intuitively defined as the area between the x-axis and the function. A formal equation usually looks something like this:

> $$\int_a^b f(x)dx = \lim_{n\to\infty}\sum_{i=1}^n f(x_i^*)\Delta x_i$$

Integrals are often computed via the **antiderivatives**, based on the fundamental theorem of Calculus:

> **Fundamental Theorem of Calculus**
>
> 1. If $f(x)$ is continuous on $[a, b]$, and $F(x)$ is a function such that $F'(x) = f(x)$, then:
>     $$\int_a^b f(x) dx = F(b) - F(a)$$
> 2. If $f(x)$ is continuous on $[a, b]$ and we defined the integral function:
>     $$F(x) = \int_a^x f(t)dt$$
>     is differentiable and $F'(x) = f(x)$.

One of the key techniques for computing integrals, and antiderivatives, is the substitution method:

> **Substitution Method**:
>
> - If $F'(x) = f(x)$, then $F(g(u))$ is an antiderivative for $f(g(u))g'(u)$.
> - $\displaystyle\int_a^b f(g(u))g'(u)du = \int_{g(a)}^{g(b)}f(u)du$.
