# Forward Rate Agreement (FRA)

<!-- Forward Rates

- The forward rate is the future zero rate implied by today's term structure of
interest rates

Formula for Forward Rates

- Suppose that the zero rates for time periods $T_1$ and $T_2$ are $R_1$ and
$R_2$ with both rates continuously compounded.
- The forward rate for the period between times $T_1$ and $T_2$ is $$\frac{R_2
T_2 - R_1 T_1}{T_2 - T_1}$$
- This formula is only approximately true when rates are not expressed with
continuous compounding

Application of the Formula

Instantaneous Forward Rate The instantaneous forward rate for a maturity
T is the forward rate that applies for a very short time period starting
at T. It is

$$R + T \frac{\partial R}{\partial T}$$ where R is the T-year rate

Upward vs Downward Sloping Yield Curve

- For an upward sloping yield curve: Fwd Rate \> Zero Rate \> Par Yield
- For a downward sloping yield curve: Par Yield \> Zero Rate \> Fwd Rate -->


- A forward rate agreement (FRA) is an OTC agreement that a certain rate will
apply to a certain principal during a certain future time period.

Forward Rate Agreement: Key Results

- An FRA is equivalent to an agreement where interest at a predetermined rate,
$R_K$ is exchanged for interest at the market rate.
- An FRA can be valued by assuming that the forward LIBOR interest rate, $R_F$,
is certain to be realized.
- This means that the value of an FRA is the present value of the difference
between the interest that would be paid at interest at rate $R_F$ and the
interest that would be paid at rate $R_K$.

Valuation Formulas

- If the period to which an FRA applies lasts from $T_1$ to $T_2$, we assume
that $R_F$ and $R_K$ are expressed with a compounding frequency corresponding to
the length of the period between $T_1$ and $T_2$.
- With an interest rate of $R_K$, the interest cash flow is $R_K(T_2 - T_1)$ at
time $T_2$.
- With an interest rate of $R_F$, the interest cash flow is $R_F(T_2 - T_1)$ at
time $T_2$.
- When the rate $R_K$ will be received on a principal of L the value of the FRA
is the present value of $(R_K - R_F) (T_2 - T_1)$ received at time $T_2$.
- When the rate $R_K$ will be received on a principal of L the value of the FRA
is the present value of $(R_F - R_K) (T_2 - T_1)$ received at time $T2$.

Example

- An FRA entered into some time ago ensures that a company will receive 4%
(s.a.) on USD 100 million for six months starting in 1 year.
- Forward LIBOR for the period is 5% (s.a.).
- The 1.5 year risk-free rate is 4.5% with continuous compounding.
- The value of the FRA (in USD millions) is.

$$100 \times (0.04 - 0.05) \times 0.5 \times e^{-0.045 \times 0.5} = -0.467$$

- If the six-month LIBOR interest rate in one year turns out to be 5.5% (s.a.)
there will be a payoff (in USD millions) of $ 100 \times (0.04 - 0.055) \times 0.5 = -0.75 $ in 1.5 years.
- The transaction might be settled at the one- year point for the present value
of this.