# Compound Interest

## Reading

Section 7.5

## Problems

Practice Exercises: 7.5 1, 2, 3, 4, 5

Exercises to turn in (along with those from 7.3 and 7.4): 7.5 6

## Compound Interest

In finance there is an interest concept called "compound interest". The basic idea is simple:

You have a *principal*, your starting amount of money, $P_0$. Then over time you accrue interest based on a fixed annual *rate* $r$. So after a year the *balance* on the account would be:
$$P_0 + P_0\times r = P_0(1+r)$$
Now what would happen if the interest is instead accrued every semester? This typically means that you also have an interest amount $\frac{r}{2}$ applied. After the first six months the balance would be:
$$P_0\left(1+\frac{r}{2}\right)$$
For the next 6 months, the interest would be accrued on this increased balance, so at the end of the year we would have made:
$$P_0\left(1+\frac{r}{2}\right)\left(1+\frac{r}{2}\right) = P_0\left(1+\frac{r}{2}\right)^2$$

What if we accrue the interest more often, say $M$ times during the year? Then the formula, with very similar logic, becomes:
$$P_0\left(1+\frac{r}{M}\right)^M$$

As $M$ gets larger, this quantity grows. That is not immediately clear, as even though the exponent increases, the base gets closer and closer to $1$. There must be a certain balance between the two. In fact there is. Turns out that the following is true:
$$e^r = \lim_{n\to +\infty}\left(1+\frac{r}{n}\right)^n$$

This is what we do in the case of **compound interest**. We assume that the interest is accrued "continuously", so as if the number $M$ of times in a year is very very large. In that case, we can work out the formula for the balance as
$$P_0 e^{r}$$
and after time $t$ years:
$$P(t) = P_0 e^{rt}$$

In other words, *continously compounded interest grows exponentially*.

### Proof of formula for exponential

All this is based on the remarkable formula:

> $$e^x = \lim_{n\to +\infty}\left(1+\frac{x}{n}\right)^n$$

We will now prove this formula. The first observation is that we can take logarithms on both sides, and then we can pass the logarithm through the limit (because it is a continuous function). Using the properties of logarithms, the equation becomes instead:

> $$x = \lim_{n\to +\infty} n\ln\left(1 + \frac{x}{n}\right)$$

We will now demonstrate this formula, at least for $x > 0$. We will do so by figuring out bounds for $\ln\left(1 + \frac{x}{n}\right)$. This follows from the fact that the logarithm is defined as an integral:
$$\ln\left(1 + \frac{x}{n}\right) = \int_1^{1+\frac{x}{n}}\frac{1}{t}dt$$

We can get bounds for that integral by figuring out what the largest and smallest values of the function $\frac{1}{x}$ on that interval would be. This is easy since the function is decreasing. In our case, the smallest value is at $1+\frac{x}{n}$, and it is equal to $\frac{n}{n+x}$, and the largest value is at $1$, and it is $\frac{1}{1} = 1$. The general rule we will use is:
$$m(b-a)\leq\int_a^bf(x)dx\leq M(b-a)$$
In our case this says:
$$\left(1+\frac{x}{n} - 1\right)\times \frac{n}{n+x}\leq\ln\left(1 + \frac{x}{n}\right)\leq \left(1+\frac{x}{n} - 1\right)\times 1$$
We multiply by $n$, as that is what interests us:
$$x\frac{n}{n+x}\leq n\ln\left(1 + \frac{x}{n}\right)\leq x$$

As $n$ goes to infinity, the quantity on the left approaches $x$, as does the one on the right. By the squeeze theorem, the quantity in the middle must also. And this is what we were trying to establish.
