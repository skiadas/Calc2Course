# Inverse Functions

## Reading

Section 7.2

## Problems

Practice Exercises: 7.2 1, 2, 3, 5, 6, 8, 10, 13, 23, 28, 29, 30

Exercises to turn in (along with those from 7.1): 7.2 4, 40

## Inverse functions

### Domains and Ranges

Before we discuss the idea of inverse functions, let us review what a function is to begin with:

> A **function** consists of 3 things:
>
> - A set $D$ called the **domain**
> - A set $R$ called the **range**
> - A rule that tells us how for any value $x$ in the domain $D$ we can produce a corresponding value $f(x)$ in the range $R$.
>
> We usually indicate the domains of the function by writing something like
> $$f\colon D \to R$$

So a function is not just a "formula", it is a specification of what values $x$ we are allowed to put in the formula, and what range we guarantee the results to be in. A requirement for something to be a function is that for every single value $x$ in $D$ it *must* produce a corresponding value $f(x)$ which must be in $R$.

Oftentimes we make allowances, and we define the domain $D$ implicitly by saying that $D$ is the set of all points where the formula makes sense. For instance for the function $f(x) = \frac{1}{x}$ we could say that the domain is $\mathbb{R}\setminus \{0\}$, or in other words all non-zero numbers. But perhaps we want to restrict our function, and say only look at its behavior from $1$ to $4$. Then we can talk about the function with domain the interval $[1, 4]$ and formula $f(x) = \frac{1}{x}$.

Similarly we often omit the range $R$, and assume it to either be the entire real line or the set of all possible values of the function (often not easy to determine that set).

But for this section we will be very explicit in our domain and range specifications, and they will be part of what it means to *have a function*.

### The inverse of a function

> If we have a function $f\colon D\to R$ and a function $g\colon R\to D$ (notice the domains and ranges switched), then we say that the function $g$ is the **inverse** to $f$, if:
>
> - $g(f(x)) = x$ for all $x\in D$ and
> - $f(g(y)) = y$ for all $y\in R$
>
> We also say that $f$ is invertible, and we denote $g$ by $f^{-1}$.
>
> Another way to think about it is to say that $y=f(x)$ if and only if $x = g(y)$.

**Note** that this is not the same as taking "one over" the function, i.e. $\frac{1}{f(x)}$. This would be denoted by $\left(f(x)\right)^{-1}$, while the inverse function would be $f^{-1}(x)$.

Most of the times we find the inverse by solving the equation $y=f(x)$ for $x$. For example:

Let $f(x) = 2x+3$. Then we set $y=2x+3$, and we solve for $x$ to find $x=\frac{1}{2}\left(y - 3\right)$. This is the inverse function $g(y) = \frac{1}{2}(y-3)$. Technically we should have included the domain and range of these functions, which would be the entire real number line.

Here is another example. Consider the function $f(x) = x^2$. We can try to do the same and set $y=x^2$. Then to solve for $x$ we would have to take square roots, which as we know:

1. requires $y$ to be nonnegative,
2. has two solutions unless we require $x$ to be nonnegative.

So in this case in order to solve for $x$ we need to restrict $x$. So even though the function $f(x) = x^2$ is defined for all real numbers $x$, we will restrict it to the domain $D=[0, +\infty)$, and similarly the range would be $R=[0, +\infty)$ to respect the fact that those are the allowed $y$ values. Then we can define the inverse $g\colon R \to D$ via $g(y) = \sqrt{y}$.

This has led us to two obstacles in having an inverse:

1. The equation $y=f(x)$ might not be solvable for some $y\in R$,
2. The equation $y=f(x)$ might have multiple solutions $x\in D$.

Both of these are problems if we are trying to define the inverse. And they both have names:

> We say a function $f\colon D\to R$ is **one-to-one**, if it cannot happen that we have $x_1,x_2\in D$ with $x_1\neq x_2$ but $f(x_1) = f(x_2)$. A one-to-one function can never take the same value twice.
>
> We say that a function $f\colon D\to R$ is **onto**, if every number in $R$ is a value of the function, i.e. if for each $y\in R$ there is an $x\in D$ such that $f(x) = y$. An onto function hits every value in the range.

Note that the book does not talk about "onto" functions, and instead effectively thinks about reducing the range to only those numbers that are values of the function.

A good example of these ideas is our function $f(x) = x^2$ earlier. If we think of it as a function $f\colon (-\infty, \infty) \to (-\infty, \infty)$, then it will be neither one-to-one nor onto:

- It is not one-to-one because negative numbers have the same squares as corresponding positive numbers, so for instance $f(2) = f(-2)$ even though $2\neq -2$.
- It is not onto because the squares are nonnegative. So if $y=-1\in (-\infty, \infty)$, then there is no $x$ such that $f(x) = y$.

On the other hand, the function $f:[0,+\infty)\to[0,+\infty)$ is both one-to-one and onto.

We can usually make a function one-to-one by restricting its domain. We can make it onto by restricting its range.

The ideas of one-to-one and onto functions are closely related to that of invertible functions. In fact we have the following:

> If $f$ is an invertible function with inverse $g$, then $f$ is both one-to-one and onto:
>
> - The fact that $g(f(x)) = x$ for all $x\in D$ means that $f$ is **one-to-one**: If for some $x_1,x_2\in D$ we have $f(x_1) = f(x_2)$, then we must also have $g(f(x_1)) = g(f(x_2))$, and hence $x_1 = x_2$. So we can't have two different $x$'s with the same values.
> - The fact that $f(g(y)) = y$ for all $y\in R$ means that $f$ is **onto**: For every $y\in R$ there is an $x\in D$ such that $f(x) = y$. That $x$ is in fact $x=g(y)$.

Conversely, if a function is one-to-one and onto, then it is invertible:

> If $f\colon D\to R$ is a one-to-one and onto function, we can define a function $g\colon R\to D$ as follows:
>
> - If $y\in R$, then because $f$ is onto there is an $x\in D$ such that $f(x) = y$. We define $g(y)$ to be that $x$.
> - We need to show 2 things: First, that for each $y\in R$ we have $f(g(y))=y$. This is literally how we defined $g(y)$, as an $x$ such that $f(x) = y$.
> - Second, that for each $x\in D$ we have $g(f(x)) = x$. Let us start by giving a name to $f(x)$, let's call it $y$. So $y=f(x)$ and $y\in R$. We defined $g(y)$ as the $x$ such that $f(x) = y$. The only problem we might have is if there were two such $x$'s. But the fact that $f$ is one-to-one means that there are not: There is a exactly one $x$ such that $y=f(x)$ and we defined $g(y)$ to be that $x$. so if we start with an $x$ and compute $y=f(x)$, then take $g(y) = g(f(x))$, we will get back that $x$ as it is the only possible value for $g(y)$.

### Derivative of the inverse

The nice thing about inverses is that the computation of the derivative of the inverse is relatively easy to do. For this, let's imagine that $f$ is differentiable, and that its inverse is also differentiable. We would like to find a formula for the derivative.

We have
$$f(g(y)) = y$$
and the chain rule tells us how to differentiate this equation in terms of $y$:
$$\frac{d}{dy}f(g(y)) = \frac{d}{dy} y = 1$$
$$f'(g(y))g'(y) = 1$$

So we get the formula:

> $$g'(y) = \frac{1}{f'(g(y))}$$

So to compute the derivative of the inverse, all we have to do is take 1 over the derivative of $f$, evaluated at the inverse.

The question of why $g$ is invertible in the first place is a harder question. We will not address it at this point.

Let us see an example of this. Suppose $f(x) = x^2$ on the domain $[0,\infty)$. Then $f'(x) = 2x$ and we already said that the inverse of $f$ is the function $g(y) = \sqrt{y}$. We already know the derivative of the square root of course, but we will now derive it as a consequence of it being the inverse function to the square function. We would have:

$$g'(y) = \frac{1}{f'(g(y))} = \frac{1}{2 g(y)} = \frac{1}{2 \sqrt{x}}$$



