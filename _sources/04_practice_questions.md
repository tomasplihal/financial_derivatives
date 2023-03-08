# Practice Questions and Problems

## Swaps


1. Companies A and B have been offered the following rates per annum on a \$20
million five-year loan:

|           | Fixed Rate |  Floating Rate   |
| :-------: | :--------: | :--------------: |
| Company A |   5.0\%    | Floating + 0.1\% |
| Company B |   6.4\%    | Floating + 0.6\% |

Company A requires a floating-rate loan; company B requires a fixed-rate loan.
Design a swap that will net a bank, acting as intermediary, 0.1\% per annum and
that will appear equally attractive to both companies.
    - (Problem 7.1., Hull 2018) A has an apparent comparative advantage in
    fixed-rate markets but wants to borrow floating. B has an apparent
    comparative advantage in floating-rate markets but wants to borrow fixed.
    This provides the basis for the swap. There is a 1.4\% per annum
    differential between the fixed rates offered to the two companies and a
    0.5\% per annum differential between the floating rates offered to the two
    companies. The total gain to all parties from the swap is therefore 1.4 -
    0.5 = 0.9\% per annum. Because the bank gets 0.1\% per annum of this gain,
    the swap should make each of A and B 0.4\% per annum better off. This means
    that it should lead to A borrowing at LIBOR -0.3\% and to B borrowing at
    6.0\%. The appropriate arrangement is therefore (nahore 5, 5.3, 5.4, libor +
    0.6; dole libor libor).
    

2. Company X wishes to borrow U.S. dollars at a fixed rate of interest. Company
Y wishes to borrow Japanese yen at a fixed rate of interest. The amounts
required by the two companies are roughly the same at the current exchange rate.
The companies have been quoted the following interest rates, which have been
adjusted for the impact of taxes:

|           |  Yen  | Dollars |
| :-------: | :---: | :-----: |
| Company X | 5.0\% |  9.6\%  |
| Company Y | 6.5\% | 10.0\%  |

Design a swap that will net a bank, acting as intermediary, 50 basis points per
annum. Make the swap equally attractive to the two companies and ensure that all
foreign exchange risk is assumed by the bank.
    - (Problem 7.2., Hull 2018) X has a comparative advantage in yen markets but
    wants to borrow dollars. Y has a comparative advantage in dollar markets but
    wants to borrow yen. This provides the basis for the swap. There is a 1.5\%
    per annum differential between the yen rates and a 0.4\% per annum
    differential between the dollar rates. The total gain to all parties from
    the swap is therefore 1.5 - 0.4 = 1.1\% per annum. The bank requires 0.5\%
    per annum, leaving 0.3\% per annum for each of X and Y. The swap should lead
    to X borrowing dollars at 9.6 - 0.3 = 9.3\% per annum and to Y borrowing yen
    at 6.5 - 0.3 = 6.2\% per annum. The appropriate arrangement is therefore
    (Nahore 5y, 5y, 6.2y, 10d,; dole 9.3d, 10d).


3. A \$100 million interest rate swap has a remaining life of 10 months. Under
the terms of the swap, six-month LIBOR is exchanged for 7\% per annum
(compounded semiannually). The average of the bid-offer rate being exchanged for
six-month LIBOR in swaps of all maturities is currently 5\% per annum with
continuous compounding. The six-month LIBOR rate was 4.6\% per annum two months
ago. What is the current value of the swap to the party paying floating? What is
its value to the party paying fixed?
    - (Problem 7.3., Hull 2018) In four months \$3.5 million (= 0.5 x 0.07 x
    \$100 million) will be received and \$2.3 million (= 0.5 x 0.046 x \$100
    million) will be paid. (We ignore day count issues.) In 10 months \$3.5
    million will be received, and the LIBOR rate prevailing in four months time
    will be paid. The value of the fixed-rate bond underlying the swap is $$
    3.5e^{-0.05 \times 4/12} + 103.5e^{-0.05 \times 10/12} = \$102.718 $$
    million. The value of the floating-rate bond underlying the swap is $$ (100
    + 2.3)e^{-0.05 \times 4/12} = \$100.609 million $$ The value of the swap to
    the party paying floating is \$102.718 - \$100.609 = \$2.109 million. The
    value of the swap to the party paying fixed is -\$2.109 million. These
    results can also be derived by decomposing the swap into forward contracts.
    Consider the party paying floating. The first forward contract involves
    paying \$2.3 million and receiving \$3.5 million in four months. It has a
    value of $ 1.2e^{-0.05 \times 4/12} = \$1.180 $ million. To value the second
    forward contract, we note that the forward interest rate is 5\% per annum
    with continuous compounding, or 5.063\% per annum with semiannual
    compounding. The value of the forward contract is $$ 100 \times (0.07 \times
    0.5 - 0.05063 \times 0.5)e^{-0.05 \times 10/12} = \$0.929 million $$ The
    total value of the forward contracts is therefore \$1.180 + \$0.929 =
    \$2.109 million.



4. A currency swap has a remaining life of 15 months. It involves exchanging
interest at 10\% on 20 million GBP for interest at 6\% on 30 million USD once a
year. The term structure of interest rates in both the United Kingdom and the
United States is currently flat, and if the swap were negotiated today the
interest rates exchanged would be 4\% in dollars and 7\% in sterling. All
interest rates are quoted with annual compounding. The current exchange rate
(dollars per pound sterling) is 1.5500. What is the value of the swap to the
party paying sterling? What is the value of the swap to the party paying
dollars?
    - (Problem 7.5., Hull 2018) The swap involves exchanging the sterling
    interest of 20 x 0.10 or GBP 2 million for the dollar interest of 30 x 0.06
    = \$1.8 million. The principal amounts are also exchanged at the end of the
    life of the swap. The value of the sterling bond underlying the swap is $$
    \frac{2}{(1.07)^{1/4}} + \frac{22}{(1.07)^{5/4}} = 22.182 $$ million pounds.
    The value of the dollar bond underlying the swap is $$
    \frac{1.8}{(1.04)^{1/4}} + \frac{31.8}{(1.04)^{5/4}} = 32.0.61 $$ million
    USD. The value of the swap to the party paying sterling is therefore $$
    32.061 - (22.182 \times 1.55) = -\$2.321 $$ million.
    - The value of the swap to the party paying dollars is \$2.321 million. The
    results can also be obtained by viewing the swap as a portfolio of forward
    contracts. The continuously compounded interest rates in sterling and
    dollars are 6.766\% per annum and 3.922\% per annum. The 3-month and
    15-month forward exchange rates are $ 1.55e^{(0.03922-0.06766) \times 0.25}
    = 1.5390 $ and $ 1.55e^{(0.03922-0.06766) \times 1.25} =1.4959 $. The values
    of the two forward contracts corresponding to the exchange of interest for
    the party paying sterling are therefore $$ (1.8-2 \times 1.5390)e^{-0.03922
    \times 0.25} = -\$1.2656 $$ million and $$ (1.8-2 \times 1.4959)e^{-0.03922
    \times 1.25} = -\$1.1347 $$ million The value of the forward contract
    corresponding to the exchange of principals is $$ (30-20 \times
    1.4959)e^{-0.03922 \times 1.25} = +\$0. 0787 $$ million The total value of
    the swap is -\$1.2656 -\$1.1347 +\$0.0787 million or -\$2.322 million (which
    allowing for rounding errors is the same as that given by valuing bonds).
    
5. Explain the difference between the credit risk and the market risk in a
financial contract.
    - (Problem 7.6., Hull 2018) Credit risk arises from the possibility of a
    default by the counterparty. Market risk arises from movements in market
    variables such as interest rates and exchange rates. A complication is that
    the credit risk in a swap is contingent on the values of market variables. A
    company's position in a swap has credit risk only when the value of the swap
    to the company is positive.

6. A corporate treasurer tells you that he has just negotiated a five-year loan
at a competitive fixed rate of interest of 5.2\%. The treasurer explains that he
achieved the 5.2\% rate by borrowing at six-month LIBOR plus 150 basis points
and swapping LIBOR for 3.7\%. He goes on to say that this was possible because
his company has a comparative advantage in the floating-rate market. What has
the treasurer overlooked?
    - (Problem 7.7., Hull 2018) The rate is not truly fixed because, if the
    company's credit rating declines, it will not be able to roll over its
    floating rate borrowings at LIBOR plus 150 basis points. The effective fixed
    borrowing rate then increases. Suppose, for example, that the treasurer's
    spread over LIBOR increases from 150 basis points to 200 basis points. The
    borrowing rate increases from 5.2\% to 5.7\%.


7. Explain why a bank is subject to credit risk when it enters into two
offsetting swap contracts.
    - (Problem 7.8., Hull 2018) At the start of the swap, both contracts have a
    value of approximately zero. As time passes, it is likely that the swap
    values will change, so that one swap has a positive value to the bank and
    the other has a negative value to the bank. If the counterparty on the other
    side of the positive-value swap defaults, the bank still has to honor its
    contract with the other counterparty. It is liable to lose an amount equal
    to the positive value of the swap.



8. Companies X and Y have been offered the following rates per annum on a \$5
million 10-year investment:

|           | Fixed Rate |  Floating Rate   |
| :-------: | :--------: | :--------------: |
| Company X |   8.0\%    | Floating |
| Company Y |   8.8\%    | Floating |

Company X requires a fixed-rate investment; company Y requires a floating-rate
investment. Design a swap that will net a bank, acting as intermediary, 0.2% per
annum and will appear equally attractive to X and Y.
    - (Problem 7.9., Hull 2018) The spread between the interest rates offered to
    X and Y is 0.8\% per annum on fixed rate investments and 0.0\% per annum on
    floating rate investments. This means that the total apparent benefit to all
    parties from the swap is 0.8\% perannum. Of this 0.2\% per annum will go to
    the bank. This leaves 0.3\% per annum for each of X and Y. In other words,
    company X should be able to get a fixed-rate return of 8.3\% per annum while
    company Y should be able to get a floating-rate return LIBOR + 0.3\% per
    annum. The required swap is shown in Figure 7.3. The bank earns 0.2\%,
    company X earns 8.3\%, and company Y earns LIBOR + 0.3\%. (Nahore Libor,
    8.3, 8.5, 8.8; dole libor, libor)


9. Why is the expected loss from a default on a swap less than the expected loss
from the default on a loan to the same counterparty with the same principal?
    - (Problem 7.15., Hull 2018) In an interest-rate swap a financial
    institution's exposure depends on the difference between a fixed-rate of
    interest and a floating-rate of interest. It has no exposure to the notional
    principal. In a loan the whole principal can be lost.
10. A bank finds that its assets are not matched with its liabilities. It is
taking floating-rate deposits and making fixed-rate loans. How can swaps be used
to offset the risk?
    - (Problem 7.16., Hull 2018) The bank is paying a floating-rate on the
    deposits and receiving a fixed-rate on the loans. It can offset its risk by
    entering into interest rate swaps (with other financial institutions or
    corporations) in which it contracts to pay fixed and receive floating.

