# The exponential function

## Reading

Section 7.1

## Problems

Practice Exercises: 7.1 1, 2, 5, 6, 7, 15, 16, 19, 23, 25, 47, 53, 71, 75, 76, 77, 93

Optional, highly recommended: 7.1 94, 97, 99

Exercises to turn in (along with those from 7.2): 7.1 26, 48

## The exponential function

The exponential function is an extension of the notion of raising a value to a power. Let us start from this idea.

If $n$ is a natural number, then we can define $b^n$ as the product of exactly $n$ copies of $b$. It is immediate to see that this satisfies a key property:

> Key property of the exponential function:
> $$b^{x+y} = b^x b^y$$

For now we can only make sense of this formula for $x,y$ both being natural numbers, $1, 2,\ldots$. And then it is straightforward: If we multiply $3$ copies of $b$ and $4$ copies of $b$, this is the same as if we had multiplied $3+4=7$ copies of $b$. In fact that same property forces this on us. For example:

$$b^2 = b^{1+1} = b^1 b^1$$
$$b^3 = b^{2+1} = b^2 b^2 = (b^1 b^1) b^1$$

So even if we don't identify $b^1$ with $b$, the above property still leads us to the result that $b^n$ is the product of $n$ copies of $b^1$.

Our goal is simple: Define the exponential function in other values while maintaining the above property. In fact the following is true:

> The exponential function $b^x$ is the unique function that:
>
> - is defined for all real numbers $x$
> - is differentiable everywhere
> - agrees with the normal "multiply $n$ times" meaning of $b^n$ when $n$ is a natural number
> - satisfies the key property $b^{x+y} = b^x b^y$ for all real numbers $x$ and $y$

It should be emphasized that the notation $b^x$ is really just that, a notation, for any value of $x$ that is not a natural number. We could just as well have written $f_b(x)$ for that function, and expected $f_b(x+y)=f_b(x)f_b(y)$. It is customary to denote the exponential function as a power, but it is important to keep in mind that the only meaning of $b^x$ as a "power" is only when $x$ is a natural number.

### Exponential for the integers

As I mentioned earlier, the key property of the exponential function is that it turns multiplication into addition:
$$b^{x+y} = b^x b^y$$

We will now explore the consequences of this property, which we assumed holds for all real numbers $x, y$. It should therefore hold when $y=0$ and $x$ is any number, and then it reads:

$$b^x = b^x b^0$$

This can only happen if either all the $b^x$ are equal to $0$, which only happens if $b=0$, or if instead $b^0=1$. Therefore, except for the trivial case of $b=0$, we are *forced* to defined $b^0$ as:

$$b^0 = 1$$

Next we consider what happens when $x$ is any number but $y=-x$ is its negative. Then the formula becomes:

$$1 = b^0 = b^{x-x} = b^x b^{-x}$$

This again forces us to define:

$$b^{-x} = \frac{1}{b^x}$$

and an easy consequence of that is that:

$$b^{x-y} = \frac{b^x}{b^y}$$

So now, based on these "derived" properties, we have definitions of $b^x$ for all *integers* $0, \pm 1, \pm 2, \ldots$.

Next up we want to consider what we should do for rational numbers. Before we do that, let us derive one more property:

$$b^{xy} = \left(b^x\right)^y$$

For now we will only derive this property for $y$ a natural number. It is easy to see how it would work for small values $y=1,2,3, 4$:

$$b^{x\cdot 1} = \left(b^x\right)^1$$

$$b^{x\cdot 2} = b^{x + x} = b^x b^x = \left(b^x\right)^2$$

$$b^{x\cdot 3} = b^{2x + x} = b^{2x} b^x = \left(b^x\right)^2 b^x = \left(b^x\right)^3$$

$$b^{x\cdot 4} = b^{3x + x} = b^{3x} b^x = \left(b^x\right)^3 b^x = \left(b^x\right)^4$$

It is easy to imagine that this could continue for all natural numbers: For each new natural number $n+1$ we use the fact that we know it for the previous one (i.e. $n$) and use that information to prove it for $n+1$. The formal way of saying that is known as the *principle of mathematical induction*.

> **Principle of Mathematical Induction**
>
> If we want a property $L(n)$ to be true for all natural numbers $n$, it is enough to:
>
> 1. Show it to be true for $n=1$, i.e. "$L(1)$ is true"
> 2. Show how knowing it to be true for a specific $n$ would allow us to also show it for $n+1$, or in other words proving that "$L(n)$ true implies $L(n+1)$ true"

### Exponential for the rational numbers

Now we show how the definition of the exponential for rational numbers is forced upon us. Because of the formula for $b^{-x}$, it is enough for us to consider positive rational numbers. So say $x=\frac{p}{q}$, where $p$, $q$ are both natural numbers. Then $p = xq$, and the property we just proved forces the following steps:

$$b^p = b^{xq} = \left(b^x\right)^q$$

Therefore we have no choice: $b^x$ must be the $q$-th square root of $b^p$:

$$b^{p/q} = \sqrt[q]{b^p}$$

and as a special case:

$$b^{1/n} = \sqrt[n]{b}$$

With this in mind, we have defined, in a unique and unavoidable way, the function $b^x$ for all rational numbers. If we had some more tools at our disposal, we could literally define $b^x$ as:

$$b^x = \lim_{m/n\to x}b^{m/n}$$

And another cool consequence of all this is that the exponential function needs to always be positive:

$$b^x = \left(b^{x/2}\right)^2$$

### The derivative of the exponential

Let us now see what we can say about the derivative of the exponential function, if such derivative is to exist. We know the limit definition:

$$\frac{d}{dx}b^x = \lim_{h\to 0}\frac{b^{x+h} - b^x}{h} = \lim_{h\to 0}\frac{b^x b^h - b^x}{h}$$

Notice that $b^x$ is a constant that is a common factor in the numerator, so we can take it all the way out of the limit:

$$\frac{d}{dx}b^x = b^x\lim_{h\to 0}\frac{b^h-1}{h}$$

So it all hinges on the limit:

$$m(b) = \lim_{h\to 0}\frac{b^h-1}{h}$$

For now we don't have a way to find this number (which depends on $b$), other than experimentally computing the limit, but one thing we can say for sure is that the derivative of $b^x$ is a constant multiple of $b^x$:

$$\frac{d}{dx}b^x = m(b) b^x$$

> The derivative of the function $b^x$ is a constant multiple of $b^x$.
>
> Because $b^x$ is always positive, the derivative of $b^x$ is either always negative or always positive, depending on the sign of $m(b)$. So $b^x$ is either always increasing or always decreasing.

### Exploring $m(b)$

Let us see what, if anything, we can say about $m(b)$. The chain rule can help us there:

$$\frac{d}{dx}b^{xy} = m(b) b^{xy} \frac{d}{dx}(xy) = m(b) y b^{xy}$$

But at the same time:

$$\frac{d}{dx}b^{xy} = \frac{d}{dx}\left(\left(b^y\right)^x\right) = m(b^y) b^{xy}$$

So we have the relation:

$$m\left(b^y\right) = y m(b)$$

If you know about the logarithm function, this might seem familiar. We also can easily say that $m(1) = 0$, thinking of its definition as a limit and the fact that $1^x=1$ for all $x$.

### The natural exponential function

It turns out that amongst all the possible bases $b$, there is a special one for which $m(b)=1$. This base is denoted by $e$, and gives rise to the familiar exponential function $e^x$. In that case we have that the exponential is its own derivative:

$$\frac{d}{dx} e^x = e^x$$

Also note that the previous formula for $m(b)$ becomes:

$$m\left(e^y\right) = y$$

So the exponential and the "function" $m$ are what we will later refer to as *inverse* functions.

### Solving the differential equation

The function $b^x$ solves the differential equation
$$\frac{d}{dx}b^x = m(b) b^x$$
with $b^0 = 1$. In fact it is the only function that has this property:

> If $f(x)$ is a differentiable function with $f(0)=1$ and such that
> $$\frac{d}{dx}f(x) = m(b)f(x)$$
> then it must be the case that $f(x) = b^x$.

In general solving differential equations, i.e. equations involving the derivatives of functions, is not so easy. But in this case it is. Let us prove the above claim:

Consider the function:
$$h(x) = \frac{f(x)}{b^x}$$
We will compute its derivative, using the quotient rule:
$$h'(x) = \frac{f'(x)b^x - f(x) \left(b^x\right)'}{\left(b^x\right)^2} = \frac{m(b)f(x)b^x - f(x)m(b)b^x}{b^{2x}} = 0$$

So we obtain the remarkable fact that $h$ must be a constant function. And since $h(0) = 1$, this constant must be $1$. Therefore we have that
$$\frac{f(x)}{b^x}=1$$
or
$$f(x) = b^x$$

And this proves our claim.

Here is one remarkable consequence of this result:
$$b^x = e^{m(b)x}$$
and in particular
$$e^{m(b)} = b$$
reinforcing the idea that $m$ and the exponential are inverse functions of each other.

Why is this last result true? We can compute the derivative of $e^{m(b)x}$ using the chain rule, and from that deduce that it is the kind of function $f$ described in the above result.

### Summary

> The exponential function $b^x$:
>
> - defined for all real numbers $x$
> - satisfies $$b^{x+y} = b^x b^y$$
> - satisfies $$b^{xy} = \left(b^x\right)^y$$
> - satisfies $$b^{x-y} = \frac{b^x}{b^y}$$
> - satisfies $$b^{1/n} = \sqrt[n]{b}$$
> - is differentiable with derivative $$\frac{d}{dx} b^x = m(b) b^x$$ where $m(b)$ is a constant that depends on $b$
>
> There is a value $e$ such that $m(e) = 1$. For this value the function equals its own derivative: $$\frac{d}{dx} e^x = e^x$$
>
> The natural exponential and the function $m$ are inverse functions of each other:
> $$e^{m(b)} = b$$
> $$m\left(e^x\right) = x$$
