# 1.8: Derivatives With a Computation Graph

Here's the computation graph from before (but with some values this time):

![](images/1-8-1.png)

- Suppose you want to compute the derivative with respect to $v$ ($\frac{dJ}{dv}$)
  - $\frac{dJ}{dv} = 3$
  - This effectively steps back one node in the computation graph

- Suppose we want to compute $\frac{dJ}{da}$
  - Let's bump up $a$ from 5 to 5.001, giving us $v = 11.001$, moving $J$ to 33.003.
  - Thus, $\frac{dJ}{da} = 3$
  - Notice the Chain Rule here: $\frac{dJ}{da} = \frac{dJ}{dv} * \frac{dv}{da}$
    - In this case, $\frac{dv}{da} = 1$ and $\frac{dJ}{dv}  = 3$, making $\frac{dJ}{da} = 3$

- Lots of backprop stuff will be computing $\frac{d(\text{Final Output Variable})}{d(\text{Variable})}$
  - So in code, we'll write `dVariable` to describe this thing
    - For example, in the example above, $\frac{dJ}{da}$ would be coded as `da`

- Let's continue finding derivatives: $\frac{dJ}{du} = \frac{dJ}{dv} * \frac{dv}{du}$
  - $\frac{dJ}{du} = 3 * 1 = 3$
- Now, what about $\frac{dJ}{db}$?
  - Write it as a product due to the Chain Rule: $\frac{dJ}{db} = \frac{dJ}{du} * \frac{du}{db}$
    - $\frac{du}{db} = 2$ through the "bumpup method"
    - So $\frac{dJ}{db} = 3 * 2 = 6$
- Last one: $\frac{dJ}{dc}$
  - $\frac{dJ}{dc} = \frac{dJ}{du} * \frac{du}{dc} = 3*3=9$