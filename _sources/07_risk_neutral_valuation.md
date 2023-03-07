# Risk-Neutral Valuation

- When the probability of an up and down movements are $p$ and $1-p$
  the expected stock price at time $T$ is $S_0e^{rT}$
- This shows that the stock price earns the risk-free rate.
- Binomial trees illustrate the general result that to value a
  derivative we can assume that the expected return on the underlying
  asset is the risk-free rate and the discount rate is also the
  risk-free rate.
- This is known as using risk-neutral valuation.

```{admonition} Example Revisited

- In the numerical example considered previously we have:
- $u = 1.1$, $d=0.9$, $r=0.04$, $T=0.25$, $f_u = 1$, and $f_d = 0$

$$22p + 18(1-p) = 20 e^{0.04 \times 0.25} \Rightarrow  p = 0.5503$$

- At the end of the 3 months, the call option has a 0.5503 probability of being
worth 1 and a 0.4497 probability of being worth zero.
- Its expected value is therefore:

$$0.5503 \times 1 + 0.4497 \times 0 = 0.5503$$

- In a risk-neutral world this should be discounted at the risk-free rate.
- The value of the option today is therefore:

$$0.5503 e^{-0.04 \times 0.25} = 0.545$$

- This is the same as the value obtained earlier, demonstrating that
no-arbitrage arguments and risk-neutral valuation give the same answer.
```

## Irrelevance of Stock's Expected Return

- When we are valuing an option in terms of the price of the underlying asset,
the probability of up and down movements in the real world are irrelevant.
- The probabilities of future up or down movements are already incorporated into
the stock price: we do not need to take them into account again when valuing the
option in terms of the stock price.
- This is an example of a more general result stating that the expected return
on the underlying asset in the real world is irrelevant.
