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

## Forwards and Futures Characteristics

```{admonition} Definition
:class: tip

- Agreement to buy or sell an underlying asset at a later date.
- A **forward/futures contract** represents an **obligation** to trade the agreed upon
asset at a future date.
- A **forward/futures contract** is a derivative contract in which two parties agree that one party, the buyer, will purchase an underlying asset from the other party, the seller, at a later date at a fixed price they agree on when the contract is signed.
```

- A fixed price, called the **forward/futures price**, at which the underlying will be exchanged.
- The forward/futures price may be different for contracts of different maturities.

+ The party that has agreed to **buy** has what is termed a **long** position.
+ The party that has agreed to **sell** has what is termed a **short** position.
+ The potential loss on a long forward contract can be as great as the full
contract price. 
+ For a short forward contract, the loss can be infinite.

- Specifications need to be defined:
    - What can be delivered.
    - Where it can be delivered.
    - When it can be delivered.

```{code-cell}
:tags: [remove-input]

K = 100
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df["profit"] = df["S"] - K
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

```{code-cell}
:tags: [remove-input]

K = 100
df = pd.DataFrame()
df["S"] = pd.Series(range(0, 201))
df['profit'] = K - df['S'] 
chart = (
    alt.Chart(df)
    .mark_line()
    .encode(x="S", y="profit")
    .properties(title="Short Forward/Futures, K=100, at maturity")
)
xrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(x=alt.datum(100))
yrule = alt.Chart().mark_rule(strokeDash=[6, 6], strokeWidth=1).encode(y=alt.datum(0))

chart + xrule + yrule
```

---

## Forward Contracts vs. Futures Contracts

| Forwards                                             | Futures                                                    |
|:----------------------------------------------------:|:----------------------------------------------------------:|
| Private contract between two parties (OTC market)    | Traded on an exchange                                      |
| Not standardized (customized features)               | Standardized contract                                      |
| Usually one specified delivery date                  | Range of delivery dates                                    |
| Gains and losses settled at maturity                 | Daily settlement of gains and losses                      |
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
- $F_0$ is the forward price

+ The **long party agrees to buy** at the forward price, and the **short party agrees to sell** at the forward price.
+ Payoff to the **long party** at expiration $(T) = S_T - F_0$
+ Payoff to the **short party** at expiration $(T) = -[S_T - F_0]$

```{admonition} Forward Payoff Example
Barbara Nix agrees to buy 1 kilogram of gold in 90 days at a price of \$38,000 from PM metals Inc (short party). After 90 days, the spot price of gold is \$38,500 per kilo.

$$F_0 = \$38,000/kilo$$
$$S_T = \$38,500/kilo$$

Payoff to the long party (Nix) at expiration: 

$$S_T - F_0 = \$38,500 - \$38,000 = \$500$$

Payoff to the short party at expiration:

$$-\$500$$
```

```{admonition} Example
- On May 3, 2016, the treasurer of a corporation enters into a long forward
contract to buy GBP 1 million in six months at an exchange rate of 1.4561
- This obligates the corporation to pay USD 1,456,100 for GBP 1 million on
November 3, 2016
- What are the possible outcomes?
```