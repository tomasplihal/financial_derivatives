# Two-Step Binomial Trees

A Two-Step Example $K$=21; r = $4$%; each time step is 3 months

![image](images/07-15-two-step-tree.png)

Valuing a Call Option

![image](images/07-16-valuing-call-option.png)

- Value at node B =
    $e^{-0.04 \times 0.25}(0.5503 \times 3.2 + 0.4497 \times 0) = 1.7433$
- Value at node A =
    $e^{-0.04 \times 0.25}(0.5503 \times 1.7433 + 0.4497\times 0) = 0.9497$

A Put Option Example

- $K$ = 52, time step = 1 year
- $r$ = 5%, $u$ = 1.2, $d$ = 0.8, $p$ = 0.6282

![image](images/07-17-valuing-put-option.png)

What Happens When the Put Option is American

- The American feature increases the value at node C from 9.4636 to 12.0000.
- This increases the value of the option from 4.1923 to 5.0894.

![image](images/07-18-american-put.png)

Choosing $u$ and $d$

- One way of matching the volatility is to set:
    $$u = e^{\sigma \sqrt{\Delta t}}$$
    $$d = \frac{1}{u} = e^{- \sigma \sqrt{\Delta t}}$$
- where $\sigma$ is the volatility and $\Delta t$ is the length of the time
step.
- This is the approach used by Cox, Ross, and Rubinstein (1979).

Girsanov's Theorem

- Volatility is the same in the real world and the risk-neutral world.
- We can therefore measure volatility in the real world and use it to build a
tree for the an asset in the risk-neutral world.
