# Forward Price for Specific Assets

## Stock Index

- Can be viewed as an investment asset paying a dividend yield.
- The futures price and spot price relationship is therefore 

$$F_0 = S_0 e^{(r-q)T}$$

- where $q$ is the average dividend yield on the portfolio represented by the
index during life of contract.
- For the formula to be true it is important that the index represent an
investment asset.
- In other words, changes in the index must correspond to changes in the value
of a tradable portfolio.
- The Nikkei index viewed as a dollar number does not represent an investment
asset.

### Index Arbitrage

- When $F_0 > S_0 e^{(r-q)T}$ an arbitrageur buys the stocks underlying the
index and sells futures.
- When $F_0 < S_0 e^{(r-q)T}$ an arbitrageur buys futures and shorts or sells
the stocks underlying the index.
- Index arbitrage involves simultaneous trades in futures and many different
stocks.
- Very often a computer is used to generate the trades.
- Occasionally simultaneous trades are not possible and the theoretical
no-arbitrage relationship between $F_0$ and $S_0$ does not hold.

---

## Exchange Rates

- A foreign currency is analogous to a security providing a yield.
- The yield is the foreign risk-free interest rate.
- It follows that if $r_f$ is the foreign risk-free interest rate

$$F_0 = S_0 e^{(r-r_f)T}$$

### Explanation of the Relationship Between Spot and Forward

- Two ways of converting 1,000 units of a foreign currency to dollars at time
$T$.
- Here, $S_0$ is spot exchange rate, $F_0$ is forward exchange rate, and $r$ and
$r_f$ are the dollar and foreign risk-free rates.


- Suppose that an individual starts with $1,000$ units of the foreign currency.
- There are two ways it can be converted to dollars at time $T$. 
  1. Investing it for $T$ years at $r_f$ and entering into a forward contract to sell the proceeds for dollars at time $T$. 
  2. Exchanging the foreign currency for dollars in the spot market and investing the proceeds for $T$ years at rate $r$.
- In the absence of arbitrage opportunities, the two strategies must give the
same result: 

$$1,000 \times e^{r_f \times T} \times F_0 = 1,000 \times S_0 \times e^{r \times T} $$

- So that

$$F_0 = S_0 e^{(r-r_f)T}$$

---

## Commodities

### Consumption Assets: Storage is Negative Income

$$F_0 \leq S_0 e^{(r+u)T}$$

- where $u$ is the storage cost per unit time as a percent of the asset value.
- Alternatively, 
 
$$F_0 \leq (S_0 +U) e^{rT}$$

- where $U$ is the present value of the storage costs.

---

## The Cost of Carry

- The cost of carry, $c$, is the storage cost plus the interest costs less the
income earned.
- For an investment asset $F_0 = S_0 e^{cT}$
- For a consumption asset $F_0 \leq S_0 e^{cT}$
- The convenience yield on the consumption asset, $y$, is defined so that 
  $F_0 = S_0 e^{(c-y)T}$
- A convenience yield is a premium associated with holding an underlying asset,
rather than the associated derivative security or contract.

---

## Futures Prices and Expected Spot Prices

- Suppose $k$ is the expected return required by investors in an asset.
- We can invest $F_0 e^{-rT}$ at the risk-free rate and enter into a long
futures contract to create a cash inflow of $S_T$ at maturity.
- The present value of this investment is $- F_0 e^{-rT} + E(S_T) e^{-kT}$
- $k$ is an investor's required return for this investment, $E$ denotes expected
value.
- We assume that all investments in securities markets are priced so that they
have zero net present value: $$F_0 = E(S_T)e^{(r-k)T}$$
- Relationship between futures price and expected future spot price:

|     Underlying asset     | Relationship of expected return k from asset to risk-free rate $r$ | Relationship of futures price $F$ to expected future spot price $E(S_T)$ |
| :----------------------: | :----------------------------------------------------------------: | :----------------------------------------------------------------------: |
|    No systematic risk    |                              $k = r$                               |                              $F_0 = E(S_T)$                              |
| Positive systematic risk |                              $k > r$                               |                              $F_0 < E(S_T)$                              |
| Negative systematic risk |                              $k < r$                               |                              $F_0 > E(S_T)$                              |

- Positive systematic risk: stock indices
- Negative systematic risk: gold (at least for some periods)

### Contango and Backwardation

- **Backwardation** $\rightarrow$ When the futures price is **below** the expected future spot price (or current spot price).
- **Contango** $\rightarrow$ When the futures price is **above** the expected future spot price (or current spot price).