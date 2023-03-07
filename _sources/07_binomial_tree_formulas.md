# The Binomial Tree Formulas

- the size of an up and down move: 

$$u = e^{\sigma \sqrt{\Delta t}}$$
$$d = \frac{1}{u} = e^{- \sigma \sqrt{\Delta t}}$$

- probability of an up move: 

$$p = \frac{a - d}{u - d}$$
$$a = e^{r\Delta t}$$

- option value (one step): 

$$f = [pf_u + (1 - p)f_d]e^{-rT}$$

## Other Types of Assets

- For options on stock indices, currencies and futures the basic procedure for
constructing the tree is the same except for the calculation of $p$:

$$p = \frac{a - d}{u - d}$$

- $a = e^{r\Delta t} \dots$ for a nondividend paying stock
- $a = e^{(r-q)\Delta t} \dots$ for a stock index where $q$ is the dividend yield on
the index
- $a = e^{(r - r_f) \Delta t} \dots$ for a currency where $r_f$ is the foreign
risk-free rate
- $a = 1 \dots$ for a futures contract
