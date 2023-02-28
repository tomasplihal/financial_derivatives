---
author:
- |
  Tomáš Plíhal\
  tomas.plihal@econ.muni.cz
bibliography:
- example.bib
date: 2023-02-21
title: Binomial Trees
---

::: frame
:::

::: frame
Table of contents \[sections numbered\]
:::

::: frame
References HULL, John. 2018. Options, futures, and other derivatives.
Ninth edition. Harlow: Pearson. ISBN 978-1-292-21289-0.

-   Chapter 13. Binomial Trees

Cox, J. C., S. A. Ross, and M. Rubinstein. \"Option Pricing: A
Simplified Approach,\" *Journal of Financial Economics* 7 (October
1979): 229--64.
:::

# A One-Step Binomial Model and A No-Arbitrage Argument

::: frame
A Simple Binomial Model - Call option

-   A 3-month call option on the stock has a strike price of \$21

-   A stock price is currently \$20

-   In 3 months it will be either \$22 or \$18

::: center
![image](images/07-13-simple-binomial-model.png){width="3.2in"}
:::
:::

::: frame
Setting Up a Riskless Portfolio

-   For a portfolio that is long $\Delta$ shares and a short 1 call
    option

-   Calculate the value of $\Delta$ that makes the portfolio riskless
    $$22 \Delta - 1 = 18 \Delta - 0$$ $$\Delta = 0.25$$

-   A riskless portfolio is therefore Long 0.25 shares + short 1 option.
:::

::: frame
Valuing the Portfolio (Risk-Free Rate is 4%)

-   The riskless portfolio is: long 0.25 shares and short 1 call option

-   The value of the portfolio in 3 months is:
    $$22 \times 0.25 - 1 = 4.50$$

-   The value of the portfolio today is:
    $$4.5e^{-0.04 \times 0.25} = 4.455$$
:::

::: frame
Valuing the Option

-   The portfolio that is long 0.25 shares and short 1 option is worth
    4.455

-   The value of the shares is 5.000 ($= 0.25 \times 20$)

-   The value of the option is therefore 5.000 -- 4.455 = 0.545
:::

::: frame
Generalization

::: center
![image](images/07-14-generalization.png){width="3.3in"}
:::
:::

::: frame
Generalization The value of the portfolio at the end of the life of the
option is:

-   If there is an up movement $= S_0u\Delta - f_u$

-   If there is a down movement $=S_0d\Delta - f_d$

-   The portfolio is riskless when
    $$S_0 u \Delta - f_u = S_0 d \Delta - f_d$$
    $$\Delta = \frac{f_u - f_d}{S_0 u - S_0 d}$$

-   In this case, the portfolio is riskless and, for there to be no
    arbitrage opportunities, it must earn the risk-free interest rate.

-   It shows that $\Delta$ is the ratio of the change in the option
    price to the change in the stock price as we move between the nodes
    at time $T$.
:::

::: frame
Generalization

-   Value of the portfolio at time $T$ is $$S_0 u \Delta - f_u$$

-   Value of the portfolio today is $$(S_0 u \Delta - f_u)e^{-rT}$$

-   The cost of setting up the portfolio today (another expression for
    the portfolio value today) is $$S_0 \Delta - f$$

-   Hence $$f = S_0 \Delta - (S_0 u \Delta - f_u)e^{-rT}$$
:::

::: frame
Generalization Substituting for $\Delta$ we obtain:
$$f = [pf_u + (1 - p)f_d]e^{-rT}$$

where $$p = \frac{e^{rT} - d}{u - d}$$
:::

::: frame
$p$ as a Probability

-   It is natural to interpret $p$ and $1-p$ as probabilities of up and
    down movements.

-   The value of a derivative is then its expected payoff in a
    risk-neutral world discounted at the risk-free rate.
:::

::: frame
Example

-   In the numerical example considered previously we have:

-   $u = 1.1$, $d=0.9$, $r=0.04$, $T=0.25$, $f_u = 1$, and $f_d = 0$

$$p = \frac{e^{0.04 \times 0.25} - 0.9}{1.1 - 0.9} = 0.5503$$

$$f = e^{-0.04 \times 0.25} (0.5503 \times 1 + 0.4497 \times 0) = 0.545$$
:::

# Risk-Neutral Valuation

::: frame
Risk-Neutral Valuation

-   When the probability of an up and down movements are $p$ and $1-p$
    the expected stock price at time $T$ is $S_0e^{rT}$

-   This shows that the stock price earns the risk-free rate.

-   Binomial trees illustrate the general result that to value a
    derivative we can assume that the expected return on the underlying
    asset is the risk-free rate and the discount rate is also the
    risk-free rate.

-   This is known as using risk-neutral valuation.
:::

::: frame
Example Revisited

-   In the numerical example considered previously we have:

-   $u = 1.1$, $d=0.9$, $r=0.04$, $T=0.25$, $f_u = 1$, and $f_d = 0$
    $$22p + 18(1-p) = 20 e^{0.04 \times 0.25} \Rightarrow  p = 0.5503$$

-   At the end of the 3 months, the call option has a 0.5503 probability
    of being worth 1 and a 0.4497 probability of being worth zero. Its
    expected value is therefore:
    $$0.5503 \times 1 + 0.4497 \times 0 = 0.5503$$

-   In a risk-neutral world this should be discounted at the risk-free
    rate. The value of the option today is therefore:
    $$0.5503 e^{-0.04 \times 0.25} = 0.545$$

-   This is the same as the value obtained earlier, demonstrating that
    no-arbitrage arguments and risk-neutral valuation give the same
    answer.
:::

::: frame
Irrelevance of Stock's Expected Return

-   When we are valuing an option in terms of the price of the
    underlying asset, the probability of up and down movements in the
    real world are irrelevant.

-   The probabilities of future up or down movements are already
    incorporated into the stock price: we do not need to take them into
    account again when valuing the option in terms of the stock price.

-   This is an example of a more general result stating that the
    expected return on the underlying asset in the real world is
    irrelevant
:::

# Two-Step Binomial Trees

::: frame
A Two-Step Example $K$=21; r = $4$%; each time step is 3 months

::: center
![image](images/07-15-two-step-tree.png){width="3in"}
:::
:::

::: frame
Valuing a Call Option

::: center
![image](images/07-16-valuing-call-option.png){width="2.8in"}
:::

-   Value at node B =
    $e^{-0.04 \times 0.25}(0.5503 \times 3.2 + 0.4497 \times 0) = 1.7433$

-   Value at node A =
    $e^{-0.04 \times 0.25}(0.5503 \times 1.7433 + 0.4497\times 0) = 0.9497$
:::

::: frame
A Put Option Example

-   $K$ = 52, time step = 1 year

-   $r$ = 5%, $u$ = 1.2, $d$ = 0.8, $p$ = 0.6282

::: center
![image](images/07-17-valuing-put-option.png){width="2.8in"}
:::
:::

::: frame
What Happens When the Put Option is American

-   The American feature increases the value at node C from 9.4636 to
    12.0000.

-   This increases the value of the option from 4.1923 to 5.0894.

::: center
![image](images/07-18-american-put.png){width="2.8in"}
:::
:::

::: frame
Choosing $u$ and $d$

-   One way of matching the volatility is to set:
    $$u = e^{\sigma \sqrt{\Delta t}}$$
    $$d = \frac{1}{u} = e^{- \sigma \sqrt{\Delta t}}$$

-   where $\sigma$ is the volatility and $\Delta t$ is the length of the
    time step.

-   This is the approach used by Cox, Ross, and Rubinstein (1979).
:::

::: frame
Girsanov's Theorem

-   Volatility is the same in the real world and the risk-neutral world.

-   We can therefore measure volatility in the real world and use it to
    build a tree for the an asset in the risk-neutral world.
:::

# The Binomial Tree Formulas

::: frame
The Binomial Tree Formulas

-   the size of an up and down move: $$u = e^{\sigma \sqrt{\Delta t}}$$
    $$d = \frac{1}{u} = e^{- \sigma \sqrt{\Delta t}}$$

-   probability of an up move: $$p = \frac{a - d}{u - d}$$
    $$a = e^{r\Delta t}$$

-   option value (one step): $$f = [pf_u + (1 - p)f_d]e^{-rT}$$
:::

::: frame
Other Types of Assets

-   For options on stock indices, currencies and futures the basic
    procedure for constructing the tree is the same except for the
    calculation of $p$

$$p = \frac{a - d}{u - d}$$

-   $a = e^{r\Delta t}$ for a nondividend paying stock

-   $a = e^{(r-q)\Delta t}$ for a stock index where $q$ is the dividend
    yield on the index

-   $a = e^{(r - r_f) \Delta t}$ for a currency where $r_f$ is the
    foreign risk-free rate

-   $a = 1$ for a futures contract
:::
