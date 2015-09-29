# Exponential Growth and Decay

## Reading

Section 7.4

## Problems

Practice Exercises: 7.4 2, 3, 6, 9, 11, 12, 13, 14, 23, 25

Exercises to turn in (along with those from 7.3 and 7.5): 7.4 24

## Exponential Growth and Decay

A number of physical phenomena can be described via growth and decay. The reason for that is simple.

> If the law that describes a physical quantity $P(t)$ over time is that **the rate of change of the quantity is proportional to its current size**, then that quantity is determined by an equation
> $$P'(t) = k P(t)$$
> whose solution necessarily has the form:
> $$P(t) = P_0 e^{kt}$$
>
> If $k > 0$ we have **exponential growth**, if $k < 0$ we have **exponential decay** and usually write the equation using a positive $k$, and as:
> $$P(t) = P_0 e^{-kt}$$

The quantity $k$ is measured in units inverse to the ones used for time.

As a quick example, suppose that we look at E-coli bacteria in a lab. Their growth constant is $k=0.41\textrm{hours}^{-1}$. Suppose we have $1000$ bacteria present at the start. That is $P_0=1000$. Then after one hour, we would have:
$$P_0e^k = 1000\times e^{0.41} = 1507$$
bacteria. After 4 hours, it would be:
$$P_0e^{4k} = 1000\times e^{1.64} = 5155$$ bacteria. And so on.

We can also ask for example when we will have say 20 times the number of bacteria, i.e. $P(t) = 20000$. We then have an equation:
$$1000e^{kt} = 20000$$
or
$$e^{kt} = 20$$
or
$$t = \frac{\ln(20)}{k} = \frac{2.9957}{0.41} = 7.3$$
so in about $7.3$ hours.

### Doubling-time Half-time

An important quantity in exponential growth/decay problems is the half-time or doubling-time, namely the time it takes for the population to be cut in half (or to be doubled if we have growth). That quantity only depends on the decay/growth rate $k$. That time is easy to find:

In order to have $P(t) = 2 P_0$ we must have $e^{kt} = 2$, or:
$$t = \frac{\ln(2)}{k}$$

Similarly for a exponential decay problem $P(t) = P_0 e^{-kt}$. In order to have $P(t) = \frac{1}{2} P_0$ we must have $e^{-kt} = \frac{1}{2}$, or the same $t$ as above.

In the example of the E-coli bacteria, doubling will occur after $\frac{\ln(2)}{0.41} = 1.69$ hours. And from there on the bacteria will double every two hours.

### Carbon Dating

Exponential decay is very useful in dating artifacts, via a technique called carbon dating. Every living organism contains carbon in two forms: $C^{14}$ is radioactive and decays over time, $C^{12}$ does not. Living organisms contains these two molecules in the same proportions, because they obtain them from the atmosphere. Once an organism dies, these carbon molecules are no longer updated from the atmosphere. Therefore if we measure the proportion of $C^{14}$ present compared to $C^{12}$, we can estimate the time that has elapsed since the organism died.

In general, we have:
$$\textrm{Ratio of }C^{14}\textrm{ to }C^{12} = R_\textrm{atm} e^{-kt}$$
where the decay constant is $k = 0.000121$ and $t$ is measured in years.

Let us do an example of this: Some cave paintings in Francy had a $C^{14}$-to-$C^{12}$ ratio that was $15\%$ of that found in the atmosphere, $R_\textrm{atm}. Using the formula above we have:
$$0.15 = e^{-kt}$$
or $t = -\frac{\ln(0.15)}{k} = - \frac{-1.89712}{0.000121} = 15679$. So these paintings were created around $16000$ years ago.



