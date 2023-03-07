# Volatility

- The volatility, $\sigma$, of a stock is a measure of our uncertainty about the
returns provided by the stock.
- Stocks typically have a volatility between 15% and 60%.
- Option's value is particularly sensitive to volatility.
- Unlike the price of the underlying, volatility is not an observable value in
the marketplace.
- Volatility can be, and often is, estimated based on a sample of historical
data.

## Historical Volatility

- The volatility is the standard deviation of the continuously compounded rate
of return in 1 year.
-  The standard deviation of the return in a short time period $\Delta t$ is
approx. $\sigma \sqrt{\Delta t}$
- If a stock price is \$30 and its volatility is 25% per year what is the
standard deviation of the price change in one day?  

$$\sigma \sqrt{\Delta t} = 30 \times \sqrt{\frac{1}{252}} = 1.89$$

- On the other hand, when you calculate volatility as a standard deviation of
daily returns, you can multiply the result by $\sqrt{252}$ to obtain annulized
volatility.

## Nature of Volatility

- Volatility is usually much greater when the market is open (i.e. the asset is
trading) than when it is closed.
- For this reason time is usually measured in **trading days** not calendar days
when options are valued.
- It is assumed that there are **252 trading days** in one year for most assets.
- Suppose it is April 1 and an option lasts to April 30 so that the number of
days remaining is 30 calendar days or 22 trading days.
- The time to maturity would be assumed to be 22/252 = 0.0873 years.

## Implied Volatility

- Volatility can also be inferred from option prices.
- This inferred volatility is called the **implied volatility**.
- The implied volatility of an option is the volatility for which the
Black-Scholes-Merton price equals the market price.
- The key advantage in using implied volatility is that it provides information
regarding the market's perception of uncertainty going forward.
- [The VIX S&P 500 Volatility Index.](https://www.cboe.com/tradable_products/vix/)

## Implied Volatility in Option Trading

- Implied volatility can be interpreted as the market's view of option value.
- In the option markets, participants use volatility as the medium in which to
quote options.
- Rather than quote a call price as \$10, traders may quote the implied
volatility as 25%, which prices the option at \$10.
- Implied volatility can be used to assess the relative value of different
options, neutralizing the effects of moneyness and time to expiration (low
implied volatility = cheap options).
- Implied volatility is useful for revaluing existing positions over time.
- Regulators, banks, compliance officers, and most option traders use implied
volatilities to communicate information related to options portfolios.

## Implied Volatility Summary

- Although historical volatility can be estimated, there is no objective measure
of future volatility.
- Implied volatility is the BSM model volatility that yields the market option
price.
- Implied volatility is a measure of future volatility, whereas historical
volatility is a measure of past volatility.
- Option prices reflect the beliefs of option market participants about the
future volatility of the underlying.
- The volatility smile is a two dimensional plot of the implied volatility with
respect to the exercise price.
- The volatility surface is a three-dimensional plot of the implied volatility
with respect to both expiration time and exercise prices.
- If the BSM model assumptions were true, then one would expect to find the
volatility surface flat, but in practice, the volatility surface is not flat.