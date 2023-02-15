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

# Forwards and Futures

- Agreement to buy or sell an underlying asset at a later date.
- A **forward/futures contract** represents an **obligation** to trade the agreed upon
asset at a future date.
- A **forward/futures contract** is a derivative contract in which two parties agree that one party, the buyer, will purchase an underlying asset from the other party, the seller, at a later date at a fixed price they agree on when the contract is signed.
- A fixed price, called the **forward/futures price**, at which the underlying will be exchanged.
- The forward/futures price may be different for contracts of different maturities.
- The party that has agreed to **buy** has what is termed a **long** position.
- The party that has agreed to **sell** has what is termed a **short** position.
- The potential loss on a long forward contract can be as great as the full
contract price. 
- For a short forward contract, the loss can be infinite.
- Specifications need to be defined:
    - What can be delivered,
    - Where it can be delivered,
    - When it can be delivered

```{code-cell}
:tags: [remove-input]

K = 100
df = pd.DataFrame()
df['S'] = pd.Series(range(0,201))
df['profit'] = df['S'] - K 
alt.Chart(df).mark_line().encode(
    x='S',
    y='profit'
).properties(
    title='Long Forward/Futures, K=100'
)
```

```{code-cell}
:tags: [remove-input]

K = 100
df = pd.DataFrame()
df['S'] = pd.Series(range(0,201))
df['profit'] = K - df['S'] 
alt.Chart(df).mark_line().encode(
    x='S',
    y='profit'
).properties(
    title='Short Forward/Futures, K=100'
)
```

## Forward Contracts vs Futures Contracts

| Forward                                              | Futures                                                    |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| Private contract between two parties (OTC market)    | Traded on an exchange                                      |
| Not standardized (customized features)               | Standardized contract                                      |
| Usually one specified delivery date                  | Range of delivery dates                                    |
| Gains and losses settled at maturity                 | Daily settlement of gains and losses.                      |
| Delivery or final cash settlement                    | Contract is usually closed out prior to maturity           |
| Some credit risk (not guaranteed by a clearinghouse) | Virtually no credit risk (traded trough a clearinghouse)   |
| Limited regulation and reporting                     | Regulated, transparent, and traded through a clearinghouse |

---

## Payoff From a Forward Contract

Assumptions and symbol definitions:
- Contract initiated at time $t = 0$
- Contract expiration at time $t = T$
- Spot price of the underlying asset at time $0 = S_0$
- Spot price of the underlying asset at time $T = S_T$
- $F_0(T)$ is the forward price

+ The **long party agrees to buy** at the forward price, and the **short party agrees to sell** at the forward price.
+ Payoff to the **long party** at expiration $(T) = S_T - F_0(T)$
+ Payoff to the **short party** at expiration $(T) = -[S_T - F_0(T)]$

```{admonition} Forward Payoff Example
:class: tip

Barbara Nix agrees to buy 1 kilogram of gold in 90 days at a price of \$38,000 from PM metals Inc (short party). After 90 days, the spot price of gold is \$38,500 per kilo.

$$F_0(T) = \$38,000/kilo$$
$$S_T = \$38,500/kilo$$

Payoff to the long party (Nix) at expiration: 
$$(T) = S_T - F_0(T) = \$38,500 - \$38,000 = \$500$$

Payoff to the short party at expiration:
$$(T) = -\$500$$
```

```{admonition} Example
:class: tip

- On May 3, 2016, the treasurer of a corporation enters into a long forward
contract to buy GBP 1 million in six months at an exchange rate of 1.4561
- This obligates the corporation to pay USD 1,456,100 for GBP 1 million on
November 3, 2016
- What are the possible outcomes?
```

## Daily Settlement of Futures 

[Gold Futures Trading](https://www.cmegroup.com/markets/metals/precious/gold.quotes.html])

The clearinghouse determines the settlement price from the final trades made
that day. Positions are marked to market based on the settlement price. Gains
(losses) are added (subtracted) daily in the trader's margin account.

The exchange sets two margin requirements:
- **Initial Margin:** the deposit required to open the contract.
- **Maintenance Margin:** the amount of money that each participant must
maintain in the account after the trade is initiated. Accounts below the
maintenance margin will receive a **margin call**.

If a party receives a *margin call*, they must restore the account *to the
initial margin* by depositing more funds and/or by closing out positions.

### Example of Daily Settlement 
A trader goes long at a futures price of \$1200. The exchange requires an
initial margn (IM) of \$150 and a maintenance margin (MM) of \$75. The trader
deposits \$150 into a margin account to open a long position at \$1200.

- At the end of the day 1, the futures price settles at \$1180.
    * The account is marked to market at \$1180 and \$20 is withdrawn from the
        trader's account bringing the balance to \$130.

- At the end of day 2, the futures price settles at \$1120.
    * The account is marked to market at \$1120, and \$60 is withdrawn from the
        trader's account bringing the balance to \$70.
    * The margin balance is below the MM, so the trader receives a margin call.
    * To keep the long position opened, the trader must deposit enough money toi
        bring the account back to IM. In this case \$80 must be deposited.