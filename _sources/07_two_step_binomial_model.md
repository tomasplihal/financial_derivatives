# Two-Step Binomial Trees

## Valuing a Call Option

+ $K=21$, time step = 3 months
+ $r = 4\%$, $u = 1.1$, $d = 0.9$, $p = 0.5503$

- Value at node $C = 0 + 0 = 0 $
- Value at node $B = e^{-0.04 \times 0.25}(0.5503 \times 3.2 + 0.4497 \times 0) = 1.7433$
- Value at node $A = e^{-0.04 \times 0.25}(0.5503 \times 1.7433 + 0.4497\times 0) = 0.9497$

![image](images/07-16-valuing-call-option.png)

## Valuing a Put Option 

+ $K = 52$, time step = 1 year
+ $r = 5\%$, $u = 1.2$, $d = 0.8$, $p = 0.6282$

- Value at node
    $C = e^{-0.05 \times 1}(0.6282 \times 4 + 0.3718 \times 20) = 9.4636$
- Value at node
    $B = e^{-0.05 \times 1}(0.6282 \times 0 + 0.3718 \times 4) = 1.4147$
- Value at node $A = e^{-0.05 \times 1}(0.6282 \times 1.4147 + 0.3718 \times 9.4636) = 4.1923$

![image](images/07-17-valuing-put-option.png)

## What Happens When the Put Option is American

- The American feature increases the value at node C from $9.4636$ to $12.0000$.
- This increases the value of the option from $4.1923$ to $5.0894$.
- Value at node $A = e^{-0.05 \times 1}(0.6282 \times 1.4147 + 0.3718 \times 12.0000) = 5.0894$

![image](images/07-18-american-put.png)

## Choosing $u$ and $d$

- One way of matching the volatility is to set:

    $$u = e^{\sigma \sqrt{\Delta t}}$$
    $$d = \frac{1}{u} = e^{- \sigma \sqrt{\Delta t}}$$

- where $\sigma$ is the volatility and $\Delta t$ is the length of the time
step.
- This is the approach used by Cox, Ross, and Rubinstein (1979).

### Girsanov's Theorem

- Volatility is the same in the real world and the risk-neutral world.
- We can therefore measure volatility in the real world and use it to build a
tree for the an asset in the risk-neutral world.
