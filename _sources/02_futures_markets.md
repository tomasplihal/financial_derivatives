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

# Mechanics of Forward/Futures Markets

## Exchange Markets

- Trading of futures contracts.
- Specification of a futures contract [Gold Futures Quotes](https://www.cmegroup.com/markets/metals/precious/gold.quotes.html])
- In the US, the regulation of futures markets is primarily the responsibility
of the Commodity Futures and Trading Commission (CFTC).
- Regulators try to protect the public interest and prevent questionable trading
practices.

### Delivery

+ Most contracts are **closed out before maturity** (no delivery occurs).
+ Closing out a futures position involves entering into an offsetting trade.

- If a futures contract is not closed out before maturity, it is usually settled
by delivering the assets underlying the contract.
- When there are alternatives about **what** is delivered, **where** it is delivered,
and **when** it is delivered, the party with **the short position chooses**.
- A few contracts (for example, those on stock indices and Eurodollars) are
settled in cash.

### Market Quotes

- **Settlement price**: the price just before the final bell each day (used
for the daily settlement process).
- **Open interest**: the total number of contracts outstanding (equal to number
of long positions or number of short positions).
- **Volume of trading**: the number of trades in one day.

```{admonition} Questions
- When a new trade is completed what are the possible effects on the open
interest?
- Can the volume of trading in a day be greater than the open interest?
```

```{admonition} Foreign exchange quotes
:class: seealso dropdown

- Futures exchange rates are quoted as the number of USD per unit of the foreign
currency.
- Forward exchange rates are quoted in the same way as spot exchange rates. This
means that GBP, EUR, AUD, and NZD are quoted as USD per unit of foreign
currency. Other currencies (e.g., CAD and JPY) are quoted as units of the
foreign currency per USD.
```

### Margins

- A margin is cash or marketable securities deposited by an investor with his or
her broker.
- The balance in the margin account is adjusted to reflect daily settlement.
- Margins minimize the possibility of a loss through a default on a contract.

The exchange sets margin requirements:
- **Initial Margin:** the deposit required to open the contract.
- **Maintenance Margin:** the amount of money that each participant must
maintain in the account after the trade is initiated. 
- Accounts below the maintenance margin will receive a **margin call**.
- If a party receives a *margin call*, they must restore the account *to the
initial margin* by depositing more funds and/or by closing out positions.

<!-- #### Margin Cash Flows

- A trader has to bring the balance in the margin account up to the initial
margin when it falls below the maintenance margin level.
- A member of the exchange clearing house only has an initial margin and is
required to bring the balance in its account up to that level every day.
- These daily margin cash flows are referred to as variation margin.
- A member is also required to contribute to a default fund.

 + Table, generate?? -->

```{seealso}
:class: dropdown

- [Margin: Know What's Needed](https://www.cmegroup.com/education/courses/introduction-to-futures/margin-know-what-is-needed.html)
- [The Benefits of Futures Margins](https://www.cmegroup.com/education/courses/understanding-the-benefits-of-futures/the-benefits-of-futures-margins.html)
- [Understanding Futures Margin](https://www.schwab.com/learn/story/understanding-futures-margin)
```

### Daily Settlement of Futures 

- The clearinghouse determines the settlement price from the final trades made
that day.
- Positions are marked to market based on the settlement price.
- Gains(losses) are added (subtracted) daily in the trader's margin account.

### Example of Daily Settlement 

- A trader goes long at a futures price of \$1200.
- The exchange requires an initial margn (IM) of \$150 and a maintenance margin
(MM) of \$75. 
- The trader deposits \$150 into a margin account to open a long position at
\$1200.

+ At the end of the **day 1**, the futures price settles at \$1180.
  + The account is marked to market at \$1180 and \$20 is withdrawn from the
  trader's account bringing the balance to \$130.

- At the end of **day 2**, the futures price settles at \$1120.
  - The account is marked to market at \$1120, and \$60 is withdrawn from the
  trader's account bringing the balance to \$70.
  - The margin balance is below the MM, so the trader receives a margin call.
  - To keep the long position opened, the trader must deposit enough money to
  bring the account back to IM.
  - In this case \$80 must be deposited.

---

## OTC Markets

- Trading of forward contracts.
- Before the 2007–2008 credit crisis, the OTC market was largely unregulated.
- Since the crisis, the OTC market has been subject to a great deal of regulation. 
- Collateral requirements (initial and variational margin).
- Bilateral clearing: 
  - The traditional way in which OTC markets have operated. 
  - A series of bilateral agreements between market participants.

```{mermaid}
:align: 'center'

flowchart LR
    A <--> B
    B <--> C
    C <--> A
```
- Central clearing:
  - OTC markets operate with a single central counterparty (CCP) acting as a clearing house.

```{mermaid}
:align: 'center'

flowchart TD
    A <--> CCP
    B <--> CCP
    C <--> CCP
    CCP <--> D
    CCP <--> E
    CCP <--> F
```