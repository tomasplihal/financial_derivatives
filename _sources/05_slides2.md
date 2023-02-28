---
author:
- |
  Tomáš Plíhal\
  tomas.plihal@econ.muni.cz
bibliography:
- example.bib
date: 2023-02-21
title: Trading Strategies Involving Options
---

::: frame
:::

::: frame
Table of contents \[sections numbered\]
:::

::: frame
References HULL, John. 2018. Options, futures, and other derivatives.
Ninth edition. Harlow: Pearson. ISBN 978-1-292-21289-0.

-   Chapter 12. Trading Strategies Involving Options
:::

# Trading Strategies Involving Options

::: frame
Strategies to Be Considered

-   Bond plus option to create principal protected note

-   Stock plus option

-   Two or more options of the same type (a spread)

-   Two or more options of different types (a combination)
:::

# Principal Protected Note

::: frame
Principal Protected Note

-   Allows investor to take a risky position without risking any
    principal.

-   Example: USD 1000 instrument consisting of:

    1.  3-year zero-coupon bond with principal of USD 1000

    2.  3-year at-the-money call option on a stock portfolio
:::

::: frame
Example: Principal Protected Note

-   Suppose that the 3-year interest rate is 6% with continuous
    compounding.

-   This means that $1,000 e^{-0.06 \times 3} = 835.27$ will grow to
    \$1,000 in 3 years.

-   The difference between \$1,000 and \$835.27 is \$164.73.

-   Suppose that a stock portfolio is worth \$1,000 and provides a
    dividend yield of 1.5% per annum.

-   Suppose further that a 3-year at-the-money European call option on
    the stock portfolio can be purchased for less than \$164.73.
:::

::: frame
Principal Protected Notes **Viability depends on:**

-   Level of dividends

-   Level of interest rates

-   Volatility of the portfolio

**Variations on standard product:**

-   Out of the money strike price

-   Caps on investor return

-   Knock outs, averaging features, etc
:::

# Stock & Option

::: frame
Positions in an Option & the Underlying

::: center
![image](images/07-1-option-and-underlying.png){width="2.45in"}
:::
:::

::: frame
Positions in an Option & the Underlying

-   The profit patterns in the previous figure have the same general
    shape as the profit patterns of options.

-   a\) short put, b) long put, c) long call, d) short call

-   It can be explained by the put-call parity
    $$p + S_0 = c + K e^{-rT} + D$$
:::

# Spreads

::: frame
Bull Spread Using Calls

::: center
![image](images/07-2-bull-spread-calls.png){width="4in"}
:::
:::

::: frame
Bull Spread Using Puts

::: center
![image](images/07-3-bull-spread-puts.png){width="4in"}
:::
:::

::: frame
Bear Spread Using Puts

::: center
![image](images/07-4-bear-spread-puts.png){width="4in"}
:::
:::

::: frame
Bear Spread Using Calls

::: center
![image](images/07-5-bear-spread-calls.png){width="4in"}
:::
:::

::: frame
Box Spread

-   A combination of a bull call spread and a bear put spread

-   If all options are European a box spread is worth the present value
    of the difference between the strike prices

-   If they are American this is not necessarily so (see Business
    Snapshot 11.1)
:::

::: frame
Butterfly Spread Using Calls

::: center
![image](images/07-6-butterfly-spread-calls.png){width="4in"}
:::
:::

::: frame
Butterfly Spread Using Puts

::: center
![image](images/07-7-butterfly-spread-puts.png){width="4in"}
:::
:::

::: frame
Calendar Spread Using Calls

::: center
![image](images/07-8-calendar-spread-calls.png){width="3.8in"}
:::
:::

::: frame
Calendar Spread Using Puts

::: center
![image](images/07-9-calendar-spread-puts.png){width="4in"}
:::
:::

# Combinations

::: frame
A Straddle Combination

::: center
![image](images/07-10-straddle.png){width="4in"}
:::
:::

::: frame
Strip & Strap

::: center
![image](images/07-11-strip-strap.png){width="5in"}
:::
:::

::: frame
A Strangle Combination

::: center
![image](images/07-12-strangle.png){width="4in"}
:::
:::

::: frame
Other Payoff Patterns

-   When the strike prices are close together a butterfly spread
    provides a payoff consisting of a small \"spike\".

-   If options with all strike prices were available any payoff pattern
    could (at least approximately) be created by combining the spikes
    obtained from different butterfly spreads.
:::
