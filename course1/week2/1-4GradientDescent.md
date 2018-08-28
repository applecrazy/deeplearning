# 1.4: Gradient Descent

- How do we learn the parameters $w$ and $b$ to minimize the cost function?
  - Our goal is to find $w, b$ that minimize $J(w,b)$ using Gradient Descent

  ![](images/1-4-1.png)

- Gradient descent takes a step in the steepest downhill direction depending on where it starts


## Gradient Descent: Details
- Here's the gradient descent algorithm for a 2D space (only $w \in \mathbb{R}$)

```
repeat {
  w := w - alpha * derivative
}
```

- In a 2D space with only $w$ and $J(w)$, the `derivative` term is $\frac{dJ(w)}{dw}$
- But in Logistic Regression, the cost is $J(w,b)$, so here's the update rule:

```
repeat {
  w := w - alpha * dw
  b := b - alpha * db
}
```

- The `dw` term is the *partial derivative* with respect to $w$ and looks something like this:
$$ \frac{ \partial J(w,b) }{ \partial w }$$
- The `db` term is the *partial derivative* with respect to $b$ and looks something like this:
$$ \frac{ \partial J(w,b) }{ \partial b }$$

- **Note:** When do we use $\partial$ over $d$ in derivatives?
  - The $\partial$ symbol is used when the function is of two or more variables
  - The $d$ symbol is for functions of one variable