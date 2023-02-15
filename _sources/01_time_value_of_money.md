# Time Value of Money

## Compounding Frequency

- When we compound $m$ times per year at rate $r$ an amount $P$ grows to $P(1+r/m)^m$ in one year.
- The compounding frequency used for an interest rate is the unit of measurement.
- The difference between quarterly and annual compounding is analogous to the
difference between miles and kilometers.
- Effect of the compounding frequency on the value of \$100 at the end of 1 year
when the interest rate is 10% per annum.

| Compounding frequency | Value of \$100 at end of year ($) |
| --------------------- | --------------------------------- |
| Annually m = 1        | 110.00                            |
| Semiannually m = 2    | 110.25                            |
| Quarterly m = 4       | 110.38                            |
| Monthly m = 12        | 110.47                            |
| Weekly m = 52         | 110.51                            |
| Daily m = 365         | 110.52                            |

## Continuous Compounding

- **Rates used in option pricing are nearly always expressed with continuous compounding.**
- In the limit as we compound more and more frequently we obtain continuously compounded interest rates.
- USD 100 grows to USD $$100 \times e^{rT}$$ when invested at a continuously compounded rate $r$ for time $T$.
- USD 100 received at time $T$ discounts to USD $$100 \times e^{-rT}$$ at time zero when the continuously compounded discount rate is $r$.

## Conversion Formulas

- $r_c$: continuously compounded rate
- $r_m$: same rate with compounding $m$ times per year

$$ r_c = m \ln (1+ \frac{r_m}{m}) $$

$$ r_m = m(e^{r_c/m} - 1) $$

Examples:

- 10% with semiannual compounding is equivalent to $2 \ln (1.05) = 9.758\%$ with continuous compounding.
- 8% with continuous compounding is equivalent to $4(e^{0.08/4} - 1) = 8.08\%$ with quarterly compounding.