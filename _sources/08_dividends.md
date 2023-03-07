# Dividends

- European options on dividend-paying stocks are valued by substituting the
stock price less the present value of dividends into Black-Scholes.
- Only dividends with ex-dividend dates during life of option should be
included.
- The "dividend" should be the expected reduction in the stock price expected
during the life of the option.

## American Calls

- An American call on a non-dividend-paying stock should never be exercised
early.
- An American call on a dividend-paying stock should only ever be exercised
immediately prior to an ex-dividend date.
- Suppose dividend dates are at times $t_1, t_2, \dots t_n$.
- Early exercise is sometimes optimal at time $t_i$ if the dividend at that time
is greater than 

$$K[1 - e^{-r (t_{i+1} - t_i)}]$$

## Black's Approximation

- For dealing with dividends in American call options.
- Set the American price equal to the maximum of two European prices:
    1. The 1st European price is for an option maturing at the same time as the
    American option.
    2. The 2nd European price is for an option maturing just before the final
    ex-dividend date.