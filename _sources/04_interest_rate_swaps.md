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

# Interest Rate Swaps

## An Example of a "Plain Vanilla" Interest Rate Swap

- Three year swap between Apple and Citigroup.
- Apple agrees to pay to Citigroup an interest rate of 3% per annum every
six-month on a notional principal of \$100 million.
- Citigroup agrees to pay Apple the six-month LIBOR rate on the same notional
principal.
- Apple is the **fixed-rate payer**; Citigroup is the
**floating-rate payer**.

![image](images/05-2-apple-citi-1.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    Citigroup --|Floating| Apple
    Apple -- |3.0%| Citigroup
``` 
-->

- Cash flows to Apple for one possible outcome of the OIS, the swap lasts two years and the notional principal is \$100 million.

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

---

## Typical Uses of an Interest Rate Swap

- Swap Converting a liability or an investment from:
    - fixed rate to floating rate
    - floating rate to fixed rate

+ Apple Transforms a **Liability** from Floating to Fixed:

![image](images/05-3-apple-citi-2.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    Citigroup --|Floating| Apple
    Apple -- |3.0%| Citigroup
    Apple -- |Floating + 0.1%| X
``` 
-->

- Intel Transforms a **Liability** from Fixed to Floating:

![image](images/05-5-intel-citi-2.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    Citigroup --|2.97%| Intel
    Intel -- |Floating| Citigroup
    Intel -- |3.2%| Y
```
 -->

+ Apple Transforms an **Asset** from Fixed to Floating:

![image](images/05-6-apple-citi-3.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    X -- |2.7%| Apple
    Apple -- |3.0%| Citigroup
    Citigroup --|Floating| Apple
```
 -->

- Intel Transforms an **Asset** from Floating to Fixed:

![image](images/05-7-intel-citi-3.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    Y -- |Floating - 0.2%| Intel
    Intel -- |Floating| Citigroup
    Citigroup --|2.97%| Intel
```
 -->

<!-- ### Quotes By a Swap Market Maker (Citigroup)

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
| 10               | 3.48 | 3.52 | 3.500     | --> 

---

## The Comparative-Advantage Argument

- AAACorp wants to borrow floating.
- BBBCorp wants to borrow fixed.

+ Borrowing rates that provide a basis for the comparative-advantage
argument ("Floating" is the floating reference rate):

|         | Fixed rate |  Floating rate  |
| :-----: | :--------: | :-------------: |
| AAACorp |    4.0%    | Floating - 0.1% |
| BBBCorp |    5.2%    | Floating + 0.6% |

 - A Swap where companies trade directly with each other:

![image](images/05-10-swap-directly.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    AAACorp -- |4%| X
    BBBCorp -- |4.35%| AAACorp
    BBBCorp -- |Floating + 0.6%| Y
    AAACorp -- |Floating| BBBCorp
```
 -->

+ The swap when a financial institution is involved:

![image](images/05-11-swap-indirectly.png)

<!-- ```{mermaid}
:align: 'center'

flowchart LR
    AAACorp -- |4%| X
    BBBCorp -- |4.37%| F[Financial institution]
    F -- |Floating| BBBCorp
    F -- |4.33%| AAACorp
    BBBCorp -- |Floating + 0.6%| Y
    AAACorp -- |Floating| F
```
 -->

### Criticism of the Comparative Advantage Argument

- The 4.0% and 5.2% rates available to AAACorp and BBBCorp in fixed rate markets
are 5-year rates.
- The Floating-0.1% and Floating+0.6% rates available in the floating rate market are
6-month rates.
- BBBCorp's fixed rate depends on the spread above Floating it borrows at in the
future.

---

## Valuation of Interest Rate Swaps

- Initially interest rate swaps are worth close to zero.
- At later times they can be valued as a portfolio of forward rate agreements
(FRAs).
- The procedure is to:
  1. Calculate Floating forward rates.
  2. Calculate the swap cash flows that will occur if Floating forward rates are
  realized.
  3. Discount these swap cash flows at the risk free rate (OIS).

### Example

- Swap involves paying 3% per annum and receiving SOFR every six months on \$100 million.
- Swap has 1.2 years remaining (exchanges in 0.2, 0.7, 1.2 years).
- Risk-free (OIS) zero rates for maturities of 3, 9, and 15 months are 2.8%,
3.2%, and 3.4%, respectively.
- SOFR rate applicable to exchange in 3 months was determined 3 months ago and
is 2.9%
- Forward SOFR rates for exchanges in 0.2, 0.7, 1.2 years are:
  - with cointinuous compounding: 2.50%, 3.36%, 3.68%, respectively
  - with semi-annual compounding: 2.516%, 3.388%, 3.714%, respectively
- Calculations (USD million):

| Time (years) | Fixed cash flow | Floating cash flow | Net cash flow | Discount factor | Present value of net cash flow |
|:------------:|:---------------:|:------------------:|:-------------:|:---------------:|:------------------------------:|
| 0.2          | -1.500          | +1.258             | -0.242        | 0.9944          | -0.241                         |
| 0.7          | -1.500          | +1.694             | +0.194        | 0.9778          | +0.190                         |
| 1.2          | -1.500          | +1.857             | +0.357        | 0.9600          | +0.343                         |
| Total        |                 |                    |               |                 | +0.292                         |

- Consider, for example, the 0.7 year row.
- The fixed cash flow is $-0.5 \times 0.03 \times 100 = -\$1.500$.
- The floating cash flow, assuming forward rates are realized, is $0.5 \times 0.03388 \times 100 = \$1.694$.
- The net cash flow is therefore $-1.500 + 1.694 = \$0.194$ million.
- The discount factor is $e^{-0.032 \times 0.7} = 0.9778$, so that the present value is $0.194 \times 0.9778 = \$0.190$.
- The value of the swap is obtained by summing the present values $ = \$0.292$ million.
- Note that these calculations are approximate because they do not take account
of holiday calendars and day count conventions.