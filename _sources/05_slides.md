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
# Mechanics of option markets and properties of options


# Mechanics of Options Markets

Review of Option Types

- A call is an option to buy
- A put is an option to sell
- A European option can be exercised only at the end of its life
- An American option can be exercised at any time

Option Positions

- Long call
- Long put
- Short call
- Short put

Long Call Profit from buying one European call option: option price =
USD 5, strike price = USD 100

```{code-cell}
:tags: [remove-input]

k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(s - k, 0) - p for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line()
    .encode(x="S", y="profit")
    .properties(title="Long Forward/Futures, K=100, at maturity")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

Short Call Profit from writing one European call option: option price =
USD 5, strike price = USD 100

```{code-cell}
:tags: [remove-input]

k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(s - k, 0) - p for s in df['S']] * -1
chart = (
    alt.Chart(df)
    .mark_line()
    .encode(x="S", y="profit")
    .properties(title="Long Forward/Futures, K=100, at maturity")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

Long Put Profit from buying a European put option: option price = USD 7,
strike price = USD 70

```{code-cell}
:tags: [remove-input]

k = 70  # strike price
p = 7  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(k - s, 0) - p for s in df['S']]
chart = (
    alt.Chart(df)
    .mark_line()
    .encode(x="S", y="profit")
    .properties(title="Long Forward/Futures, K=100, at maturity")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

Short Put Profit from writing a European put option: option price = USD
7, strike price = USD 70

```{code-cell}
:tags: [remove-input]

k = 100  # strike price
p = 5  # option premium
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = [max(k - s, 0) - p for s in df['S']] * -1
chart = (
    alt.Chart(df)
    .mark_line()
    .encode(x="S", y="profit")
    .properties(title="Long Forward/Futures, K=100, at maturity")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

Assets Underlying Exchange-Traded Options

- Stocks
- ETFs (and other ETPs)
- Foreign Currency
- Stock Indices
- Futures

Specification of Exchange-Traded Options

- Expiration date
- Strike price
- European or American
- Call or Put (option class)

Terminology Moneyness:

- At-the-money option
- In-the-money option
- Out-of-the-money option

- Option class (call or put for specific underlying)
- Option series (same expiration date in a given class)
- Intrinsic value (value if there were no time to maturity)
- Time value (the excess of an option's value over its intrinsic value)

Other CBOE Products

- FLEX options
- Weeklys
- Binary options
- Credit event binary options (CEBOs)
- Doom options

Dividends & Stock Splits Suppose you own $N$ options with a strike price of $K$:

- No adjustments are made to the option terms for cash dividends
- When there is an $n$-for-$m$ stock split:

1. the strike price is reduced to $\frac{m}{n} \times K$
2. the no. of options is increased to $\frac{n}{m} \times N$

- Stock dividends are handled similarly to stock splits

Dividends & Stock Splits Example

- Consider a call option to buy 100 shares for \$20/share
- How should terms be adjusted:

1. for a 2-for-1 stock split?
2. for a 5% stock dividend?

Market Makers

- Most exchanges use market makers to facilitate options trading
- A market maker quotes both bid and ask prices when requested
- The market maker does not know whether the individual requesting the quotes wants to buy or sell

Margin

- Margin is required when options are sold
- When a naked option is written the margin is the greater of:

1. A total of 100% of the proceeds of the sale plus 20% of the underlying share
price less the amount (if any) by which the option is out of the money
2. A total of 100% of the proceeds of the sale plus 10% of the underlying share
price (call) or exercise price (put)

- For other trading strategies there are special rules

Warrants

- Warrants are options that are issued by a corporation or a financial institution
- The number of warrants outstanding is determined by the size of the
  original issue and changes only when they are exercised or when they expire
- The issuer settles up with the holder when a warrant is exercised
- When call warrants are issued by a corporation on its own stock,
  exercise will usually lead to new treasury stock being issued

Employee Stock Options

- Employee stock options are a form of remuneration issued by a company to its executives
- They are usually at the money when issued
- When options are exercised the company issues more stock and sells
  it to the option holder for the strike price
- Expensed on the income statement

Convertible Bonds

- Convertible bonds are regular bonds that can be exchanged for equity at
certain times in the future according to a predetermined exchange ratio
- Usually a convertible is callable
- The call provision is a way in which the issuer can force conversion at a time
earlier than the holder might otherwise choose

# Properties of Stock Options

Notation

0.5

- $c$: European call option price
- $p$: European put option price
- $S_0$: Stock price today
- $K$: Strike price
- $T$: Life of option
- $\sigma$: Volatility of stock price

- $C$: Americal call option price
- $P$: American put option price
- $S_T$: Stock price at option maturity
- $D$: PV of dividends paid during life of option
- $r$: Risk-free rate for maturity T with cont. comp.

Effect of Variables on Option Pricing Summary of the effect on the price
of a stock option of increasing one variable while keeping all others
fixed.

::: center
![image](images/06-6-effect-of-variables.png){width="5in"}
:::

American vs European Options An American option is worth at least as
much as the corresponding European option

- $C \geq c$
- $P \geq p$

# Upper and Lower Bounds for Option Prices

Upper Bounds for Call Options American or European call option:

- The option can never be worth more than the stock.
- $c \leq S_0$ and $C \leq S_0$
- Otherwise, an arbitrageur could easily make a riskless profit by buying the
stock and selling the call option.

Upper Bounds for Put Options American put option:

- The option can never be worth more than $K$.
- $P \leq K$

European put option:

- At maturity the option cannot be worth morethan $K$.
- It follows that it cannot be worth more than the present value of $K$ today.
- $p \leq K e^{-rT}$

If this were not true, an arbitrageur could make a riskless profit by writing
the option and investing the proceeds of the sale at the risk-free interest
rate.

Lower Bound for European Calls on Non-Dividend-Paying Stocks

- A lower bound for the price of a European call option on a non-dividend-paying
stock is: $$S_0 - K e^{-rT}$$
- Example: $S_0$ = 20, $T$ = 1, $r$ = 10%, $K$ = 18, $D$ = 0 $$S_0 - K e^{-rT} =
20 - 18 e^{-0.1} = 3.71$$
- What if the European call price is \$3?
- An arbitrageur can short the stock, buy the call, and invest proceeds at 10%.

Lower Bound for European Puts on Non-Dividend-Paying Stocks

- A lower bound for the price of a European put option on a non-dividend-paying
stock is: $$K e^{-rT} - S_0$$
- Example: $S_0$ = 37, $T$ = 0.5, $r$ = 5%, $K$ = 40, $D$ = 0 $$K e^{-rT} - S_0
= 40 e^{-0.05 \times 0.5} - 37 = 2.01$$
- What if the European put price is \$1?
- An arbitrageur can borrow \$38 for 6 months to buy both the put and the stock.

Upper and Lower Bounds Summary

- Upper bound for European and American call options:
    $$c \leq S_0 \text{ and } C \leq S_0$$
- Upper bound for European and American put options:
    $$p \leq K e^{-rT} \text{ and } P \leq K$$
- Lower bound for European call option:
    $$c \geq max(S_0 - K e^{-rT}, 0)$$
- Lower bound for European put option:
    $$p \geq max(K e^{-rT} - S_0, 0)$$

# Put-Call Parity

Put-Call Parity: No Dividends Consider the following 2 portfolios:

-   Portfolio A: European call on a stock + zero-coupon bond that pays
    $K$ at time $T$
-   Portfolio C: European put on the stock + the stock

Values of Portfolios Portfolios illustrating put-call parity.

::: center
![image](images/06-7-put-call-parity.png){width="4in"}
:::
:::

::: frame
The Put-Call Parity Result

- Both are worth $max(S_T , K )$ at the maturity of the options
- They must therefore be worth the same today.
- This means that $$c + K e^{-rT} = p + S_0$$

Put-Call Parity Arbitrage ($S_0$ = \$31, $r$ = 10%, $c$ = \$3, $K$ =
\$30) ![image](images/06-arbitrage-put-call.png){width="5in"}
:::

# Americal Call Option on a Non-Dividend Paying Stock

Early Exercise

- Usually there is some chance that an American option will be exercised early
- An exception is an American call on a non-dividend paying stock
- This should [never]{.alert} be exercised early

An Extreme Situation

- For an American call option: $S_0$ = 100; T = 0.25; K = 60; D = 0
- Should you exercise immediately?

What should you do if

- You want to hold the stock for the next 3 months?
- You do not feel that the stock is worth holding for the next 3 months?

Reasons For Not Exercising a Call Early (No Dividends)

- No income is sacrificed
- You delay paying the strike price
- Holding the call provides insurance against stock price falling below strike price
- If you do not want to hold the stock, it is better to sell it than exercise
it. (intrinsic value + time value)

Bounds for European or American Call Options (No Dividends)

::: center
![image](images/06-8-option-bounds.png){width="3in"}
:::
:::

# Americal Put Option on a Non-Dividend Paying Stock

Should Puts Be Exercised Early?

- At any given time during its life, the put option should always be exercised
early if it is sufficiently deep in the money.
- In general, the early exercise of a put option becomes more attractive as
$S_0$ decreases, as $r$ increases, and as the volatility decreases.
- Suppose that the strike price is \$10 and the stock price is virtually zero.
- By exercising immediately, an investor makes an immediate gain of \$10.
- If the investor waits, the gain from exercise might be less than \$10, but it
cannot be more than \$10, because negative stock prices are impossible.
- Furthermore, receiving \$10 now is preferable to receiving \$10 in the future.
- It follows that the option should be exercised immediately.

Bounds for European and American Put Options (No Dividends)

![image](images/06-9-put-option-bounds.png){width="5in"}

# Effect of Dividends

Effect of Dividends

- We assume that the dividends that will be paid during the life of the option
are known.
- We will use $D$ to denote the present value of the dividends during the life
of the option.
- A dividend is assumed to occur at the time of its ex-dividend date.
- When dividends are expected, we can no longer assert that an American call
option will not be exercised early.
- Sometimes it is [optimal to exercise]{.alert} an American call immediately
prior to an ex-dividend date.
- It is never optimal to exercise a call at other times.

The Impact of Dividends on Lower Bounds to Option Prices
$$c \geq S_0 - D - K e^{-rT}$$

$$p \geq D + K e^{-rT} - S_0$$

Extensions of Put-Call Parity

- American options; D = 0 $S_0 - K < C -P < S_0 - K e^{-rT}$
- European options; D \> 0 $c + D + K e^{-rT} = p + S_0$
- American options; D \> 0 $S_0 - D - K < C - P < S_0 - K e^{-rT}$