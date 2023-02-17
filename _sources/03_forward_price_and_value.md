# Forward Price for an Investment Asset

## Arbitrage Example 

### Assumptions

1. The market participants are subject to no transaction costs when they trade.
2. The market participants are subject to the same tax rate on all net trading
profits.
3. The market participants can borrow money at the same risk-free rate of
interest as they can lend money.
4. The market participants take advantage of arbitrage opportunities as they
occur.

### Notation

- $S_0$ = Spot price today
- $F_0$ = Futures or forward price today
- $T$ = Time until delivery date
- $r$ = Risk-free interest rate for maturity $T$

### Arbitrage Example 
- Arbitrage opportunities when forward price is out of line with spot price for
asset providing no income.
- Asset price = \$40; interest rate = 5%; maturity = 3 months

| Forward Price = \$43                                           | Forward Price = \$39                                            |
| -------------------------------------------------------------- | --------------------------------------------------------------- |
| *Action now:*                                                  | *Action now:*                                                   |
| Borrow \$40 at 5% for 3 months                                 | Short 1 unit of asset to realize \$40                           |
| Buy one unit of asset                                          | Invest \$40 at 5% for 3 months                                  |
| Enter into forward contract to sell asset in 3 months for \$43 | Enter into a forward contract to buy asset in 3 months for \$39 |
| *Action in 3 months:*                                          | *Action in 3 months:*                                           |
| Sell asset for \$43                                            | Buy asset for \$39                                              |
| Use \$40.50 to repay loan with interest                        | Close short position                                            |
|                                                                | Receive \$40.50 from investment                                 |
| **Profit realized = +2.50**                                    | **Profit realized = +1.50**                                     |

---

## The Forward Price

- If the spot price of an investment asset is $S_0$ and the futures price for a
contract deliverable in $T$ years is $F_0$, then 

$$F_0 = S_0 e^{rT}$$ 

where $r$ is the $T$-year risk-free rate of interest.

- In our examples, $S_0$ = 40, $T$ = 0.25, and $r$ = 0.05 so that 
 
$$F_0 = 40 e^{0.05\times0.25} = 40.50$$

- If short sales are not possible the formula still works for an investment
asset because investors who hold the asset will sell it and buy forward
contracts when the forward price is too low.

### When Asset Provides a Known Income or Yield

$$F_0 = (S_0 - I)e^{rT}$$ 

- where $I$ is the present value of the income during life of forward contract

$$F_0 = S_0 e^{(r-q)T}$$ 

- where $q$ is the average yield during the life of the contract (expressed with
continuous compounding)

---

## Valuing a Forward Contract

- A forward contract is worth zero (except for bid-offer spread effects) when it
is first negotiated.
- Later it may have a positive or negative value.
- Suppose that $K$ is the delivery price and $F_0$ is the forward price for a
contract that would be negotiated today.
- By considering the difference between a contract with delivery price $K$ and a
contract with delivery price $F_0$ we can deduce that:
    - the value of a long forward contract is $(F_0 - K) e^{-rT}$
    - the value of a short forward contract is $(K - F_0) e^{-rT}$

---

## Forward vs. Futures Prices

- When the maturity and asset price are the same, forward and futures prices are
usually assumed to be equal. (Eurodollar futures are an exception)
- In theory, when interest rates are uncertain, they are slightly different:
    - A strong positive correlation between interest rates and the asset price
    implies the futures price is slightly higher than the forward price.
    - A strong negative correlation implies the reverse.