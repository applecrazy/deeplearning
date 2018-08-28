# 1.9: Logistic Regression Gradient Descent

## Recap of Logistic Regression
- Pre Activation Function value:
$z=w^T x + b$

- Predicted value:
$\hat{y} = a = \sigma(z)$

- Loss function:
$\mathcal{L}(a, y) = - \big(y \log{a} + (1-y)\log{(1-a)}\big)$

## Logistic Regression Computation Graph
Assume $n_x = 2$, meaning $x \in \mathbb{R}^2$. Thus our computation graph is:

![](images/1-9-1.png)

- So to go backwards to optimize $\mathcal{L}$, we need to first compute $\frac{d\mathcal{L}}{da}$ (`da`)
  - Given the above loss function, $\frac{d\mathcal{L}}{da} = -\frac{y}{a} + \frac{1-y}{1-a}$
- Next, we need to compute $\frac{d\mathcal{L}}{dz} = \frac{d\mathcal{L}}{da} * \frac{da}{dz}$
  - Given that $\frac{da}{dz} = a(1-a)$, $\frac{d\mathcal{L}}{dz} = a-y$.
- Now, let's calculate the derivatives for the weights:
  - $\frac{d\mathcal{L}}{dw_1} = x_1 * \frac{d\mathcal{L}}{dz}$
  - $\frac{d\mathcal{L}}{dw_2} = x_2 * \frac{d\mathcal{L}}{dz}$
  - $\frac{d\mathcal{L}}{db} = \frac{d\mathcal{L}}{dz}$

- Based on this math, we update the weights and bias as such:

```
w1 = w1 - alpha * dw1
w2 = w2 - alpha * dw2
b  = b - alpha * db
```