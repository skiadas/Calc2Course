# Volumes

## Reading

6.2 Sections on Volume and Average Value (the sections on Density and Flow Rate are optional).

## Problems

- Practice Exercises: 6.2 3, 4, 5, 7, 9, 13, 16, 55, 57
- To turn in (on Monday along with those from 6.3): 6.2 10, 56

## Volumes via integrals

Suppose we have a solid object, whose cross-sections along an axis we can understand. For example in a pyramid, the cross-sections are all rectangles (or triangles depending on the pyramid), in a sphere the cross-sections are all circles.

Then we can express this as an integral, that looks something like this:

> $$V = \int_a^b A(y) dy$$
> where $A(y)$ is the area of the cross section.

This is possible because we can imagine the solid cut into smaller and smaller "cylinders", whose areas equal the height times the area of the base. We then add all these "volumes", and imagine cutting into finer and finer pieces. This process can always be seen as an integral:

> $$V = \lim_{N\to\infty} \sum_{i=1}^N A(y^*)\Delta y = \int_a^b A(y) dy$$

**Example:** Use this to compute the volume of a square-based pyramid with height $h$ and base side $a$.

1. Set up coordinates with $y$ axis going down the center of the pyramid, and $x$ axis parallel to a side. At $y=0$ the pyramid's base has side length $a$.
2. At a height $y$, so still $h - y$ away from the top, the side the cross-section can be computed by similar triangles as: $s(y) = (h - y) \times \frac{a}{h}$
3. We integrate:

    $$V = \int_0^h s(y)^2 dy = \int_0^h \left(a\frac{h-y}{h}\right)^2dy$$

4. First result: $V = a^2 \int_0^h \left(1 - \frac{y}{h}\right)^2dy$
5. To make computation easier, change coordinates: $u = 1 - \frac{y}{h}$. Then $dy = -hdu$ and the integral becomes:

    $$V = a^2 \int_1^0u^2 (-h) du = a^2 h \int_0^1 u^2 du = \frac{1}{3} h a^2$$


**Example 2:** Find the volume of a sphere of radius $R$. (Answer: $\frac{4}{3}\pi R^2$)

## The Average Value

Our goal here is to obtain a formula for the "average value" of a function $f(x)$ on an interval $[a,b]$.

There are different ways to approach this problem. A simple approach is this:

1. Imagine the interval $[a, b]$ split into $N$ equal pieces via points $a = x_0 < x_1 < ... < x_N = b$, exactly like we do for partitions.
2. Then it would be meaningful to consider the average of the function at these values (and for simplicity of the argument we remove the point $x_0$; the final result turns out to be unaffected).
3. That average would therefore equal:

    $$\frac{1}{N}\bigl(f(x_1) + f(x_2) + \cdots + f(x_N)\bigr)$$

4. Recall that $\frac{b-a}{N} = \Delta x$, so we can write that above average as:

    $$\frac{\Delta x}{b-a} \bigl(f(x_1) + f(x_2) + \cdots + f(x_N)\bigr) = \frac{1}{b-a}\sum_{i=1}^N f(x_i)\Delta x$$

5. Taking this process to the limit gives us an integral.
6. It is therefore reasonable to define the integral of the function on the whole region $[a,b]$ as the average:

    > The **average value** of the function $f(x)$ on the interval $[a, b]$ is defined as:
    > $$\textrm{Avg} = \frac{1}{b-a}\int_a^b f(x)dx$$

**Practice problem:** What is the average value of the function $f(x) = x^2$ on the interval $[0, 1]$?

One important result about the average value of an integral is the so-called *mean value theorem for integrals*:

> **Mean Value Theorem for Integrals**
>
> If $f(x)$ is continuous on $[a, b]$, then there exists a value $c\in[a, b]$ such that:
> $$f(c) = \frac{1}{b-a}\int_a^b f(x) dx$$
>
> In other words *the average value of a continuous function on an interval is always achieved as a value of the function somewhere in that interval*.

Proof:

- Let us denote the average value by $A = \frac{1}{b-a}\int_a^b f(x) dx$.
- As a continuous function, $f$ achieves both a maximum ($M$) and a minimum ($m$) somewhere on the interval $[a, b]$. So we have values $m$ and $M$, which are values of $f$ for some points $c$, $d$ inside $[a, b]$, and such that for all $x$ we have:

    $$m \leq f(x) \leq M$$

- Integrating the inequality from $a$ to $b$ we obtain:

    $$m ( b-a) \leq \int_a^b f(x) dx \leq M (b-a)$$

- But then this means that $m \leq A \leq M$.
- Since $m$ and $M$ are actually the function values $m=f(d_1)$ and $M=f(d_2)$, for some points $d_1,d_2\in[a,b]$, and since $f$ is continuous, the Intermediate Value Theorem guarantees for us that $A$ is also equal to a value $f(t)$ for some $t$ between $d_1$ and $d_2$, and hence some $t$ in $[a, b]$.

