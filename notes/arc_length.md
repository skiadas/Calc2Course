# Arc Length

## Reading

Section 9.1

## Problems

Practice Exercises: 9.1 5, 7, 9, 17, 18, 25, 33, 35

Exercises to turn in: 9.1 6, 10, 34, 36

## Arc Length

The methods of integration that we have seen so far can be used in the computation of the arc length of curves, as well as the surface area of surfaces. For now we focus on curves, and we want to somehow define the **length** of the curve $y=f(x)$ from $x=a$ to $x=b$.

The idea is simple:

- Divide the $x$-interval from $a$ to $b$ into a partition, $x_0=a < x_1 < x_2 < \cdots < x_N = b$.
- In each interval from $x_{i-1}$ to $x_i$, instead of using a rectangle to approximate an area, we use a straight line between the points $(x_{i-1}, y_{i-1} = f(x_{i-1}))$ and $(x_i, y_i = f(x_i))$ to approximate the function between those points.
- To approximate the length of the segment of the curve between those two points, we use the length of the straight line between those two points, namely: $$\sqrt{(x_i - x_{i-1})^2 + (y_i - y_{i-1})^2}$$
- The difference $x_i-x_{i-1} = \Delta x$ is the same quantity on each interval. The difference $y_i - y_{i-1} = f(x_i)-f(x_{i-1})$ can be estimated using the mean value theorem, as $$y_i - y_{i-1} = f(x_i)-f(x_{i-1}) = f'(c_i)(x_i - x_{i-1}) = f'(c_i)\Delta x$$ where $c_i$ is some unknown point between $x_{i-1}$ and $x_i$.
- In that case the estimate of the length of the straight line becomes: $$\sqrt{(\Delta x)^2 + (f'(c_i)\Delta x)^2} = \Delta x \sqrt{1 + f'(c_i)^2}$$
- We add all those estimates for each interval to obtain an estimate of the overall length: $$\sum_{i=1}^N \Delta x \sqrt{1 + f'(c_i)^2}$$
- We then imagine taking a limit at $N\to\infty$. These sum expressions are exactly the **Riemann sums** of the integral: $$\int_a^b \sqrt{1+f'(x)^2}dx$$

It therefore makes sense to define the length thus:

> If $f'(x)$ exists and is continuous on the interval $[a,b]$, then we define the **length of the curve** $y=f(x)$ from $a$ to $b$ is defined as:
> $$\int_a^b \sqrt{1+f'(x)^2}dx$$

As a simple example, consider the circle of radius $R$ centered at $0$, and its segment that is above the $x$ axis. This can be represented by the curve $y=f(x)=\sqrt{R^2-x^2}$ from $x=-R$ to $x=R$. We start by computing
$$f'(x) = \frac{-x}{\sqrt{R^2-x^2}}$$
The length would then be given as the integral
$$\int_{-R}^R \sqrt{1+f'(x)^2}dx$$
Now we have:
$$1+f'(x)^2 = 1 + \frac{(-x)^2}{R^2-x^2} = \frac{R^2}{R^2-x^2}$$
So the integral becomes:
$$\int_{-R}^R \frac{R}{\sqrt{R^2-x^2}}dx$$
This requires a trigonometric substitution $x = R\sin u$:
$$\int_{-\pi/2}^{\pi/2}\frac{R}{R\cos u} R\cos u du = R\pi$$
This is as expected: The whole perimeter of the circle is supposed to equal $2\pi R$.

As an extension of the above example, suppose we wanted to compute the arc length as a function of $x$, starting from $x=R$. Then we can think of that as the following function of $a$:
$$\int_a^R\sqrt{1+f'(x)^2}dx$$
and with computations as above we would end up with the integral
$$\int_{\sin^{-1}(a/R)}^{\pi/2}\frac{R}{R\cos u} R\cos u du = R\pi/2-R\sin^{-1}(a/R)= R\cos^{-1}(a/R)$$

In other words, we can think of the cosine as measuring the arc length on the circle starting from the $x$ axis.

### Area of Surfaces of Revolution

A similar approach provides us with a formula for the area of a surface of revolution:

> If $f(x)\geq 0$ and $f'(x)$ is defined and continuous on the interval $[a,b]$, then the area of the surface produced by the revolution of $f$ around the $x$ axis is given by:
> $$A = 2\pi\int_a^b f(x) \sqrt{1 + f'(x)^2}dx$$

Practice: Calculate the surface area of a sphere of radius $R$. You should find it to be $4\pi R^2$.
