# Area between Graphs

## Reading

Section 6.1. Pay particular attention to the difference between integrating along the $x$-axis and integrating along the $y$-axis.

## Problems

Practice Exercises: 6.1 1, 3, 5, 13, 19, 21, 29, 33

Exercises to turn in (due on Wednesday): 6.1 14, 20, 26, 34

## Area between Graphs

Suppose we have two functions, $f(x)$ and $g(x)$, and we want to compute the area between them.

If we follow our standard methodology for integrals, we could:

- Imagine cutting the x-interval up into tiny intervals.
- For each of these intervals, the desired area can be approximated by a rectangle, whose height is the positive difference between the two functions, and whose width is the corresponding $\Delta x$ width.
- So mathematically that area is like $\left|f(x) - g(x)\right|\Delta x$.
- Adding all these together gives total area.
- Taking the limit of this process gives us an integral.

> The area between two curves $f(x)$ and $g(x)$ and the points $x=a$ and $x=b$ is given by:
>
> $$\int_a^b \left|f(x) - g(x)\right| dx$$

**Example 1:** Write the integral that computes the area between the circle of unit radius centered at $1$ and the line $y + x = 1$.

**Example 2:** Write the integral that computes the area between the curves $y=x^2$ and $y=1-x^2$ and the $y$ axis.

## Variations

There are two variations that complicate matters. The first is that some times the curves under consideration are best described as functions of $y$ rather than $x$. Then the formula is essentially the same:

> $$\int_c^d \left|g(y) - h(y)\right| dy$$

Example: Compute the area of the region enclosed by the curves $y^2 = x + 5$ and $y^2 = 3 - x$.

Other times the area surrounded by the curves is more complex and you have to break the range up into pieces, then compute each piece via one of the aforementioned methods.

Example: Compute the area of the region enclosed by the curves $x + y = 4$, $x - y = 0$ and $y + 3x = 4$.

Practice problems in class: 6.1 21, 29, 59
