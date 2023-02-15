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

# Swaps

## Mechanics of Interest Rate Swaps

### Nature of Swaps

- A swap is an OTC contract
- A swap is subject to default risk
- A swap is negotiated between two parties and is customized
- A swap is an agreement to exchange cash flows at specified future times
according to certain specified rules.
- A forward contract is equivalent to the exchange of cash flows on just one
future date.
- Swaps typically lead to cash-flow exchanges taking place on
**several** future dates.
- A swap can be regarded as a convenient way of packaging forward contracts.
- When a swap is initiated the swap has zero value, but typically some forwards
have a positive value and some have a negative value.

### An Example of a "Plain Vanilla" Interest Rate Swap

- Three year swap between Apple and Citigroup.
- Apple agrees to pay to Citigroup an interest rate of 3% per annum every
six-month on a notional principal of \$100 million.
- Citigroup agrees to pay Apple the six-month LIBOR rate on the same notional
principal.
- Apple is the **fixed-rate payer**; Citigroup is the
**floating-rate payer**.
- Next slides illustrates cash flows that could occur (Day count conventions are
not considered).

Interest Rate Swap Between Apple and Citigroup

```{mermaid}
flowchart LR
    Citigroup -->|Floating| Apple
    Apple --> |3.0%| Citigroup
```
Cash flows to Apple for one possible outcome of the OIS in Figure 7.1.
The swap lasts two years and the notional principal is \$100 million

| Date          | SOFR rate (%) | Floating cash flow received (\$’000s) | Fixed cash flow paid (\$’000s) | Net cash flow (\$’000s) |
| ------------- | ------------- | ------------------------------------- | ------------------------------ | ----------------------- |
| June 8, 2022  | 2.20          | 550                                   | 750                            | -200                    |
| Sept. 8, 2022 | 2.60          | 650                                   | 750                            | -100                    |
| Dec. 8, 2022  | 2.80          | 700                                   | 750                            | -50                     |
| Mar. 8, 2023  | 3.10          | 775                                   | 750                            | +25                     |
| June 8, 2023  | 3.30          | 825                                   | 750                            | +75                     |
| Sept. 8, 2023 | 3.40          | 850                                   | 750                            | +100                    |
| Dec. 8, 2023  | 3.60          | 900                                   | 750                            | +150                    |
| Mar. 8, 2024  | 3.80          | 950                                   | 750                            | +200                    |

### Typical Uses of an Interest Rate

- Swap Converting a liability or an investment from:
    - fixed rate to floating rate
    - floating rate to fixed rate

Apple Transforms a Liability from Floating to Fixed

```{mermaid}
flowchart LR
    Citigroup -->|Floating| Apple
    Apple --> |3.0%| Citigroup
    Apple --> |Floating + 0.1%| X
```
Intel Transforms a Liability from Fixed to Floating

```{mermaid}
flowchart LR
    Citigroup -->|2.97%| Intel
    Intel --> |Floating| Citigroup
    Intel --> |3.2%| Y
```
Apple Transforms an Asset from Fixed to Floating

```{mermaid}
flowchart LR
    Citigroup -->|Floating| Apple
    Apple --> |3.0%| Citigroup
    X --> |2.7%| Apple
```

Intel Transforms an Asset from Floating to Fixed

```{mermaid}
flowchart LR
    Citigroup -->|2.97%| Intel
    Intel --> |Floating| Citigroup
    Y --> |Floating - 0.2%| Intel
```

### Quotes By a Swap Market Maker (Citigroup)

- Example of bid and offer fixed rates in the swap market for a swap where
payments are exchanged quarterly (percent per annum).
- Bid-offer spread is usually three to four basis points.

| Maturity (years) | Bid  | Ask  | Swap rate |
| ---------------- | ---- | ---- | --------- |
| 2                | 2.97 | 3.00 | 2.985     |
| 3                | 3.05 | 3.08 | 3.065     |
| 4                | 3.15 | 3.19 | 3.170     |
| 5                | 3.26 | 3.30 | 3.280     |
| 7                | 3.40 | 3.44 | 3.420     |
| 10               | 3.48 | 3.52 | 3.500     |

## The Comparative-Advantage Argument

The Comparative Advantage Argument Example

Borrowing rates that provide a basis for the comparative-advantage
argument.

- AAACorp wants to borrow floating
- BBBCorp wants to borrow fixed



Table 7.5 Borrowing rates that provide a basis for the comparative-advantage
argument. “Floating” is the floating reference rate.

|         | Fixed rate | Floating rate   |
| ------- | ---------- | --------------- |
| AAACorp | 4.0%       | Floating - 0.1% |
| BBBCorp | 5.2%       | Floating + 0.6% |

A Swap where Companies Trade Directly with Each Other

```{mermaid}
flowchart LR
    AAACorp --> |4%| X
    BBBCorp --> |4.35%| AAACorp
    BBBCorp --> |Floating + 0.6%| Y
    AAACorp --> |Floating| BBBCorp
```

The Swap when a Financial Institution is Involved

```{mermaid}
flowchart LR
    AAACorp --> |4%| X
    BBBCorp --> |4.37%| F[Financial institution]
    F --> |Floating| BBBCorp
    F --> |4.33%| AAACorp
    BBBCorp --> |Floating + 0.6%| Y
    AAACorp --> |Floating| F
```
Criticism of the Comparative Advantage Argument

- The 4.0% and 5.2% rates available to AAACorp and BBBCorp in fixed rate markets
are 5-year rates.
- The Floating-0.1% and Floating+0.6% rates available in the floating rate market are
6-month rates.
- BBBCorp's fixed rate depends on the spread above Floating it borrows at in the
future.

## Valuation of Interest Rate Swaps

- Initially interest rate swaps are worth close to zero
- At later times they can be valued as a portfolio of forward rate agreements
(FRAs).
- The procedure is to:
    1. Calculate LIBOR forward rates
    2. Calculate the swap cash flows that will occur if LIBOR forward rates are
    realized
    3. Discount these swap cash flows at the risk free rate (OIS)

### Example

- str 185 upravit zadani
- Swap involves paying 3% per annum and receiving LIBOR every six months on
\$100 million
- Swap has 1.2 years remaining (exchanges in 0.2, 0.7, 1.2 years)
- LIBOR rate applicable to exchange in 3 months was determined 3 months ago and
is 2.9%
- Forward LIBOR rates for 3-9 month period and 9-15 month periods are 3.429% and
3.734%, respectively
- OIS zero rates for maturities of 3, 9, and 15 months are 2.8%, 3.2%, and 3.4%,
respectively

Calculations (USD million)

| Time (years) | Fixed cash flow | Floating cash flow | Net cash flow | Discount factor | Present value of net cash flow |
| ------------ | --------------- | ------------------ | ------------- | --------------- | ------------------------------ |
| 0.2          | -1.500          | + 1.258            | -0.242        | 0.9944          | -0.241                         |
| 0.7          | -1.500          | + 1.694            | + 0.194       | 0.9778          | + 0.190                        |
| 1.2          | -1.500          | + 1.857            | + 0.357       | 0.9600          | + 0.343                        |
| Total        |                 |                    |               |                 | + 0.292                        |

## Fixed-for-Fixed Currency Swaps

An Example of a Fixed-for-Fixed Currency Swap

- Consider a hypothetical five-year currency swap agreement between British
Petroleum and Barclays.
- British Petroleum pays a fixed rate of interest of 3% in dollars to Barclays
and receives a fixed rate of interest of 4% in British pounds (sterling) from
Barclays.
- Interest rate payments are made once a year.
- The principal amounts are USD 15 million and GBP 10 million.
- This is termed a fixed-for-fixed currency swap because the interest rate in
both currencies is fixed.

Exchange of Principal

- In an interest rate swap the principal is not exchanged
- In a currency swap the principal **is exchanged** at the beginning and
the end of the swap

The Cash Flows

- Cash flows to British Petroleum in currency swap.
 
| Date             | Dollar cash flow (millions) | Sterling cash flow (millions) |
| ---------------- | --------------------------- | ----------------------------- |
| February 1, 2022 | +15.00                      | -10.00                        |
| February 1, 2023 | -0.45                       | + 0.40                        |
| February 1, 2024 | -0.45                       | + 0.40                        |
| February 1, 2025 | -0.45                       | + 0.40                        |
| February 1, 2026 | -0.45                       | + 0.40                        |
| February 1, 2027 | -15.45                      | + 10.40                       |

Typical Uses of a Currency Swap

- Conversion from a liability in one currency to a liability in another currency
- Conversion from an investment in one currency to an investment in another
currency

Comparative Advantage May Be Real Because of Taxes

- General Electric wants to borrow AUD
- Quantas wants to borrow USD
- Borrowing costs after adjusting for the differential impact of taxes could be:

|                  | USD* | AUD* |
| ---------------- | ---- | ---- |
| General Electric | 5.0% | 7.6% |
| Qantas Airways   | 7.0% | 8.0% |
(* Quoted rates have been adjusted to reflect the differential impact of taxes.)

A Currency Swap Motivated by Comparative Advantage

```{mermaid}
flowchart LR
    GE[General Electric] --> |USD 5%| X
    QA[Qantas Airways] --> |USD 6.3%| F[Financial institution]
    F --> |AUD 8.0%| QA
    F --> |AUD 6.9%| GE
    QA --> |AUD 8%| Y
    GE --> |AUD 6.9%| F
```

## Valuation of Fixed-for-Fixed Currency Swaps

- Each exchange of payments in a fixed-for-fixed currency swap is a forward
contract.
- Forward foreign exchange contracts can be valued by assuming that forward
exchange rates are realized.
- A fixed-for-fixed currency swap can therefore be valued assuming that forward
rates are realized.

### Example

- All Japanese interest rates are 1.5% per annum (cont. comp.)
- All USD interest rates are 2.5% per annum (cont. comp.)
- 3% is received in yen; 4% is paid in dollars.
- Payments are made annually
- Principals are USD 10 million and 1,200 million yen
- Swap will last for 3 more years
- Current exchange rate is 110 yen per dollar

Example of Valuation in Terms of Forward Rates

-   The current spot rate is 1/110 = 0.009091 dollar per yen.

-   In this case, $r = 2.5\%$ and $r_f = 1.5\%$ so that the one-year
    forward exchange rate is,
    $0.009091 e^{(0.025-0.015) \times 1} = 0.009182$

-   The two- and three-year forward exchange rates in the table are
    calculated similarly.

| Time (years) | Dollar cash flow | Yen cash flow | Forward exchange rate | Dollar value of yen cash flow | Net cash flow | Present value |
| ------------ | ---------------- | ------------- | --------------------- | ----------------------------- | ------------- | ------------- |
| 1            | -0.4             | + 36          | 0.009182              | 0.3306                        | -0.0694       | -0.0677       |
| 2            | -0.4             | + 36          | 0.009275              | 0.3339                        | -0.0661       | -0.0629       |
| 3            | -10.4            | + 1236        | 0.009368              | 11.5786                       | + 1.1786      | + 1.0934      |
| Total        |                  |               |                       |                               |               | + 0.9629      |

Other Currency Swaps - Fixed-for-Floating

- Fixed-for-floating: equivalent to a fixed-for-fixed currency swap plus a fixed
for floating interest rate swap
- An example of the first type of swap would be an exchange where Sterling LIBOR
on a principal of GBP 7 million is paid and 3% on a principal of \$10 million is
received with payments being made semiannually for 10 years.

1. a swap where 3% on a principal of \$10 million is received and (say) 4% on a
principal of GBP 7 million is paid
2. an interest rate swap where 4% is received and sterling LIBOR is paid on
anotional principal of GBP 7 million.

### Other Currency Swaps - Floating-for-Floating

- Floating-for-floating: equivalent to a fixed-for-fixed currency swap plus two
floating interest rate swaps
- An example of the second type of swap would be the exchange where sterling
LIBOR on a principal of GBP 7 million is paid and dollar LIBOR on a principal of
\$10 million is received.

1. a swap where 3% on aprincipal of \$10 million is received and 4% on a
principal of GBP 7 million is paid
2. an interest rate swap where 4% is received and sterling LIBOR is paid on a
notional principal of GBP 7 million
3. an interest rate swap where 3% is paid and USD LIBOR is received on a
notional principal of \$10 million.

## Other Types of Swaps

- Amortizing/step up
- Compounding swap
- Constant maturity swap
- LIBOR-in-arrears swap
- Accrual swap
- Equity swap
- Cross currency interest rate swap
- Floating-for-floating currency swap
- Diff swap
- Commodity swap
- Variance swap