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

```{code-cell} 
:tags: [remove-cell]

import pandas as pd
import altair as alt
```

# Mechanics of Options Markets

## Options

```{admonition} Definition
:class: tip

- An option gives the holder the **right** to buy or sell at a certain price.
- An **option** is a derivative contract in which one party, the buyer, pays a
sum of money to the other party, the seller or writer, and receives the
**right** to either buy or sell an underlying asset at a fixed price either on a
specific expiration date or at any time prior to the expiration date.
```

- A **call option** is an option to **buy** a certain asset by a certain date
for a certain price (the strike price).
- A **put option** is an option to **sell** a certain asset by a certain date
for a certain price (the strike price).

+ An **American option** can be exercised at any time during its life.
+ A **European option** can be exercised only at maturity.

## Option Positions

### Long Call

```{code-cell}
:tags: [remove-input]
k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(s - k, 0) - p for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line(clip=True, strokeWidth=3)
    .encode(
        alt.X("S", scale=alt.Scale(domain=(70, 130))),
        alt.Y("profit", scale=alt.Scale(domain=(-10, 30))),
    )
    .properties(title="Long Call Option, K = 100, c = 5")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

### Short Call

```{code-cell}
:tags: [remove-input]
k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [-(max(s - k, 0) - p) for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line(clip=True, strokeWidth=3)
    .encode(
        alt.X("S", scale=alt.Scale(domain=(70, 130))),
        alt.Y("profit", scale=alt.Scale(domain=(-30, 10))),
    )
    .properties(title="Short Call Option, K = 100, c = 5")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

### Long Put

```{code-cell}
:tags: [remove-input]

k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(k - s, 0) - p for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line(clip=True, strokeWidth=3)
    .encode(
        alt.X("S", scale=alt.Scale(domain=(70, 130))),
        alt.Y("profit", scale=alt.Scale(domain=(-10, 30))),
    )
    .properties(title="Long Put Option, K = 100, p = 5")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

### Short Put

```{code-cell}
:tags: [remove-input]

k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [-(max(k - s, 0) - p) for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line(clip=True, strokeWidth=3)
    .encode(
        alt.X("S", scale=alt.Scale(domain=(70, 130))),
        alt.Y("profit", scale=alt.Scale(domain=(-30, 10))),
    )
    .properties(title="Short Put Option, K = 100, p = 5")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

## Option Payoffs

Assumptions and symbol definitions:

- $S_T$: the price of the underlying at the expiration date $T$
- $K$: the exercise price of the option

+ Payoff to the call buyer: $c_T = Max(0, S_T - K)$
+ Payoff to the put buyer: $p_T = Max(0, K - S_T)$

```{admonition} Example
At expiration the underlying asset price $S_T$ is \$28. If the strike price K is
\$25, what is the payoff of the put and call?

- Payoff to the call buyer:

$$c_T = Max(0, S_T - K) = Max(0, \$28 - \$25) = \$3$$

- Payoff to the put buyer:

$$p_T = Max(0, K - S_T) = Max(0, \$25 - \$28) = 0$$

When the option has a positive payoff it is said to be **in the money**. In the
example above, the call option is **in the money**. The put option is **out of
the money** because $X - S_T$ is less than 0. When $S_T = X$, the option is said
to be **at the money**.
```

## Option Profit

- Since option buyer must pay a price (or **option premium**), the profit is
computed by subtracting the option premium from the option payoff.

Assumptions and symbol definitions:

- $S_T$: the price of the underlying at the expiration date $T$ 
- $K$: the exercise price of the option
- $c_0$: the price (premium) of the call option
- $p_0$: the price (premium) of the put option

+ Profit to the call buyer: $\Pi = Max(0, S_T - K) - c_0$
+ Profit to the put buyer: $\Pi = Max(0, K - S_T) - p_0$

```{admonition} Example
- Assume that a put and call on CBX stock both have a strike price $K = \$30$.
The call initially costs \$1, and the put costs \$2.
- What is the profit on the call and put if the price of CBX stock at expiration
($S_T$) is \$27.50?

+ Profit to the call buyer: 

$$ \Pi = Max(0, S_T - K) - c_0 = Max(0, \$27.5 - \$30) - \$1 = -\$1 $$

+ Profit to the put buyer: 

$$ \Pi = Max(0, K - S_T) - p_0 = Max(0, \$30 - \$27.5) - \$2 = \$0.5 $$
```

## Other Option Characteristics

- Assets underlying exchange-traded options:
    - Stocks
    - ETFs (and other ETPs)
    - Foreign Currency
    - Stock Indices
    - Futures
- Specification of exchange-traded options:
    - Expiration date
    - Strike price
    - European or American
    - Call or Put (option class)
- Moneyness:
    - At-the-money option
    - In-the-money option
    - Out-of-the-money option
- Value:
    - **Intrinsic value** (value if there were no time to maturity).
    - **Time value** (the excess of an option's value over its intrinsic value).
- Margin:
  - Margin is required when options are sold.
  - Specific rules for different trading strategies.

## Dividends and Stock Splits 

- No adjustments are made to the option terms for cash dividends.
- Stock splits and stock dividends require adjustment in strike price and number
of options.

+ Suppose you own $N$ options with a strike price of $K$:
+ When there is an $n$-for-$m$ stock split:

1. the strike price is reduced to $\frac{m}{n} \times K$
2. the number of options is increased to $\frac{n}{m} \times N$

```{admonition} Example
- Consider a call option to buy 100 shares for \$20 per share.
- How should terms be adjusted:
    1. for a 2-for-1 stock split?
        - the strike price is reduced to $\frac{1}{2} \times \$20 = \$10$
        - the number of options is increased to $\frac{2}{1} \times 100 = 200$
    2. for a 5% stock dividend?
        - the strike price is reduced to $\frac{1}{1.05} \times \$20 = \$19.05$
        - the number of options is increased to $\frac{1.05}{1} \times 100 = 105$
```

## Other Assets Related to Options

- Warrants
    - Warrants are options that are issued by a corporation or a financial
    institution.
    - The number of warrants outstanding is determined by the size of the
    original issue and changes only when they are exercised or when they expire.
    - The issuer settles up with the holder when a warrant is exercised.
    - When call warrants are issued by a corporation on its own stock, exercise
    will usually lead to new treasury stock being issued.

+ Employee Stock Options
    + Employee stock options are a form of remuneration issued by a company to
    its executives.
    + They are usually at the money when issued.
    + When options are exercised the company issues more stock and sells it to
    the option holder for the strike price.
    + Expensed on the income statement.

- Convertible Bonds
    - Convertible bonds are regular bonds that can be exchanged for equity at
    certain times in the future according to a predetermined exchange ratio.
    - Usually a convertible is callable.
    - The call provision is a way in which the issuer can force conversion at a
    time earlier than the holder might otherwise choose.
