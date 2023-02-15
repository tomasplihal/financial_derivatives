# Determination of Forward and Futures Prices

## Introduction

### Pricing and Valuation

- Forward/futures **pricing** involves determining the appropriate price or rate
when **initiating** the contract.
- Forward/futures **valuation** involves determining the appropriate value of
the contract, typically **after** it has been initiated.
- When the forward or futures contract is established, the price is usually
negotiated so that the **value of the contract on the initiation date is zero**.

### Forward Price vs. Value Example
On 2 November, an investor goes long a December Gold futures contract at a
price of \$1,250/oz. This contract has an initial **value of \$0**.

**After the initiation date, the value can be significantly positive or
negative.**

On 3 November, the price of the December Gold futures contract drops to
\$1,225/oz. The long investor’s position (initiated the prior day) now has a
**negative value**.

### Pricing and Valuation Methodology 

+ **Risk aversion:** The concept that investors do not accept risk without the
expectation of a return commensurate with that risk.
+ **Risk-neutral pricing:** Arbitrage guarantees that a risk-free portfolio
consisting of the underlying and the derivative must earn the risk-free rate.
+ **Arbitrage-free pricing:** The process of pricing a derivative under the
assumption of risk-neutral pricing and a market free of arbitrage opportunities

- Our approach to pricing and valuation is based on the assumption that prices
adjust in order to **not allow arbitrage profits**.
- The arbitrageur abides by two fundamental rules:
    1. Do not use your own money.
    2. Do not take any price risk.
- **Law of one price:** Two investments with the same or equivalent future cash
flows, regardless of what will happen in the future, will sell for the same
current price.

### Short Selling

- Short selling involves selling securities you do not own.
- Your broker borrows the securities from another client and sells them in the
market in the usual way.
- At some stage you must buy the securities so they can be replaced in the
account of the client.
- You must pay dividends and other benefits the owner of the securities
receives.
- There may be a small fee for borrowing the securities.

### Example

- You short 100 shares when the price is \$100 and close out the short position
three months later when the price is \$90.
- During the three months a dividend of \$3 per share is paid.
- What is your profit?
- What would be your loss if you had bought 100 shares?

### Consumption vs Investment Assets

- **Investment assets** are assets held by significant numbers of people purely
for investment purposes (Examples: gold, silver, stocks, bonds).
- **Consumption assets** are assets held primarily for consumption (Examples:
copper, oil, wheat).

## Forward Price for an Investment Asset

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

| Forward Price = \$43 | Forward Price = \$39 |
|----------------------|----------------------|
| *Action now:* | *Action now:* |
| Borrow \$40 at 5% for 3 months |  Short 1 unit of asset to realize \$40 |
| Buy one unit of asset  | Invest \$40 at 5% for 3 months
| Enter into forward contract to sell asset in 3 months for \$43 | Enter into a forward contract to buy asset in 3 months for \$39 |
| *Action in 3 months:* | *Action in 3 months:* |
| Sell asset for \$43  | Buy asset for \$39 |
| Use \$40.50 to repay loan with interest | Close short position |
|      |          Receive \$40.50 from investment |
| **Profit realized = +2.50** | **Profit realized = +1.50** | 

### The Forward Price
- If the spot price of an investment asset is $S_0$ and the futures price for a
contract deliverable in $T$ years is $F_0$, then $$F_0 = S_0 e^{rT}$$ where $r$
is the $T$-year risk-free rate of interest.
- In our examples, $S_0$ = 40, $T$ = 0.25, and $r$ = 0.05 so that $$F_0 = 40 e^{0.05\times0.25} = 40.50$$
- If short sales are not possible the formula still works for an investment
asset because investors who hold the asset will sell it and buy forward
contracts when the forward price is too low.

### When Asset Provides a Known Income or Yield

$$F_0 = (S_0 - I)e^{rT}$$ 
- where $I$ is the present value of the income
during life of forward contract
$$F_0 = S_0 e^{(r-q)T}$$ 
- where $q$ is the average yield during the life of the contract (expressed with
continuous compounding)

## Valuing a Forward Contract

### Valuing a Forward Contract

- A forward contract is worth zero (except for bid-offer spread effects) when it
is first negotiated.
- Later it may have a positive or negative value.
- Suppose that $K$ is the delivery price and $F_0$ is the forward price for a
contract that would be negotiated today.
- By considering the difference between a contract with delivery price $K$ and a
contract with delivery price $F_0$ we can deduce that:
    - the value of a long forward contract is $$(F_0 - K) e^{-rT}$$
    - the value of a short forward contract is $$(K - F_0) e^{-rT}$$

### Forward vs Futures Prices

- When the maturity and asset price are the same, forward and futures prices are
usually assumed to be equal. (Eurodollar futures are an exception)
- In theory, when interest rates are uncertain, they are slightly different:
    - A strong positive correlation between interest rates and the asset price
    implies the futures price is slightly higher than the forward price.
    - A strong negative correlation implies the reverse.

## Forward Price for a Stock Index

### Stock Index

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

## Forward Price for Exchange Rates

### Futures and Forwards on Currencies

- A foreign currency is analogous to a security providing a yield.
- The yield is the foreign risk-free interest rate.
- It follows that if $r_f$ is the foreign risk-free interest rate
$$F_0 = S_0 e^{(r-r_f)T}$$

### Explanation of the Relationship Between Spot and Forward

- Two ways of converting 1,000 units of a foreign currency to dollars at time
$T$.
- Here, $S_0$ is spot exchange rate, $F_0$ is forward exchange rate, and $r$ and
$r_f$ are the dollar and foreign risk-free rates.

```{mermaid}
flowchart TD
    A[1000 units of foreign currency at time zero]
    B1[1000$e^rfT$ units of foreign currency at time T]
    C1[1000erfTF0 dollars at time T]
    B2[1000S0 dollarsat time zero]
    C2[1000S0erT dollarsat time T]
    A --> B1
    B1 --> C1
    A --> B2
    B2 --> C2
```

## Forward Price for Commodities

### Consumption Assets: Storage is Negative Income

$$F_0 \leq S_0 e^{(r+u)T}$$
- where $u$ is the storage cost per unit time as a percent of the asset value.
- Alternatively, $$F_0 \leq (S_0 +U) e^{rT}$$ where $U$ is the present value of
the storage costs.

### The Cost of Carry

- The cost of carry, $c$, is the storage cost plus the interest costs less the
income earned
- For an investment asset $F_0 = S_0 e^{cT}$
- For a consumption asset $F_0 \leq S_0 e^{cT}$
- The convenience yield on the consumption asset, $y$, is defined so that 
  $F_0 = S_0 e^{(c-y)T}$
- A convenience yield is a premium associated with holding an underlying asset,
rather than the associated derivative security or contract.

## Futures Prices and Expected Spot Prices

### Futures Prices and Expected Future Spot Prices

- Suppose $k$ is the expected return required by investors in an asset.
- We can invest $F_0 e^{-rT}$ at the risk-free rate and enter into a long
futures contract to create a cash inflow of $S_T$ at maturity.
- The present value of this investment is $- F_0 e^{-rT} + E(S_T) e^{-kT}$
- $k$ is an investor's required return for this investment, $E$ denotes expected
value.
- We assume that all investments in securities markets are priced so that they
have zero net present value: $$F_0 = E(S_T)e^{(r-k)T}$$
- Relationship between futures price and expected future spot price.

| Underlying asset | Relationship of expected return k from asset to risk-free rate r | Relationship of futures price F to expected future spot price E(ST)|
|----|----|----|
| No systematic risk | k = r | F0 = E(S T) 
| 
| Positive systematic risk | k > r | F0 < E(S T) | 
| Negative systematic risk | k < r | F0 > E(S T) | 

- Positive systematic risk: stock indices
- Negative systematic risk: gold (at least for some periods)

## Froward Pricing Example ##

Assume an asset sells in the spot market for a price of \$94, the risk-free
rate is 4%, and the forward contract expires in six months. What is the
initial value of the contract and the correct forward price?

$S_0(T) = \$94$

The value of the contract at initiation is $V_0(T) = 0$

$T$ = 6 months = 0.5 years

Forward Pricing Equation
$$F_0(T) = S_0(1 + r)^T = \$94(1 + 0.04)^{0.5} = \$95.86 $$

The forward price established at the initiation date of the
contract is \$95.86

1. Gold: An Arbitrage Opportunity? Suppose that:

- The spot price of gold is USD 1,200
- The 1-year forward price of gold is USD 1,300
- The 1-year USD interest rate is 5% per annum

Is there an arbitrage opportunity?

2. Gold: Another Arbitrage Opportunity? Suppose that:

- The spot price of gold is USD 1,200
- The 1-year forward price of gold is USD 1,200
- The 1-year USD interest rate is 5% per annum

Is there an arbitrage opportunity?

The Forward Price of Gold (ignores the gold lease rate) If the spot
price of gold is $S$ and the forward price for a contract deliverable in
$T$ years is $F$, then $$F = S (1+r)^T$$

where $r$ is the 1-year (domestic currency) risk-free rate of interest.

In our examples, $S$ = 1200, $T$ = 1, and $r$ =0.05 so that
$$F = 1200(1+0.05) = 1,260$$


1. Oil: An Arbitrage Opportunity? Suppose that:

- The spot price of oil is USD 50
- The quoted 1-year futures price of oil is USD 60
- The 1-year USD interest rate is 5% per annum
- The storage costs of oil are 2% per annum

Is there an arbitrage opportunity?

2. Oil: Another Arbitrage Opportunity? Suppose that:

- The spot price of oil is USD 50
- The quoted 1-year futures price of oil is USD 40
- The 1-year USD interest rate is 5% per annum
- The storage costs of oil are 2% per annum

Is there an arbitrage opportunity?
