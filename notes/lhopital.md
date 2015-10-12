# L'Hopital's Rule

## Reading

Section 7.7

## Problems

Practice Exercises: 7.7 1-4, 6-7, 9-10, 14-16, 18, 19, 25, 27, 29, 47-48, 55

Exercises to turn in (along with those from 7.8): 26, 46, 56, 58

## L'Hopital's Rule

L'Hopital's Rule is a powerful result that allows us to compute some difficult integrals that belong to the indeterminate forms.

> **Indeterminate Forms**
>
> The following expressions, thought of as expressions of functions that tend to those values, are *indeterminate*, meaning that their value depends on the particular situation:
>
> $\frac{0}{0}$, $\frac{\pm\infty}{\pm\infty}$, $0\cdot \infty$, $1^{\pm\infty}$, $0^0$, $\infty - \infty$

For example, consider the silly expression $\frac{2x}{x}$. If we take the limit of numerator and denominator, we get $0$, yet the quotient goes to $2$. If we had a different number than $3$ in the numerator, the answer would have been different. So the quotient of two functions that each go to $0$ really depends on more information, and could be any number depending on what the functions are.

Take a moment to intuitively think about why the other expressions can have similar problems.

In general, L'Hopital's rule allows us to deal with such situations. Before we do so however, let us think of another approach to some of these limits:

> A $\frac{0}{0}$ limit can often be thought of as a derivative, or a quotient of two derivatives, using the definition of a derivative as a limit:
>
> $$\lim_{x\to a}\frac{f(x) - f(a)}{x-a} = f'(a)$$
> and
> $$\lim_{x\to a}\frac{f(x) - f(a)}{g(x) - g(a)} = \lim_{x\to a}\frac{\displaystyle\frac{f(x)-f(a)}{x-a}}{\displaystyle\frac{g(x)-g(a)}{x-a}} = \frac{\displaystyle\lim_{x\to a}\frac{f(x)-f(a)}{x-a}}{\displaystyle\lim_{x\to a}\frac{g(x)-g(a)}{x-a}} = \frac{f'(a)}{g'(a)}$$

For instance, consider the problem of finding $\lim_{x\to 0}\frac{e^x-1}{x}$. This is a good example of a limit that looks just like the derivative of a function. In fact, if $f(x) = e^x$ then what we are looking at is:
$$\lim_{x\to 0}\frac{f(x) - f(0)}{x-0}$$
So this limit must equal the derivative of the function $e^x$ at $x=0$, which just so happens to be $e^0=1$. So the limit would be $1$.

Another example would be the expression $\displaystyle\lim_{x\to 1}\frac{\ln(x)}{x-1}$. Again what we are looking at is the very definition of the derivative of the function $\ln(x)$ at the point $x=1$, which is $\frac{1}{x}$ at $x=1$, or $\frac{1}{1} = 1$.

Finally, let's consider some quotients, like:
$$\lim_{x\to 0}\frac{\ln(1+2x)}{e^{3x} - 1}$$
We can divide both numerator and denominator by an $x$:
$$\lim_{x\to 0}\frac{\displaystyle\frac{\ln(1+2x)}{x}}{\displaystyle\frac{e^{3x} - 1}{x}} = \frac{\lim_{x\to 0}\displaystyle\frac{\ln(1+2x)}{x}}{\lim_{x\to 0}\displaystyle\frac{e^{3x} - 1}{x}}$$
Now we see that at the numerator we have the derivative of the function $f(x) = \ln(1+2x)$ at the point $x=0$. The value of that is $\frac{2}{1+2\cdot 0} = 2$.

Now on the denominator we have the derivative of the function $g(x)=e^{3x}$ at $x=0$. That would be $3e^{3\cdot 0} = 3$.

So the overall limit would be $\frac{2}{3}$.

L'Hopital's Rule does something somewhat similar:

> **L'Hopital's Rule**
>
> Suppose $f(x)$, $g(x)$ are functions defined around $x=a$, and such that the limits:
> $$\lim_{x\to a} f(x)\textrm{ and }\lim_{x\to a} g(x)$$
> exist and are either both $0$ or both $\pm\infty$. And suppose further that the limit
> $$\lim_{x\to a}\frac{f'(x)}{g'(x)}$$
> exists. Then we have:
> $$\lim_{x\to a} \frac{f(x)}{g(x)} = \lim_{x\to a}\frac{f'(x)}{g'(x)}$$

It is really important that you check the *hypotheses* of the theorem before trying to use its result.

Let's employ the theorem in the example we just did:
$$\lim_{x\to 0}\frac{\ln(1+2x)}{e^{3x} - 1}$$
The individual limits of numerator and denominator are both $0$. So we compute their derivatives:
$$\frac{f'(x)}{g'(x)} = \frac{\frac{2}{1+2x}}{3e^{3x}}$$
Next we take the limit of this quotient, and if that exists it is our answer:
$$\lim_{x\to 0}\frac{\frac{2}{1+2x}}{3e^{3x}} = \frac{\frac{2}{1}}{3} = \frac{2}{3}$$

Some times we end up applying the rule twice in a row: The derivatives quotient may also be an indeterminate form, and we apply the theorem to *it*. Here's an example:
$$\lim_{x\to 0}\frac{e^x - x - 1}{x^2}$$

Both numerator and denominator go to $0$ as $x$ goes to $0$, so this is set up for L'Hopital's. We look at the quotient of the derivatives:
$$\lim_{x\to 0}\frac{e^x-1-0}{2x}$$
Now *this* has both numerator and denominator go to $0$, so we take *their* derivatives:
$$\lim_{x\to 0}\frac{e^x}{2}$$
This limit can finally be computed, and it is equal to $\frac{1}{2}$.

### Other indeterminate forms

> Other indeterminate forms can be rewritten in the form of a quotient $\frac{0}{0}$ or $\frac{\infty}{\infty}$, using one of the following:
> $$f(x)g(x) = \frac{f(x)}{1/g(x)}$$
> $$f(x)^{g(x)} = e^{g(x)\ln(f(x))}$$
> $$\frac{1}{f(x)} - \frac{1}{g(x)} = \frac{g(x) - f(x)}{f(x)g(x)}$$

As an example, let us take a look at:
$$\lim_{x\to 0^+}x^x$$
This is an indeterminate form $0^0$. We rewrite it:
$$\lim_{x\to 0^+}e^{x\ln(x)} = e^{\lim_{x\to 0^+}x\ln(x)}$$
So now we are left with a different problem, that of the limit:
$$\lim_{x\to 0^+}x\ln(x)$$
This is an indeterminate form $0\times \infty$. We need to rewrite it, by bringing one of the terms to the denominator. We choose to bring $x$, because it will be easier to differentiate $\frac{1}{x}$ than to differentiate $\frac{1}{\ln(x)}$. So we have:
$$\lim_{x\to 0^+}x\ln(x) = \lim_{x\to 0^+}\frac{\ln(x)}{\frac{1}{x}}$$
This is now a $\frac{-\infty}{\infty}$ form, and we try L'Hopital's:
$$\lim_{x\to 0^+} \frac{1/x}{-1/x^2} = \lim_{x\to 0^+} \frac{-x^2}{x} = 0$$
So $\lim_{x\to 0^+}x\ln(x) = 0$, and hence our original limit becomes:
$$\lim_{x\to 0^+}x^x = e^{\displaystyle\lim_{x\to 0^+}x\ln(x)} = e^0 = 1$$
