# Method of Partial Fractions

## Reading

Section 8.5

## Problems

Practice Exercises: 8.5 1, 2, 3, 5, 6, 9, 11, 15, 21, 27, 29

Exercises to turn in: 8.5 4, 8, 16, 30

## Method of Partial Fractions

The main goal of this section is to learn the techniques involved in computing integrals of the form:
$$\int\frac{P(x)}{Q(x)}dx$$
where $P(x)$ and $Q(x)$ are polynomials.

We will outline here the main ideas. There are plenty of examples in the book.

The method of computing such integrals follows 4 steps:

- If the degree of $P(x)$ is at least as much as the degree of $Q(x)$, first do polynomial division.
- Break the denominator $Q(x)$ into factors. We need linear factors $x-a$ as well as quadratic factors $x^2+bx+c$ where the quadratic has no real roots.
- Perform partial fraction decomposition, where the quotient $\frac{P(x)}{Q(x)}$ breaks down into a sum of terms with denominators those factors from the previous step.
- Compute the integrals of each of these smaller pieces.

We will now look at each of these steps.

### Polynomial Division

> If $P(x)$, $Q(x)$ are two polynomials, and the degree of $P$ is equal to or more than the degree of $Q$, then there are polynomials $R(x)$, $S(x)$, so that the degree of $S$ is less than the degree of $Q$ and so that:
> $$P(x) = R(x)Q(x) + S(x)$$
> or equivalently
> $$\frac{P(x)}{Q(x)} = R(x) + \frac{S(x)}{Q(x)}$$

Quotients where the numerator has degree less than the denominator are often called **proper**.

To find $R$ and $S$ we use **long division**. An example would be:
$$\frac{x^3 + 1}{x^2-4} = x + \frac{4x+1}{x^2-4}$$

You can find many examples of long division online.

### Factoring out the denominator

The fact that we can factor out the denominator is an important theorem in algebra:

> **Fundamental Theorem of Algebra** (for real polynomials)
>
> Every non-constant polynomial can be written as a product of terms of two types:
> - Linear terms $x-a$.
> - Quadratic terms $x^2+bx+c$ with no real roots (irreducible).

We will not prove this theorem here, but we will discuss how to find at least linear terms.

> The linear term $x-a$ will be a factor of the polynomial $P(x)$ if and only if $a$ is a root of of the polynomial, i.e. if $P(a) = 0$.
>
> Roots can be found for instance via Newton's method, or the bisection method, both usually seen in Calculus 1.
>
> If the polynomial coefficients are all integers, then good candidates for roots are rational numbers of the form $\pm\frac{p}{q}$, where $p$ divides the constant coefficient and $q$ divides the leading coefficient.

Once a linear term has been found, long division can simplify the original polynomial into $P(x) = (x-a)P_1(x)$, then we continue with $P_1(x)$.

In most problems, we will be providing the factorization for you (or in the case of a quadratic, you can easily find it yourself by solving the quadratic).

### Partial Fraction Decomposition

The heart of the matter is the partial fraction decomposition. At this point we have a quotient that has the form:
$$\frac{P(x)}{\left(x-a_1\right)^{k_1}\left(x-a_2\right)^{k_2}\cdots\left(x^2+b_1x+c_1\right)^{n_1}\left(x^2+b_2x+c_2\right)^{n_2}\cdots}$$
where the terms appearing in the denominator are distinct and have total degree adding up to more than the numerator. Then we can write this expression as a sum of terms:
$$\frac{A}{(x-a)^k}$$
and terms
$$\frac{Bx+C}{\left(x^2+bx+c\right)^k}$$
where the terms are amongst those that appear in the original denominator, and the power $k$ goes from $1$ to the power appearing in the original denominator.

An example will make this clearer. Suppose we have the expression:
$$\frac{x+1}{(x-1)(x+2)}$$
Then we should be able to write it as:
$$\frac{x+1}{(x-1)(x+2)} = \frac{A_1}{x-1} + \frac{A_2}{x+2}$$
All that remains is to determine the coefficients $A_1$ and $A_2$. We do this by making common denominators, then equating the resulting numerators on the two sides:
$$x+1 = A_1(x+2) + A_2(x-1)$$
The key thing here is that this equality should hold *for all $x$*. So we treat it as an identity: The two polynomials on the two sides must be equal. There are two ways to find the coefficients from here:

1. Equate same terms: The right-hand side can be rewritten as $(A_1+A_2)x + (2A_1 - A_2)$. So we must have that $A_1+A_2=1$ and $2A_1 - A_2 = 1$. We then solve this system of equations.
2. Plug in appropriate values for $x$. This can make things a lot easier. For example if we plug in $x=1$, then the $A_2$ term goes away, and we are left with: $1+1 = A_1(1+2)$, or $A_1 = \frac{2}{3}$. Similarly, plugging in $x=-2$ makes the $A_1$ term go away, and gives us $A_2 = \frac{1}{3}$.

So we obtain:
$$\frac{x+1}{(x-1)(x+2)} = \frac{2/3}{x-1} + \frac{1/3}{x+2}$$

Some times we deal with one of the terms showing up with a higher power, for example:
$$\frac{2x+1}{(x-1)^2(x+2)}$$
In that case we need to include in the terms on the right the various powers as options:
$$\frac{2x+1}{(x-1)^2(x+2)} = \frac{A_1}{x-1} + \frac{A_2}{(x-1)^2} + \frac{A_3}{x+2}$$

To find out the three terms, we again make common denominators:
$$\frac{2x+1}{(x-1)^2(x+2)} = \frac{A_1(x-1)(x+2) + A_2 + A_3(x-1)^2}{x-1}$$
We now equate the numerators:
$$2x+1 = A_1(x-1)(x+2) + A_2 + A_3(x-1)^2$$

- First off we can find $A_2$ by setting $x=1$ on both sides. Then we get $A_2 = 3$.
- Now we plug in $x=-2$. This eliminates one of the terms on the right, and leads to: $-3 = A_2 + A_3(-3) = 3 - 3A_3$, or $A_3 = 2$.
- Next, we can compare the quadratic terms. This leads us to conclude that $A_1+A_3=0$, or that $A_1 = -A_3 = -2$.

So finally we have:
$$\frac{2x+1}{(x-1)^2(x+2)} = \frac{-2}{x-1} + \frac{3}{(x-1)^2} + \frac{2}{x+2}$$

### Computing the resulting integrals

All remaining integrals fall into one of two forms:

> $$\int\frac{A}{(x-a)^k}$$

If $k=1$, this integral is simply a logarithm $A\ln|x-a|$. If $k > 1$, we can integrate directly to $\frac{A}{k+1}\frac{1}{(x-a)^{k+1}}$

> $$\int\frac{Ax+B}{\left(ax^2+bx+c\right)^k}$$

where the quadratic has no real roots. These integrals can be solved by an appropriate trigonometric substitution using $\tan t$, using the techniques we have examined in previous sections.
