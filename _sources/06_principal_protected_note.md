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

# Principal Protected Note

- Allows investor to take a risky position without risking any principal.

```{admonition} Example
- USD 1000 instrument consisting of:
1. 3-year zero-coupon bond with principal of USD 1,000.
2. 3-year at-the-money call option on a stock portfolio.

- Suppose that the 3-year interest rate is 6% with continuous compounding.
- This means that $1,000 e^{-0.06 \times 3} = 835.27$ will grow to \$1,000 in 3
years.
- The difference between \$1,000 and \$835.27 is \$164.73.
- Suppose that a stock portfolio is worth \$1,000 and provides a dividend yield
of 1.5% per annum.
- Suppose further that a 3-year at-the-money European call option on the stock
portfolio can be purchased for less than \$164.73.
```

- **Viability depends on:**
    - Level of dividends
    - Level of interest rates
    - Volatility of the portfolio

+ **Variations on standard product:**
    - Out of the money strike price
    - Caps on investor return
    - Knock outs, averaging features, etc