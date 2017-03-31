# Numerical Integration

## Reading

Section 8.8

## Problems

Practice Exercises: 8.8 1-5, 9, 11, 13, 15, 17

Exercises to turn in: 8.8 10, 12, 14, 18

## Numerical Integration

There are numerous instances where the exact value of an integral cannot be determined, often simply because we have no way to find a closed form for the antiderivative. In such situations it is important, and convenient, to have methods for approximating the integral. We will look at various methods in this section.

First we need to set up some notation. All our methods are based around the idea of using a **partition** of the interval into $N$ equal pieces. We will fix our notation throughout:

> $\Delta x = \frac{b-a}{N}$ is the interval width.
>
> $x_0=a$, $x_1=a+\Delta x$, $x_2 = a + 2\Delta x$, \ldots, $x_N = b$($= a + N \Delta x$) are the $N+1$ endpoints.
>
> We also assign names to the values at those endpoints:
> $$y_i = f(x_i) = f(a + i\Delta x)$$

### Trapezoidal Rule

Our first method goes as follows: On each subinterval, we approximate the area by using a trapezoid connecting the endpoints. So in the $i$'th interval, that goes from $x_{i-1}$ to $x_i$, we form a trapezoid using the 4 points $(x_{i-1},0)$, $(x_i, 0)$, $(x_{i-1}, y_{i-1})$, $(x_i, y_i)$. The area of this trapezoid would be:
$$\frac{1}{2}\Delta x (y_{i-1} + y_i)$$
Putting all these areas together leads us to the formula for the trapezoidal rule:

> **Trapezoidal Rule**. The $N$-th trapezoidal approximation to $\int_a^b f(x) dx$ is:
>
> $$T_N = \frac{1}{2}\Delta x \left(y_0 + 2y_1 + \cdots + 2y_{N-1} + y_N\right)$$

You can also think of the trapezoidal rule as an average between the left-endpoint rectangles and the right-endpoint rectangles.

Let us try this in an example, using the integral:
$$\int_0^1 \sqrt{1-x^2}dx$$
This is simply the area in the first quadrant under the unit circle, so it should equal $\frac{\pi}{4}$. So we will use this method to try to approximate $4$.

We need to first decide to break the interval $[0,1]$ in smaller intervals. We will go with $N=8$, so then the points $x_0$, $x_1$, \ldots are:
$$0,\,0.125,\,0.25,\,0.375,\,0.5,\,0.625,\,0.75,\,0.875, 1$$
We start by computing the corresponding $y$ values, using $y=f(x) = \sqrt{1-x^2}$:
$$1,\,0.992,\,0.968,\,0.927,\,0.866,\,0.7806,\,0.6614,\,0.484,\,0$$
Now the trapezoid rule would say:
$$T_8 = \frac{1}{2}\cdot 0.125 \left(1+ 2\times 0.992+ 2\times 0.968+ 2\times 0.927+ 2\times 0.866+ 2\times 0.7806+ 2\times 0.6614+ 2\times 0.484+ 0\right) = 0.772375$$
Multiplying by $4$ we get the following pretty bad approximation for $\pi$: $3.0895$.

But for using only $8$ intervals, it isn't all that bad. One of the reasons that it is doing so poorly is the speed with which the function $\sqrt{1-x^2}$ descents to $0$ near $x=1$. If you look at our $y$ values, they jump straight from $0.484$ to $0$, and we are missing information about that transition.

Let us try another integral that also approximates $\frac{\pi}{4}$, namely:
$$\int_0^1\frac{1}{1+x^2}dx = \frac{\pi}{4}$$
We will use the same $x$ values as above. The corresponding $y$ values would be:
$$1,\,0.9846,\,0.9412,\,0.8767,\,0.8,\,0.7191,\,0.64,\,0.5664,\,0.5$$
The trapezoid rule for this case would be:
$$T_8 = \frac{1}{2}\cdot 0.125\left(1+2\times 0.9846+2\times 0.9412+2\times 0.8767+2\times 0.8+2\times 0.7191+2\times 0.64+2\times 0.5664+ 0.5\right) = 0.78475$$
Multiplying that by $4$ we find $\pi\approx 3.139$. Not too bad!

### Midpoint approximation

The midpoint approximation uses the values at the midpoints of each interval. You can think of it as a "rectangle" approximation, or you can also think of it as a trapezoidal approximation where the trapezoid is formed by taking the tangent line at the midpoint.

> **Midpoint Rule**. The $N$th midpoint approximation for $\int_a^b f(x)dx$ is:
>
> $$M_N = \Delta x\left(f(c_1)+f(c_2)+\cdots + f(c_N)\right)$$
> where $c_i = \frac{1}{2}(x_{i-1} + x_i)$ is the midpoint of the $i$-th interval.

Using the second example above, the midpoint $c$s would be:
$$0.0625,\,0.1875,\,0.3125,\,0.4375,\,0.5625,\,0.6875,\,0.8125,\,0.9375$$
The values of $f(x) = \frac{1}{1+x^2}$ at those points are:
$$0.9961,\,0.966,\,0.911,\,0.8393,\,0.75964,\,0.679,\,0.6024,\,0.532$$
Then $M_8$ would equal:
$$M_8 = 0.125\left(0.9961 + 0.966 + 0.911 + 0.8393 + 0.75964 + 0.679 + 0.6024 + 0.532\right) = 0.78568$$
Multiplying this by $4$ we find for $\pi$ the approximation $\pi\approx 3.14272$.

Before we talk about error bounds, i.e. how can we tell how good the approximation is, let us see one final version:

### Simpson's Rule

Simpson's Rule is a certain combination of the two previous methods, weighted appropriately. The final formula is:

> **Simpson's rule**. For $N$ even, the $N$-th approximation to $\int_a^b f(x)dx$ by Simpson's rule is:
>
> $$S_N = \frac{1}{3}\Delta x\left(y_0 + 4y_1 + 2y_2 + 4y_3 + \cdots + 2y_{N-2} + 4y_{N-1} + y_N \right)$$

Let us try it out in our example, with $N=8$:
$$S_N = \frac{1}{3}0.125 \left(1+ 4\times 0.9846+ 2\times 0.9412+ 4\times 0.8767+ 2\times 0.8+ 4\times 0.7191+ 2\times 0.64+ 4\times 0.5664+ 0.5\right) = 0.7854$$
Multiplying by $4$ we get the approximation $\pi\approx 3.14156$.

Not bad!

### Error bounds

Will the above estimates are nice, and seemed to work not all that bad in practice, there is one piece missing: We would like to have guarantees about how close an approximation is. This is measured by the error:

> $$\textrm{Error}(T_N) = \left|\int_a^b f(x)dx - T_N\right|$$

And similarly for other approximations. The error simply measures how far we are from the actual value. It is useful to have bounds for these errors, to be able to say for instance that "we are less than 0.005 away from the correct value". This is the goal of error bound calculations:

> **Error bounds**
>
> If $f''(x)$ exists and is continuous on $[a,b]$, and if $K_2$ is a bound on its absolute value, i.e. $\left|f''(x)\right|\leq K_2$ for all $x\in[a,b]$, then:
> $$\textrm{Error}(T_N) \leq\frac{K_2(b-a)^3}{12N^2}$$
> and
> $$\textrm{Error}(M_N) \leq\frac{K_2(b-a)^3}{24N^2}$$
>
> If the fourth derivative exists and is bounded by $K_4$ in absolute value, then:
> $$\textrm{Error}(S_N) \leq\frac{K_4(b-a)^5}{180N^4}$$

Let us try these bounds in action. In our latest example $a=0$, $b=1$, and $f(x) = \frac{1}{1 + x^2}$. We need its derivatives:
$$f'(x) = \frac{-2x}{\left(1+x^2\right)^2}$$
$$f''(x) = \frac{6x^2-2}{\left(1+x^2\right)^3}$$
We need to find a good bound for this second derivative, on the interval $[0,1]$. The numerator is at most $4$, whilc the denominator is at least $1$, so the quotient is at most $4$, so we can use $K_2=4$. Then the above formulas read:
$$\textrm{Error}(T_N) \leq\frac{4}{12 \cdot 8^2} = 0.0052$$
So $T_N$ would be guaranteed to be that close to the right answer.
Similarly:
$$\textrm{Error}(M_N) \leq\frac{4}{24 \cdot 8^2} = 0.0026$$

Recall that when we try to estimate $\pi$ with this method, we end up multiplying by $4$, which would then multiply these bounds by $4$.

The Simpson's Rule estimate would require some more work. The fourth derivative turns out to be:
$$f^{(4)}(x) = \frac{24\left(5x^4-10x^2+1\right)}{\left(x^2+1\right)^5}$$
It turns out that the best possible bound for this quantity is $K_4=24*4 = 96$. The estimate for Simpson's Rule would then read:
$$\textrm{Error}(S_N) \leq\frac{96}{180\cdot 8^4} = 0.00013$$

That 4th power helps $S_N$ end up with a much smaller error, compared to the others.

**Question**: If we wanted to achieve an error less than $10^{-12}$ in this example, with Simpson's Rule, how many intervals $N$ should we use?
