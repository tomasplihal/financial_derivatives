# Black-Scholes-Merton Model

## Model Assumptions

- The options are European-style (early exercise is not allowed).
- There are no dividends during the life of the derivative.
- There are no riskless arbitrage opportunities.
- Short selling of the underlying instrument is permitted.
- There are no market frictions: no transaction costs, regulatory constraints,
or taxes.
- The risk-free rate of interest is constant and the same for all maturities.
- The volatility of the return on the underlying is known and constant.
- The underlying follows a geometric Brownian motion statistical process
(continuous prices with no jumps).
- Continuous trading is available (one must be able to trade at every instant)
and the underlying instrument has perfect liquidity.

## The Black-Scholes-Merton Formulas for Options

- $c \dots$ call option price
- $p \dots$ put option price
- $N(x) \dots$ the standard normal cumulative distribution function
- $r \dots$ annualized continuously compounded risk-free rate
- $\sigma \dots$ annualized constant volatility
- $S \dots$ stock price
- $K \dots$ strike price
- $T \dots$ time to expiration for the option (in years)

$$c = S_0 N(d_1) - K e^{-rT} N(d_2)$$
$$p = K e^{-rT} N(-d_2) - S_0 N(-d_1)$$
$$d_1 = \frac{\ln (S_0 / K) + (r + \sigma^2 / 2)T}{\sigma \sqrt{T}}$$
$$d_2 = \frac{\ln (S_0 / K) + (r - \sigma^2 / 2)T}{\sigma \sqrt{T}} =
        d_1 - \sigma \sqrt{T}$$

## The $N(x)$ Function

- $N(x)$ is the probability that a normally distributed variable with a mean of
zero and a standard deviation of 1 is less than $x$.
- See tables at the end of the book or function NORMDIST in excel.

![image](images/08-2-nx.png)

## Example

- $S_0 = 42$
- $K = 40$
- $r = 10\%$
- $\sigma = 20\%$
- $T = 0.5$

$$d_1 = \frac{\ln (42/40) + (0.1 + 0.2^2 / 2) \times0.5 }{0.2 \sqrt{0.5}} = 0.7693$$
$$d_2 = 0.7693 - 0.2 \sqrt{0.5} = 0.6278$$

- Using NORMDIST in Excel:
    - N(0.7693) = 0.7791; N(0.6278) = 0.7349;
    - N(-0.7693) = 0.2209; N(-0.6278) = 0.2651

$$K e^{-rT} = 40 e^{-0.1 \times 0.5} = 38.049$$

$$c = 42 \times 0.7791 - 38.049 \times 0.7349 = 4.76$$
$$p = 38.049 \times 0.2651 - 42 \times 0.2209 = 0.81$$