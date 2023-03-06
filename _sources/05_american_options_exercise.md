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

# American Options

## Americal Call Option on a Non-Dividend Paying Stock

Early Exercise

- Usually there is some chance that an American option will be exercised early.
- An exception is an American call on a non-dividend paying stock.
- This should **never** be exercised early.

An Extreme Situation

- For an American call option: $S_0 = 100$; $T = 0.25$; $K = 60$; $D = 0$
- Should you exercise immediately?

What should you do if:

- You want to hold the stock for the next 3 months?
- You do not feel that the stock is worth holding for the next 3 months?

Reasons For Not Exercising a Call Early (No Dividends)

- No income is sacrificed.
- You delay paying the strike price.
- Holding the call provides insurance against stock price falling below strike
price.
- If you do not want to hold the stock, it is better to sell it than exercise
it (intrinsic value + time value).

- Upper bound for American call options:
    $$ C \leq S_0$$
- Lower bound for American call option:
    $$C \geq max(S_0 - K e^{-rT}, 0)$$

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

- Upper and lower bounds for American put options:
    $$ max(K - S_0, 0) \leq P \leq K $$