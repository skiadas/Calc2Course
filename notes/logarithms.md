# Logarithms

## Reading

Section 7.3

## Problems

Practice Exercises: 7.3 5, 6, 7, 8, 17, 21, 23, 24, 26, 33, 38, 39, 47, 53, 67, 73, 75, 95, 96, 97

Optional: 7.3 118, 120

Exercises to turn in: 7.3 22, 54, 98, 108

## Logarithms

The logarithm function is the inverse of the exponential:

> The base-$b$ **logarithm** $\log_b\colon (0,+\infty)\to\mathbb{R}$ is the inverse to the exponential function $b^x$, namely:
>
> $$b^{\log_b x} = x,\qquad \log_b\left(b^x\right) = x$$
>
> When $b=e$, this is called the **natural logarithm** and denoted $\ln(x)$.

Many properties of the logarithm can be derived from those of the exponential. For now however, we start with the derivative, and for the time being we focus on the natural logarithm:

> $$\ln'(x) = \frac{1}{x}$$

We also know that $\ln(1) = 0$ (because $e^0=1$). We could therefore now formally define the natural logarithm:

> The natural logarithm is defined as the interval
> $$\ln(x)=\int_1^x\frac{1}{t}dt$$
> which makes sense for all $x>0$.

Question: Why does this integral not make sense when $x< 0$?

We can now establish a proper order of proving everything we need:

1. We define $\ln(x)$ via an integral.
2. We prove key formulas for $\ln(x)$, like $\ln(xy) = \ln(x) + \ln(y)$.
3. We prove $\ln(x)$ is one-to-one and onto the real line. It is therefore invertible.
4. We define the exponentinal $\exp(x)$ as its inverse.
5. We prove that for $x$ an integer it then has its usual meaning.
6. We compute its derivative.
7. We establish other properties of $\exp(x)$ from those of its inverse, $\ln(x)$.
8. We define $b^x$ and $\log_b(x)$ using $\exp(x)$ and $\ln(x)$.

During this section, until the very end, we will solely use the notation $a^x$ to denote the usual meaning of power, which makes sense for integers (and maybe if we push it a bit to rational numbers).

Let us begin!

### Logarithm as an integral

We already mentioned above the definition of $\ln(x)$ as the integral $\int_1^x\frac{1}{t}dt$. The fundamental theorem of arithmetic then immediately tells us that $\ln'(x) = \frac{1}{x}$. From this we know that it must be an increasing function. Also the second derivative is $\ln''(x) = -\frac{1}{x^2} < 0$, so the logarithm is always concave down.

We now use the properties of integrals to prove the most important property of logarithms: They turn multiplication to addition:

> $$\ln(xy) = \ln(x) + \ln(y)$$

The proof is very instructive. We break the interval up in 2 parts:

$$\ln(xy) = \int_1^{xy}\frac{1}{t}dt=\int_1^{x}\frac{1}{t}dt + \int_x^{xy}\frac{1}{t}dt$$

We can now perform integration by parts on the second integral, by setting $u=\frac{t}{x}$. Then $du=\frac{dt}{x}$, and the second integral becomes:

$$\int_x^{xy}\frac{1}{t}dt = \int_1^y\frac{1}{u}du$$

Putting the two together we get:

$$\ln(xy) = \int_1^{xy}\frac{1}{t}dt = \int_1^{x}\frac{1}{t}dt + \int_1^y\frac{1}{u}du = \ln(x) + \ln(y)$$

From this we can easily deduce what happens to powers:
$$\ln(x^2) = \ln(xx) = \ln(x) + \ln(x) = 2\ln(x)$$
$$\ln(x^3) = \ln(x^2x) = \ln(x^2) + \ln(x) = 2\ln(x) + \ln(x) = 3\ln(x)$$
and so on. The Principle of mathematical induction then shows us that for all natural numbers $n$:
$$\ln(x^n) = n\ln(x)$$

Also if we put in $y=\frac{1}{x}$ in the formula above we would obtain:

$$\ln(1/x) = -ln(x)$$
and from it
$$\ln(x/y) = \ln(x) - \ln(y)$$

Let us pause for a second and list the properties that we have so far:

> - $\ln(x) = \int_1^x\frac{1}{t}dt$.
> - $\ln$ is an increasing function and concave down.
> - $\ln(xy) = \ln(x) + \ln(y)$.
> - $\ln(1) = 0$.
> - $\ln(1/x) = -\ln(x)$.
> - $\ln(x/y) = \ln(x) - \ln(y)$.
> - $\ln(x^n) = n\ln(x)$.

### The range of the logarithm

Our next goal would be to find the range of the logarithm function. We start by the following simple observation, that holds for all integers $n$:

$$\ln\left(2^n\right) = n\ln(2)$$

Now $\ln(2)$ is a positive number (it is the integral from $1$ to $2$ of a positive function). So $n\ln(2)$ can be made as large as we want it to be for positive integers $n$, and as negative as we want it to be for all negative integers $n$.

What this means is that the function $\ln(x)$ can take arbitrarily large positive and negative values, as we adjust the value of $x=2^n$. Because it is also a continuous function, the *Intermediate Value Theorem* tells us that all numbesr inbetween are also values of the function. In other words we get all of the following:

> - $\lim_{x\to+\infty}\ln(x) = +\infty$.
> - $\lim_{x\to 0^+}\ln(x) = -\infty$.
> - The range of values of $\ln(x)$ is $\mathbb{R} = (-\infty,\infty)$.
> - In particular there must be a number $e$ such that $\ln(e) = 1$.

### The exponential properly

Since the logarithm is an onto function over the entire real line, and it is also one-to-one (it is increasing because of its positive derivative), we can define its inverse:

> $$\exp\colon \mathbb{R} -> (0,+\infty)$$
> $$y=\exp(x)\textrm{ if and only if }x = \ln(y)$$
> $$\exp(\ln(y)) = y$$
> $$\ln(\exp(x)) = x$$

Based on this fact, we can derive basic properties of the exponential from the corresponding properties of the logarithm. For example, take $x_1,x_2$, and we want to show that $\exp(x_1+x_2) = \exp(x_1)\exp(x_2)$. Let's see:

- Define $y_1 = \exp(x_1)$, and so $x_1 = \ln(y_1)$.
- Define $y_2 = \exp(x_2)$, and so $x_2 = \ln(y_2)$.
- Now we can say that $\ln(y_1y_2) = \ln(y_1) + \ln(y_2) = x_1 + x_2$.
- But if $\ln(y_1y_2) = x_1+x_2$, this must mean that $\exp(x_1+x_2) = y_1y_2$.
- This is in fact the formula we were trying to establish.

A similar logic can help us show for example that $\exp(nx) = (\exp(x))^n$, or that $\exp(-x) = 1 / \exp(x)$.

Finally, let us compute the derivative of $\exp(x)$. Recall the general rule: If $g$ was the function that is inverse to $f$, then its derivative is:
$$g'(x) = \frac{1}{f'(g(x))}$$
In our case, this means that:
$$\exp'(x) = \frac{1}{\ln'(\exp(x))} = \frac{1}{1/\exp(x)} = \exp(x)$$

So the exponential is its own derivative!. We obtained the result this time by using its definition as the inverse of the logarithm, and the definition of the logarithm as an integral.

### Other bases for logarithms and exponentials

Let us establish a relation between logarithms, exponentials and actually powers of elements. Let us write some such relations down:

- $\ln(b^n) = n\ln(b)$. This gives:
- $b^n = \exp(n\ln(b))$. For $b=e$ and since $\ln(e)=1$ we have:
- $e^n = \exp(n)$.
- It therefore makes sense to in general define: $$b^x =\exp(\ln(b)x)$$ and $e^x = \exp(x)$$.
- In particular $b^x = e^{\ln(b) x}$.
- $\log_b(x)$ is the inverse of $b^x$.
- $y=\log_b(x)$ if and only if $x = b^y = e^{\ln(b)y}$, if and only if $\ln(b)y = \ln(x)$.
- So we could define: $$\log_b(x) = \frac{\ln(x)}{\ln(b)}$$
- More generally we have the formula: $$\log_b x = \frac{\log_a x}{\log_a b}$$
- The derivative of the generic logarithm is now straighforward: $$\log_b'(x) = \left(\frac{\ln(x)}{\ln(b)}\right)' = \frac{1}{\ln(b) x}$$

This wraps up our main overview of the logarithm and exponential functions and their properties. There is however one more cool topic to explore:

### The "logarithmic derivative" of a function

A commonly used concept is that of the logarithmic derivative of a function, which is simply the derivative of the logarithm of the function, which makes sense for positive-valued functions:

> The logarithmic derivative of $f$ is:
> $$\frac{d}{dx}\ln(f(x)) = \frac{f'(x)}{f(x)}$$

One convenient property of the logarithmic derivative is that it is easy to compute for a product of functions:

$$\frac{d}{dx}\ln(f(x)g(x)) = \frac{f'(x)}{f(x)} + \frac{g'(x)}{g(x)}$$
