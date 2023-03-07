---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Properties of Stock Options

## Factors Affecting Option Prices 

- Summary of the effect on the price of a stock option of increasing one
variable while keeping all others fixed.

+ $+$ Indicates that an increase in the variable causes the option price to
increase or stay the same.
+ $-$ Indicates that an increase in the variable causes the option price to
decrease or stay the same.
+ $?$ Indicates that the relationship is uncertain.

|          Variable          | European call | European put | American call | American put |
| :------------------------: | :-----------: | :----------: | :-----------: | :----------: |
|    Current stock price     |      $+$      |     $-$      |      $+$      |     $-$      |
|        Strike price        |      $-$      |     $+$      |      $-$      |     $+$      |
|     Time to expiration     |      $?$      |     $?$      |      $+$      |     $+$      |
|         Volatility         |      $+$      |     $+$      |      $+$      |     $+$      |
|       Risk-free rate       |      $+$      |     $-$      |      $+$      |     $-$      |
| Amount of future dividends |      $-$      |     $+$      |      $-$      |     $+$      |

## Notation

- $c$: European call option price
- $p$: European put option price
- $C$: Americal call option price
- $P$: American put option price

- $S_0$: Stock price today
- $S_T$: Stock price at option maturity
- $K$: Strike price
- $T$: Life of option
- $\sigma$: Volatility of stock price
- $D$: Present value of dividends paid during life of option
- $r$: Risk-free rate (nominal) for maturity $T$ with continuous compounding

## American vs. European Options

- An American option is worth at least as much as the corresponding European
option.

$$ C \geq c $$
$$ P \geq p $$

## Upper and Lower Bounds for Option Prices

### Upper Bounds for Call Options

- Applies to both, American and European, options.
- The option can never be worth more than the stock.
- $c \leq S_0$ and $C \leq S_0$
- Otherwise, an arbitrageur could easily make a riskless profit by buying the
stock and selling the call option.

### Upper Bounds for Put Options

- American put option:
  - The option can never be worth more than $K$.
  - $P \leq K$

+ European put option:
  - At maturity the option cannot be worth more than $K$.
  - It follows that it cannot be worth more than the present value of $K$ today.
  - $p \leq K e^{-rT}$
  - If this were not true, an arbitrageur could make a riskless profit by
  writing the option and investing the proceeds of the sale at the risk-free
  interest rate.

### Lower Bounds for European Call Options

- A lower bound for the price of a European call option on a **non-dividend-paying
stock** is: 

$$S_0 - K e^{-rT}$$

```{admonition} Example
- $S_0 = 20$, $T = 1$, $r = 10\%$, $K = 18$, $D = 0$

$$S_0 - K e^{-rT} = 20 - 18 e^{-0.1} = 3.71$$

- What if the European call price is \$3?
- An arbitrageur can short the stock, buy the call, and invest proceeds at 10%.
```

### Lower Bounds for European Put Options

- A lower bound for the price of a European put option on a **non-dividend-paying
stock** is: 

$$K e^{-rT} - S_0$$

```{admonition} Example
- $S_0 = 37$, $T = 0.5$, $r = 5\%$, $K = 40$, $D = 0$ 

$$K e^{-rT} - S_0 = 40 e^{-0.05 \times 0.5} - 37 = 2.01$$

- What if the European put price is \$1?
- An arbitrageur can borrow \$38 for 6 months to buy both the put and the stock.
```

## Upper and Lower Bounds Summary

- Upper bound for European and American call options:

  $$c \leq S_0 \text{ and } C \leq S_0$$

- Upper bound for European and American put options:

  $$p \leq K e^{-rT} \text{ and } P \leq K$$

- Lower bound for European call option:

  $$c \geq max(S_0 - K e^{-rT}, 0)$$

- Lower bound for European put option:

  $$p \geq max(K e^{-rT} - S_0, 0)$$