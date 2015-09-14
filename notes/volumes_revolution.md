# Volumes of Revolution

## Reading

Section 6.3

## Problems

Practice Exercises: 6.3 8, 9, 13, 14, 15, 21, 23, 25
In class: 27, 28, 31

Exercises to turn in (along with those from 6.4): 6.3 24, 40

## Volumes of Revolution

Recall that last time we expressed a volume as an integral of an "area function":

> $$V = \int_a^b A(x) dx$$

where $A(x)$ is the area of the cross section.

Volumes of Revolution follow a similar idea, but they are used in a more specialized form:

> A solid of revolution is formed by rotating, the region under the graph of a function $y=f(x)$ around the $x$ axis. The volume of such a solid can be found as:
>
> $$V = \pi \int_a^b f(x)^2dx$$

For example, the sphere of radius $R$ can be thought of as a solid of revolution, where the function $f(x)$ is $\sqrt{R^2 - x^2}$. So we can compute the volume of the sphere via the integral:

$$\pi\int_{-R}^{R}\left(\sqrt{R^2 - x^2}\right)^2 dx = \pi \int_{-R}^R R^2 - x^2 dx$$

If you finish the computation you will find the result to be the well known formula $V =\frac{4}{3}\pi R^3$.

This is often called the **disc method**.

A slight variation of it, called the **washer method**, describe the solid created by the revolution of the area *between* two functions $f(x)$ and $g(x)$. You can think of it as the volume of the solid produced by $f(x)$ alone, with the volume of the solid produced by $g$ removed. The formula would be:

> $$V = \pi \int_a^b f(x)^2 - g(x)^2 dx$$

Take note of the integrand!! We do not take the difference of $f$ and $g$, and then square it. We first square them, then take the difference.

Special care needs to be taken when rotating around an axis other than the $x$ axis itself. For instance one might want to rotate around the axis $y = 1$ or the axis $y = -3$. In all cases the rule is:

> $$ V = \pi \int_a^b R_{\textrm{outer}}^2 - R_{\textrm{inner}}^2 dx$$

So take the "largest radius", namely the distance from your function to the axis of rotation, and substract the "smallest radius", which may be $0$ or may be the distance of another function $g$ from the axis of rotation.
