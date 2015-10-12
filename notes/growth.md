# Growth of Functions

This section starts off with the main ideas near the end of section 7.7 but goes on a bit further.

The interest in this section is how functions behave as $x\to\infty$. There are lots of functions that go to infinity: $x$, $x^2$, $e^x$, $x^x$, $\ln(x)$, $\ln(x)^2$ and so on. The question we will focus on in this section is: *How fast do these functions go to infinity*? *Do some of them go to infinity "faster" than others*?

Let us start with a definition:

> We say that a function $g(x)$ **grows faster** than a function $f(x)$, if:
> $$\lim_{x\to\infty}\frac{g(x)}{f(x)} = \infty$$
> We denote this by $$f(x) \ll g(x)$$
>
> We could also instead check that:
> $$\lim_{x\to\infty}\frac{f(x)}{g(x)} = 0$$

Notice that a lot of those quotients will end up being indeterminate forms of the type $\frac{\infty}{\infty}$.

For example, $2x$ is not considered to grow faster than $x$, because $\lim_{x\to \infty}\frac{2x}{x} = 2\neq\infty$. On the other hand, $x^2$ does grow faster than $x$.

Here are some facts about the relative growth of functions:

> $$x^n \ll x^m\textrm{ when }m > n$$
> $$x^n \ll e^x \ll e^{2x} \ll e^{x^n}\textrm{ for all }n$$
> $$\ln(x)^n \ll x^\alpha\textrm{ for all }n,\alpha > 0$$

Let us demonstrate these various assertions. We start with the first, which is easy to see by looking at $\lim_{x\to \infty}\frac{x^m}{x^n} = \lim_{x\to\infty}x^{m-n} = \infty$.

The limits that compare the various exponentials follow from the formula:
$$\frac{e^{f(x)}}{e^{g(x)}} = e^{f(x) - g(x)}$$
So as long as $\lim_{x\to \infty}f(x)-g(x) =\infty$, then $e^{f(x)} \gg e^{g(x)}$.
This helps us show for example that $e^x\ll e^{2x}\ll e^{x^2}\ll e^{x^3}$ and so on.

The hardest comparison is between $x^n$ and $e^x$. Let us work on that now:
$$\lim_{x\to\infty}\frac{e^x}{x^n}$$
As long as $n>0$, we have a $\frac{\infty}{\infty}$ form, and we can apply L'Hopital's rule to get:
$$\lim_{x\to\infty}\frac{e^x}{x^n} = \lim_{x\to\infty}\frac{e^x}{nx^{n-1}}$$

This is again an indeterminate form, but where the $x^n$ power is now of lower degree, but the $e^x$ has remained unchanged. Continuing this way, we will eventually get to a point where we have $e^x$ on the numerator, and a number ($n(n-1)(n-2)\cdots 2\cdot 1$) in the denominator. This limit would then be infinity.

Let us try out some of the remaining comparisons, for instance comparing different exponentials:

> $$\lim_{x\to\infty}\frac{e^{f(x)}}{e^{g(x)}} = e^{\displaystyle \lim_{x\to \infty} f(x) - g(x)}$$
> So $e^{f(x)} \ll e^{g(x)}$ if $\lim_{x\to\infty}f(x) - g(x) = -\infty$ and
> $e^{f(x)} \gg e^{g(x)}$ if $\lim_{x\to\infty}f(x) - g(x) = +\infty$.

Use this to compare $e^x$, $e^{2x}$ and $e^{x^2}$.

Finally, for the logarithm, we use L'Hopital's rule:

$$\lim_{x\to\infty}\frac{\ln(x)}{x^\alpha} = \lim_{x\to\infty}\frac{1/x}{\alpha x^{\alpha-1}} = \lim_{x\to\infty}\frac{1}{\alpha x^\alpha} = 0$$
as long as $\alpha > 0$.
