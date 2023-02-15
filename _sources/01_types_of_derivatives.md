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
import plotly.express as px
```

# Types of Derivatives

- **Forward Commitments** - Agreements to transact at a later date
    - Forward Contracts
    - Futures Contracts
    - Swaps

+ **Contingent Claims** - Give the holder the right to make a transaction
    + Options

## Forward Contracts vs. Contingent Claims 

- Both forward contracts and contingent claims derive their values from the performance of an underlying asset.
- A **forward contract** represents an **obligation** to trade the agreed upon asset at a future date. The potential loss on a long forward contract can be as great as the full contract price. For a short forward contract, the loss can be infinite.
- A **contingent claim** grants the holder the **right** to trade, but he/she is not obligated to do so. The most the buyer can lose on a contingent claim is the premium paid for that claim. 

## Forward Contract

- A **forward contract** is an over-the-counter derivative contract in which two parties agree that one party, the buyer, will purchase an underlying asset from the other party, the seller, at a later date at a fixed price they agree on when the contract is signed.
- The party that has agreed to **buy** has what is termed a **long** position.
- The party that has agreed to **sell** has what is termed a **short** position.

+ Characteristics of a forward contract:
    + Underlying asset type and quantity to be traded.
    + Manner in which the contract will be executed or settled when it expires.
    + A fixed price, called the **forward price**, at which the underlying will be exchanged.

- Forward contracts on foreign exchange are very popular.
- Traded in the OTC markets (at least one side is usually a financial institution).
- The forward price for a contract is the delivery price that would be applicable to the contract if were negotiated today (i.e., it is the delivery price that would make the contract worth exactly zero).
- The forward price may be different for contracts of different maturities.

## Futures Contract    

- A futures contract is similar to a forward contract but is a **standardized** derivative contract created and traded on a **futures exchanges**. 

## Forwards vs. Futures

- Forwards:
    - Agreement to buy or sell an underlying asset at a later date.
    - Traded OTC with customized features.
    - Not guaranteed by a clearinghouse; Limited regulation and reporting.
    - Gains and losses settled at maturity.

+ Futures Contracts
    + Agreement to buy or sell an underlying asset at a later date.
    + Exchange traded with standardized features.
    + Regulated, transparent, and traded through a clearinghouse.
    + Daily settlement of gains and losses.

## Swap

- A swap is an over-the-counter derivative contract in which two parties agree to exchange a series of cash flows.

A swap is similar to a forward contract:
However, a Swap is used to hedge multi-period risk, whereas a forward contract

## Options

- An option is a derivative contract in which one party, the buyer, pays a sum of money to the other party, the seller or writer, and receives the right to either buy or sell an underlying asset at a fixed price either on a specific expiration date or at any time prior to the expiration date.
- A **call** is an option that provides the right to **buy** the underlying.
- A **put** is an option that provides the right to **sell** the underlying.
- An **American option** can be exercised at any time during its life.
- A **European option** can be exercised only at maturity.