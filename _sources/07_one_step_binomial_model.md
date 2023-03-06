# A One-Step Binomial Model and A No-Arbitrage Argument

A Simple Binomial Model - Call option

- A 3-month call option on the stock has a strike price of \$21
- A stock price is currently \$20
- In 3 months it will be either \$22 or \$18

![image](images/07-13-simple-binomial-model.png)

Setting Up a Riskless Portfolio

- For a portfolio that is long $\Delta$ shares and a short 1 call
  option
- Calculate the value of $\Delta$ that makes the portfolio riskless
  $$22 \Delta - 1 = 18 \Delta - 0$$ $$\Delta = 0.25$$
- A riskless portfolio is therefore Long 0.25 shares + short 1 option.

Valuing the Portfolio (Risk-Free Rate is 4%)

- The riskless portfolio is: long 0.25 shares and short 1 call option
- The value of the portfolio in 3 months is:
  $$22 \times 0.25 - 1 = 4.50$$
- The value of the portfolio today is:
  $$4.5e^{-0.04 \times 0.25} = 4.455$$

Valuing the Option

- The portfolio that is long 0.25 shares and short 1 option is worth 4.455
- The value of the shares is 5.000 ($= 0.25 \times 20$)
- The value of the option is therefore 5.000 -- 4.455 = 0.545

Generalization

![image](images/07-14-generalization.png)

Generalization The value of the portfolio at the end of the life of the
option is:

- If there is an up movement $= S_0u\Delta - f_u$
- If there is a down movement $=S_0d\Delta - f_d$
- The portfolio is riskless when
    $$S_0 u \Delta - f_u = S_0 d \Delta - f_d$$
    $$\Delta = \frac{f_u - f_d}{S_0 u - S_0 d}$$
- In this case, the portfolio is riskless and, for there to be no
    arbitrage opportunities, it must earn the risk-free interest rate.
- It shows that $\Delta$ is the ratio of the change in the option
    price to the change in the stock price as we move between the nodes
    at time $T$.

Generalization

- Value of the portfolio at time $T$ is $$S_0 u \Delta - f_u$$
- Value of the portfolio today is $$(S_0 u \Delta - f_u)e^{-rT}$$
- The cost of setting up the portfolio today (another expression for
    the portfolio value today) is $$S_0 \Delta - f$$
- Hence $$f = S_0 \Delta - (S_0 u \Delta - f_u)e^{-rT}$$

Generalization Substituting for $\Delta$ we obtain:
$$f = [pf_u + (1 - p)f_d]e^{-rT}$$

where $$p = \frac{e^{rT} - d}{u - d}$$

$p$ as a Probability

- It is natural to interpret $p$ and $1-p$ as probabilities of up and down
movements.
- The value of a derivative is then its expected payoff in a risk-neutral world
discounted at the risk-free rate.

Example

- In the numerical example considered previously we have:
- $u = 1.1$, $d=0.9$, $r=0.04$, $T=0.25$, $f_u = 1$, and $f_d = 0$

$$p = \frac{e^{0.04 \times 0.25} - 0.9}{1.1 - 0.9} = 0.5503$$

$$f = e^{-0.04 \times 0.25} (0.5503 \times 1 + 0.4497 \times 0) = 0.545$$
