# Hedging Strategies Using Futures

## Basic Principles

Long & Short Hedges

- A **long** futures hedge is appropriate when you know you will
**purchase** an asset in the future and want to lock in the
price.
- A **short** futures hedge is appropriate when you know you will **sell** an
asset in the future and want to lock in the price.

Arguments in Favor of Hedging

- Companies should focus on the main business they are in and take steps to
**minimize risks** arising from interest rates, exchange rates, and other market
variables.

Arguments against Hedging

- Shareholders are usually well diversified and can make their own hedging
decisions.
- It may increase risk to hedge when competitors do not.
- Explaining a situation where there is a loss on the hedge and a gain on the
underlying can be difficult.

## Basis Risk

Basis Risk Hedging in practice is usually more complex than our simplified
examples:

1. The asset whose price is to be hedged may not be exactly the same as the
asset underlying the futures contract.
2. There may be uncertainty as to the exact date when the asset will be bought
or sold.
3. The hedge may require the futures contract to be closed out before its
delivery month.

The Basis

- Basis is usually defined as the spot price minus the futures price.
- Basis risk arises because of the uncertainty about the basis when the hedge is
closed out.

Long Hedge for Purchase of an Asset Define:

- $F_1$: Futures price at time hedge is set up *(88.0)*
- $F_2$: Futures price at time asset is purchased *(89.1)*
- $S_2$: Asset price at time of purchase *(90.0)*
- $b_2$: Basis at time of purchase *(90.0 - 89.1 = 0.9)*

+ Cost of asset = $S_2$
+ Gain on Futures = $F_2 - F_1$ *( = 89.1 - 88.0 = 1.1)*
+ Net amount paid = $S_2 - (F_2 - F_1) = F_1 + b_2$ *( = 90.0 - 1.1 = 88.0 + 0.9
= 88.9)*

Short Hedge for Sale of an Asset Define:

- $F_1$: Futures price at time hedge is set up *(0.98)*
- $F_2$: Futures price at time asset is sold *(0.925)*
- $S_2$: Asset price at time of sale *(0.92)*
- $b_2$: Basis at time of sale *( = 0.92 - 0.925 = -0.005)*

+ Price of asset = $S_2$
+ Gain on Futures = $F_1 - F_2$ *( = 0.98 - 0.925 = 0.055)*
+ Net amount received = $S_2 + (F_1 - F_2) = F_1 + b_2$ *( = 0.92 + 0.055 = 0.98 - 0.005 = 0.975)*

Choice of Contract

- Choose a delivery month that is as close as possible to, but later than, the
end of the life of the hedge.
- When there is no futures contract on the asset being hedged, choose the
contract whose futures price is most highly correlated with the asset price.
This is known as cross hedging.

## Cross Hedging

Proportion of the exposure that should optimally be hedged is $$h^{*} = \rho \frac{\sigma_S}{\sigma_F}$$ where

- $\sigma_S$ is the standard deviation of $\Delta S$, the change in the spot
price during the hedging period,
- $\sigma_F$ is the standard deviation of $\Delta F$, the change in the futures
price during the hedging period
- $\rho$ is the coefficient of correlation between $\Delta S$ and $\Delta F$.

Optimal Number of Contracts

- $Q_A$ = Size of position being hedged (units)
- $Q_F$ = Size of one futures contract (units)

Optimal number of contracts if not adjusted for daily settlement:
$$N^{*} = h^{*} \times \frac{Q_A}{Q_F}$$

Example:

- Airline will purchase 2 million gallons of jet fuel in one month and hedges
using heating oil futures.
- From historical data $\sigma_F = 0.0313$, $\sigma_S = 0.0263$, and $\rho = 0.928$

$$h^{*} = 0.928 \times \frac{0.0263}{0.0313} = 0.78$$

- The size of one heating oil contract is 42,000 gallons
- Optimal number of contracts is

$$0.78 \times \frac{2,000,000}{42,000} = 37$$

### Daily Settlement

Optimal hedge ratio is
$$\hat{h} = \hat{\rho} \frac{\hat{\sigma_S}}{\hat{\sigma_F}}$$

where variables are defined as follows

- $\hat{\rho}$ = Correlation between percentage daily changes for spot and
futures
- $\hat{\sigma_S}$ = SD of percentage daily changes in spot
- $\hat{\sigma_F}$ = SD of percentage daily changes in futures

Optimal Number of Contracts

- $V_A$ = Value of position being hedged = spot price $\times$ $Q_A$
- $V_F$ = Value of one futures contract = futures price $\times$ $Q_F$

Optimal number of contracts after 'tailing adjustment' to allow for
daily settlement of futures $$N^{*} = \hat{h} \times \frac{V_A}{V_F}$$

## Stock Index Futures

- To hedge the risk in a portfolio the number of contracts that should be
shorted is

$$\beta \times \frac{V_A}{V_F}$$

- where $V_A$ is the value of the portfolio,
- $\beta$ is its beta, and
- $V_F$ is the value of one futures contract

Example:

- S&P 500 futures price is 1,000
- Value of Portfolio is USD 5 million
- Beta of portfolio is 1.5
- Each future contract is on \$250 times the index

What position in futures contracts on the S&P 500 is necessary to hedge
the portfolio?

$$1.5 \times \frac{5~000~000}{250~000} = 30$$

Changing Beta

- What position is necessary to reduce the beta of the portfolio to 0.75?
- What position is necessary to increase the beta of the portfolio to 2.0?

$$(\beta^{*} - \beta) \times \frac{V_A}{V_F}$$

- $\beta^{*}$ = new beta
- $\beta$ = initial beta
- negative value means short futures, positive value means long futures

Why Hedge Equity Returns

- May want to be out of the market for a while. Hedging avoids the costs of
selling and repurchasing the portfolio.
- Suppose stocks in your portfolio have an average beta of 1.0, but you feel
they have been chosen well and will outperform the market in both good and bad
times. Hedging ensures that the return you earn is the risk-free return plus the
excess return of your portfolio over the market.

Stack and Roll

- We can roll futures contracts forward to hedge future exposures
- Initially we enter into futures contracts to hedge exposures up to a time
horizon
- Just before maturity we close them out an replace them with new contract
reflect the new exposure
- etc.

Liquidity Issues

- In any hedging situation there is a danger that losses will be realized on the
hedge while the gains on the underlying exposure are unrealized
- This can create liquidity problems
- One example is Metallgesellschaft which sold long term fixed-price contracts
on heating oil and gasoline and hedged using stack and roll
- The price of oil fell...