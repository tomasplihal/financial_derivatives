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

# Effect of Dividends

- We assume that the dividends that will be paid during the life of the option
are known.
- We will use $D$ to denote the present value of the dividends during the life
of the option.
- A dividend is assumed to occur at the time of its ex-dividend date.
- When dividends are expected, we can no longer assert that an American call
option will not be exercised early.
- Sometimes it is *optimal to exercise* an American call immediately prior to an
ex-dividend date.
- **It is never optimal to exercise a call at other times.**

## The Impact of Dividends on Lower Bounds to Option Prices

$$c \geq S_0 - D - K e^{-rT}$$

$$p \geq D + K e^{-rT} - S_0$$

## Extensions of Put-Call Parity

- American options; D = 0 $ \rightarrow S_0 - K < C -P < S_0 - K e^{-rT}$
- European options; D > 0 $ \rightarrow c + D + K e^{-rT} = p + S_0$
- American options; D > 0 $ \rightarrow S_0 - D - K < C - P < S_0 - K e^{-rT}$