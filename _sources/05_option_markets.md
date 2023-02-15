# Mechanics of option market and properties of options

<!-- 
-
from 01_introduction

Options

Options

A call option is an option to buy a certain asset by a certain date for a certain price
(the strike price)
A put option is an option to sell a certain asset by a certain date for a certain price
(the strike price)
An American option can be exercised at any time during its life
A European option can be exercised only at maturity

T. Plíhal

· Introduction to Financial Derivatives · February 14, 2022

30 / 45

Options

Options vs Futures/Forwards

A futures/forward contract gives the holder the obligation to buy or sell at a certain
price
An option gives the holder the right to buy or sell at a certain price

T. Plíhal

· Introduction to Financial Derivatives · February 14, 2022

31 / 45

Options

Google Call Option Prices
Google Call Option Prices from CBOE (May 3, 2016; Stock Price is bid 695.86, offer
696.25);

T. Plíhal

· Introduction to Financial Derivatives · February 14, 2022

32 / 45

Options

Google Put Option Prices
Google Put Option Prices from CBOE (May 3, 2016; Stock Price is bid 695.86, offer
696.25);

T. Plíhal

· Introduction to Financial Derivatives · February 14, 2022

33 / 45

Types of Trades

Table of Contents


## Contingent Claims/Options Summary ##
- An option is a derivative contract in which one party, the buyer, pays a sum
    of money to the other party, the seller or writer, and receives the right
    to either buy or sell an underlying asset at a fixed price either on a
    specific expiration date or at any time prior to the expiration date.

- A **call** is an option that provides the right to **buy** the underlying.

- A **put** is an option that provides the right to **sell** the underlying.

Put and call options may be *American style* or *European style*.

## Option Definition ##
An **option** is a derivative contract in which one party, the buyer, pays a
sum of money to the other party, the seller or writer, and receives the right
to either buy or sell an underlying asset at a fixed price either on a specific
expiration date or at any time prior to the expiration date.

There are two types of options:

- **Call Option:** grants the holder the right to **buy** the underlying asset
    at a fixed price (called the exercise price or strike price) either on the
    expiration date or at any time prior to the expiration date.

- **Put Option:** grants the holder the right to **sell** the underlying asset
    at a fixed price (called the exercise price or strike price) either on the
    expiration date or at any time prior to the expiration date.

Put and call options may be *American style* or *European style*.

## Option Payoffs ##
Assumptions and symbol definitions:

- $S_T$: the price of the underlying at the expiration date $T$

- $X$: the exercise price of the option

Payoff to the call buyer: $c_T = Max(0, S_T - X)$

Payoff to the put buyer: $p_T = Max(0, X - S_T)$


## Option Payoff Example ##
At expiration the underlying asset price $S_T$ is \$28. If the strike price X
is \$25, what is the payoff of the put and call?

Payoff to the call buyer:
$$c_T = Max(0, S_T - X) = Max(0, \$28 - \$25) = \$3$$

Payoff to the put buyer:
$$p_T = Max(0, X - S_T) = Max(0, \$25 - \$28) = 0$$

When the option has a positive payoff it is said to be **in the money**. In the
example above, the call option is **in the money**. The put option is **out of
the money** because $X - S_T$ is less than 0. When $S_T = X$, the option is
said to be **at the money**.


## Option Profit ##
Since option buyer must pay a price (or **option premium**), the profit is
computed by subtracting the option premium from the option payoff.

Assumptions and symbol definitions:

- $S_T$: the price of the underlying at the expiration date $T$ 

- $X$: the exercise price of the option

- $c_0$: the price (premium) of the call option

- $p_0$: the price (premium) of the put option

Profit to the call buyer: $\Pi = Max(0, S_T - X) - c_0$

Profit to the put buyer: $\Pi = Max(0, X - S_T) - p_0$


## Option Profit Example ##
Assume that a put and call on CBX stock both have a strike price $X = \$30$. The
call initially costs \$1, and the put costs \$2.

What is the profit on the call and put if the price of CBX stock at expiration
($S_T$) is \$27.50?

Profit to the call buyer: 
$$ \Pi = Max(0, S_T - X) - c_0 = Max(0, \$27.5 - \$30) - \$1 = -\$1 $$

Profit to the put buyer: 
$$ \Pi = Max(0, X - S_T) - p_0 = Max(0, \$30 - \$27.5) - \$2 = \$0.5 $$

# Options

::: {.frame}
Options

-   A **call option** is an option to buy a certain asset by a certain
    date for a certain price (the strike price)

-   A **put option** is an option to sell a certain asset by a certain
    date for a certain price (the strike price)

```{=html}
```
-   An **American option** can be exercised at any time during its life

-   A **European option** can be exercised only at maturity
::: -->