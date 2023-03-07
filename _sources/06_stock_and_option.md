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

- Following graphs shows positions in an option and the underlying.
- The profit patterns in the graphs have the same general shape as the profit
patterns of options.
    - a) short put 
    - b) long put
    - c) long call 
    - d) short call
- It can be explained by the put-call parity

 $$p + S_0 = c + K e^{-rT} + D$$

![image](images/07-1-option-and-underlying.png)