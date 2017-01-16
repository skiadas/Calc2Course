# The Shell Method

## Reading

Section 6.4

## Problems

- Practice Exercises: 7, 9, 10, 15, 16, 21, 22, 23, 39, 41, 42
- Exercises to turn in (on Wednesday): 6.4 8, 40, 44, 46

## The Shell Method

The Shell Method, like the Disc Method, deals with solids created by the revolution of some curve/function around some axis. But it works in sort of the opposite direction. Let's explain.

Consider the triangle formed by $x+y=1$, $y=0$ and $x=0$. Say we rotate this region around the $y$-axis and we want to find out the area of the resulting solid.

With the disc method, we need to write our curve, $x+y=1$, as a function of $y$, the variable that we are rotating around. So we have the function $x=1-y$. Then the cross-sections perpendicular to the $y$ axis are circles with radius $1-y$, so we can write the integral, using the disc method, as:

$$\pi\int_0^1 (1-y)^2 dy$$
which we can compute to equal $\frac{\pi}{3}$.

Now the Shell method is different. It will try to integrating along the $x$-axis instead. To do that, imagine cutting the interval in $x$ into many tiny segments. One such segment would be going from say $x$ to $x+\Delta x$. The solid we are after that corresponds to this segment is the little area above this segment and below the $y=1-x$ line, which is roughly a rectangle with base $\Delta x$ and height $1-x$, but rotated around the $y$ axis. This results in effect in two cylinders, the outer and the inner, and we look at their differences:

$$\pi (x+\Delta x)^2 (1-x) - \pi x^2 (1-x) = \pi(1-x)\left((x+\Delta x)^2-x^2\right)$$

We need to understand the quantity $(x+\Delta x)^2 - x^2$ more. Let's expand it out, as it is a difference of squares:

$$(x+\Delta x)^2 - x^2 = (x+\Delta x +x)(x+\Delta x - x) = (2x +\Delta x)\Delta x$$

Now here we are thinking of the $\Delta x$ as a tiny, infinitesimal quantity. In which case $2x+\Delta x$ is really the same as $2x$. So at the end of the day the volume of the cylinder for that particular $x$ is:

$$2\pi (1-x) x \Delta x$$

We then add up all these little cylinders and integrate:

$$V = 2\pi \int_0^1 x(1-x)dx = 2\pi\int_0^1 x - x^2dx = \frac{\pi}{3}$$

Good, we get the same answer, as we should.

In general, the formula for the Shell method would read:

> Volume of the solid produced by rotating the area under $y=f(x)$ around the $y$ axis.
> $$V = 2\pi \int_a^b x f(x)dx$$

### Shell vs Disc

So when to use which method? That depends on which way of the function is easier. In general:

> You can compute a solid of revolution around the $y$ axis via:
>
> - the shell method if you have the boundary as a function $y=f(x)$, or
> - the disc method if you have the boundary as a function $x=g(y)$.
>
> The Disc method uses the same variable of integration as the axis of rotation, the Shell method uses the other axis.
