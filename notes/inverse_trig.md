# Inverse Trigonometric Functions

## Reading

Section 7.8

## Problems

Practice Exercises: 7.8 1-6, 7-12, 17, 18, 21, 23, 29, 30, 33, 35, 37, 53, 57, 59, 61, 63, 70, 71

Exercises to turn in (along with those from 7.9): 7.8 22, 38, 60

## Inverse Trigonometric Functions

As you know, trigonometric functions are periodic, with period $2\pi$, i.e. their values repeat every $2\pi$. This prevents the function from being one-to-one.

In order to obtain an invertible function we must restrict to an interval:

> The function
> $$\sin\colon \left[-\frac{\pi}{2}, \frac{\pi}{2}\right]\to [-1, 1]$$
> is invertible. Its inverse is the inverse sine function:
> $$\sin^{-1}\colon[-1,1]\to\left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$$
>
> In other words, $\sin^{-1}(x)$ is the unique $y\in\left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$ such that $\sin(y) = x$.

In order to remember the basic trigonometric numbers, it is good to keep the following two triangles in mind:

![Triangles for trig numbers](images/trigTriangles.png)

For example, $\sin\left(\frac{\pi}{3}\right) = \frac{\sqrt{3}}{2}$. We can read this conversely to say that $\sin^{-1}\left(\frac{\sqrt{3}}{2}\right) = \frac{\pi}{3}$.

Note that in general $\sin^{-1}\left(\sin(x)\right)\neq x$. This is only true if $x$ is in the specific interval $\left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$. If it is not, we have to convert it, using the periodicity if $\sin$, turning every angle into the range $\left[-\frac{\pi}{2}, \frac{\pi}{2}\right]$.

For instance, consider $\sin^{-1}(\sin(\frac{5\pi}{3}))$. since $\frac{5\pi}{3} = \frac{6\pi}{3} - \frac{\pi}{3} = 2\pi - \frac{\pi}{3}$, we have that $\sin\left(\frac{5\pi}{3}\right) = \sin\left(\frac{-\pi}{3}\right)$. Therefore that would be the answer:
$$\sin^{-1}(\sin(\frac{5\pi}{3})) = \frac{-\pi}{3}$$

We have similar definitions for $\cos^{-1}$ and $\tan^{-1}$:

> The function
> $$\cos\colon \left[0, \pi\right]\to [-1, 1]$$
> is invertible. Its inverse is the inverse cosine function:
> $$\cos^{-1}\colon[-1,1]\to\left[0, \pi\right]$$
>
> In other words, $\cos^{-1}(x)$ is the unique $y\in\left[0, \pi\right]$ such that $\cos(y) = x$.

> The function
> $$\tan\colon \left(-\frac{\pi}{2}, \frac{\pi}{2}\right)\to (-\infty,\infty)$$
> is invertible. Its inverse is the inverse tangent function:
> $$\tan^{-1}\colon (-\infty,\infty)\to\left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$$
>
> In other words, $\tan^{-1}(x)$ is the unique $y\in\left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$ such that $\tan(y) = x$.

An important question is how to combine for instance $\cos$ and $\sin^{-1}$. We have the following result:

> $$\cos\left(\sin^{-1}(x)\right) = \sqrt{1-x^2}$$
> $$\tan\left(\sin^{-1}(x)\right) = \frac{x}{\sqrt{1-x^2}}$$

The idea for this result is as follows: Draw a right angle triangle where the hypotenuse is equal to $1$ and a side is $x$. Then the angle opposite that side is exactly $\sin^{-1}(x)$. Now by the pythagorean theorem, the third side of that triangle has to have length $\sqrt{1-x^2}$.

From that triangle we can now read the cosine and tangent of that angle. This gives us the above formulas. It also gives us the following:

> $$\sin^{-1}(x) + \cos^{-1}(x) = \frac{\pi}{2}$$

This is because the same triangle that gives us the sine as $x$ for one of the non-right angles, gives us the cosine as $x$ for the other non-right angle, and those two need to add up to $\frac{\pi}{2}$.

A consequence of these formulas is that we can figure out the derivatives of the inverse trigonometric functions:

> **Derivatives of inverse trigonometric functions**
> $$\frac{d}{dx}\sin^{-1}(x) = \frac{1}{\sqrt{1-x^2}}$$
> $$\frac{d}{dx}\cos^{-1}(x) = -\frac{1}{\sqrt{1-x^2}}$$
> $$\frac{d}{dx}\tan^{-1}(x) = \frac{1}{1+x^2}$$

Let us prove these using the formula for the derivative of the inverse of a function:

$$\frac{d}{dx}\sin^{-1}(x) = \frac{1}{\sin'\left(\sin^{-1}(x)\right)} = \frac{1}{\cos\left(\sin^{-1}(x)\right)} = \frac{1}{\sqrt{1-x^2}}$$

And a similar formula works for the inverse tangent:

$$\frac{d}{dx}\tan^{-1}(x) = \frac{1}{\tan'\left(\tan^{-1}(x)\right)} = \frac{1}{\sec^2\left(\tan^{-1}(x)\right)} =\frac{1}{1+x^2}$$

The last step follows by considering a right-angle triangle with one side $x$ and another $1$, and hence the hypotenuse is $\sqrt{1+x^2}$. The secant of the angle with tangent $x$ would then be exactly $\sqrt{1+x^2}$.

### Basic Integral Formulas

These derivatives can be read backwards as facts about integrals. The two most relevant to us are:

> $$\frac{dx}{\sqrt{1-x^2}} = \sin^{-1}(x) + C$$
> $$\frac{dx}{1+x^2} = \tan^{-1}(x) + C$$

These are often preceded by a $u$ substitution. For example, suppose we want to compute:
$$\int_{-3/4}^0\frac{dx}{\sqrt{9-16x^2}}$$
Looking at that denominator, it looks a bit like a $\sqrt{1-u^2}$, except it's got some extra numbers all around. Let us rewrite it a bit:
$$\int_{-3/4}^0\frac{dx}{\sqrt{9}\sqrt{1-\left(\frac{4x}{3}\right)^2}}$$
So it makes sense to set $u=\frac{4x}{3}$. Then $du = \frac{4}{3}dx$, and the interval becomes:
$$\int_{-1}^0\frac{\frac{3}{4}du}{3\sqrt{1-u^2}} \frac{1}{4}\left(\sin^{-1}(0)-\sin^{-1}(-1)\right) = -\frac{1}{4}\left(-\frac{\pi}{2}\right) = \frac{\pi}{8}$$

