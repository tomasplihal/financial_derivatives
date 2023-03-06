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

# Stock and Option

Positions in an Option and the Underlying

![image](images/07-1-option-and-underlying.png)

- The profit patterns in the previous figure have the same general shape as the
profit patterns of options.
- a) short put, b) long put, c) long call, d) short call
- It can be explained by the put-call parity

 $$p + S_0 = c + K e^{-rT} + D$$