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

# Introduction

## What is a Derivative?

- A derivative is a financial instrument whose value is **derived from** the value of **an underlying asset**.
- The underlying asset, called the underlying, trades in the cash or spot market and its price is called the cash or spot price.
- The underlying assets include stocks, currencies, interest rates, commodities, debt instruments, electricity prices, insurance payouts, the weather, etc.

## Why Derivatives Are Important?

Derivatives:
- play a key role in **transferring risks**,
- enable the creation of strategies and payoffs not otherwise possible with spot assets,
- provide information about the spot market,
- offer lower transaction costs,
- reduce the amount of capital required,
- are easier than the underlying to go short,
- improve the efficiency of spot markets.

## How Derivatives are Used?

- To hedge risks.
- To speculate (take a view on the future direction of the market).
- To lock in an arbitrage profit.
- To change the nature of a liability.
- To change the nature of an investment without incurring the costs of selling one portfolio and buying another.

## Derivative Markets

- Derivatives can be traded on an **organized exchange** or in **over-the-counter** (OTC) markets.
- Exchange-traded derivatives are **standardized**.
- OTC derivatives are **customized**.

### Exchange-traded Derivatives

- **Standardized** contract features such as:
  - Contract size
  - Expiration date
  - Underlying assets
- Exchange trades are **guaranteed by a clearing house** (margin required from participants).
- Transparency
- Regulation

### Over-The-Counter (OTC) Derivatives

- Flexibility in contract size and asset specification.
- Flexibility in expiration date.
- Greater risk of default (credit risk) for market participants.

+ The OTC Market Prior to 2008
    + Largely unregulated.
    + Banks acted as market makers quoting bids and offers.
    + Master agreements usually defined how transactions between two parties would be handled.
    + Some transactions were cleared through central counterparties (CCPs, comparable to clearing house).

- Since 2008
    - OTC market has become regulated.
        - Reduce systemic risk
        - Increase transparency
    - CCPs must be used to clear standardized transactions between financial institutions in most countries.
    - All trades must be reported to a central repository.

### The Lehman Bankruptcy

- Lehman's filed for bankruptcy on September 15, 2008.
- This was the biggest bankruptcy in US history.
- Lehman was an active participant in the OTC derivatives markets and got into financial difficulties because it took high risks and found it was unable to roll over its short term funding.
- It had hundreds of thousands of transactions outstanding with about 8,000 counterparties.
- Unwinding these transactions has been challenging for both the Lehman liquidators and their counterparties.

<!---
# https://www.bis.org/statistics/extderiv.htm?m=2616
# zkusit stahnout statistiku obratu otc vs exchange traded jako hull
-->