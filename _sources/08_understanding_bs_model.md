# Understanding $N(d_1)$ and $N(d_2)$

## Interpretation #1

- $N(d_2) \dots$ Probability of exercise (at maturity).
- $S_0 e^{rT} N(d_1) \dots$ The expected stock price at maturity in a
risk-neutral world when stock prices less than the strike price are counted as
zero.
- The expected payoff is therefore:

$$S_0 e^{rT} N(d_1) - K N(d_2)$$

- Calculate present value to get:

$$c = S_0 N(d_1) - K e^{-rT} N(d_2)$$

## Interpretation #2

$$c = e^{-rT} N(d_2) \left( S_0 e^{rT} N(d_1) / N(d_2) - K \right)$$

- $e^{-rT} \dots$ Present value factor.
- $N(d_2) \dots$ Probability of exercise (at maturity).
- $S_0 e^{rT} N(d_1) / N(d_2) \dots$ Expected stock price in a risk-neutral
world if option is exercised.
- $K \dots$ Strike price paid if option is exercised.

## Properties of Black-Scholes Formula

- As $S_0$ becomes very large:
    - $c$ tends to $S_0 - Ke^{-rT}$ because $d_1$ and $d_2$ become very large, and $N(d_1)$ and $N(d_2)$ become close to 1.
    - $p$ tends to zero because $N(-d_1)$ and $N(- d_2)$ become close to 0.

+ As $S_0$ becomes very small
    - $c$ tends to zero.
    - $p$ tends to $Ke^{-rT} - S_0$.