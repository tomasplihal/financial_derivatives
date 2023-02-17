# Forward Rate Agreement (FRA)

- A forward rate agreement (FRA) is an agreement to exchange a predetermined fixed
rate for a reference rate that will be observed in the market at a future time.
- Both rates are applied to a specified principal, but the principal itself is not exchanged.
- Historically, the reference rate has usually been LIBOR.

```{admonition} FRA Example
- Consider an agreement to exchange 3% for three-month LIBOR in two years with both rates being applied to a principal of $\$100$ million.
- One side (Party A) would agree to pay LIBOR and receive the fixed rate of 3%.
- The other side (Party B) would agree to receive LIBOR and pay the fixed rate of 3%.
- Assume all rates are compounded quarterly (as would usually be the case).
- If three-month LIBOR proved to be 3.5% in two years, Party A would receive from Party B:

$$ \$100,000,000 \times (0.035 - 0.030) \times 0.25 = \$ 125,000 $$

- The payment would be due at time 2.25 years.
- In practice, because LIBOR is determined in advance of a period, the payment would be made at time two years and equal to the present value of \$125,000 discounted for three months at 3.5%.
```

- As LIBOR is phased out, we can expect to see more FRAs based on floating rates
such as three-month SOFR and three-month SONIA.
- FRAs are a way of locking in the rate that will be paid or received in the future.
- For example, a trader who is due to receive a rate based on three-month SOFR on a certain principal during a certain future time period can lock in the rate by entering into an FRA where SOFR is paid and a fixed rate is received.
- Similarly, a trader who is due to pay a rate based on three-month SOFR on a certain principal during a certain future time period can lock in the rate by entering into an FRA where SOFR is received and a fixed rate is paid.

+ When the fixed rate equals the relevant forward rate the value of an FRA is zero.
+ When an FRA is first set up the fixed rate is normally equal to the forward rate, so that its value is zero. 
+ As time passes, the forward rate is liable to change. 