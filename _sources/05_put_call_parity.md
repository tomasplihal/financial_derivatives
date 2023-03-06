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

# Put-Call Parity

## Put-Call Parity: No Dividends

- Consider the following 2 portfolios:
  - Portfolio A: European call on a stock + zero-coupon bond that pays $K$ at
  time $T$
- Portfolio C: European put on the stock + the stock

+ Values of Portfolios Portfolios illustrating put-call parity:

|             |                  | $S_T > K$ | $S_T < K$ |
| ----------- | ---------------- | :-------: | :-------: |
| Portfolio A | Call option      | $S_T - K$ |    $0$    |
|             | Zero-coupon bond |    $K$    |    $K$    |
|             | **Total**        |   $S_T$   |    $K$    |
| Portfolio C | Put Option       |    $0$    | $K - S_T$ |
|             | Share            |   $S_T$   |   $S_T$   |
|             | **Total**        |   $S_T$   |    $K$    |

- Both portfolios are worth $max(S_T , K)$ at the maturity of the options.
- They must therefore be worth the same today.
- This means that:
   $$c + K e^{-rT} = p + S_0$$

Put-Call Parity Arbitrage ($S_0$ = \$31, $r$ = 10%, $c$ = \$3, $K$ = \$30) 

| Three-month put price = \$2.25      | Three-month put price = \$1         |
| ----------------------------------- | ----------------------------------- |
| *Action now:*                       | *Action now:*                       |
| Buy call for \$3                    | Borrow \$29 for 3 months            |
| Short put to realize \$2.25         | Short call to realize \$3           |
| Short the stock to realize \$31     | Buy put for \$1                     |
| Invest \$30.25 for 3 months         | Buy the stock for \$31              |
| ...                                 |                                     |
| *Action in 3 months if* $S_T > 30$: | *Action in 3 months if* $S_T > 30$: |
| Receive \$31.02 from investment     | Call exercised: sell stock for \$30 |
| Exercise call to buy stock for \$30 | Use \$29.73 to repay loan           |
| Net profit = \$1.02                 | Net profit = \$0.27                 |
| ...                                 |                                     |
| *Action in 3 months if* $S_T < 30$: | *Action in 3 months if* $S_T < 30$: |
| Receive \$31.02 from investment     | Exercise put to sell stock for \$30 |
| Put exercised: buy stock for \$30   | Use \$29.73 to repay loan           |
| Net profit = \$1.02                 | Net profit = \$0.27                 |

## American Options

- Put–call parity holds only for European options.
- However, it is possible to derive upper and lower bounds for American option prices.
- It can be shown that, when there are no dividends,

$$ S_0 - K \leq C -P \leq S_0 - Ke^{-rT} $$