# 1.10: Gradient Descent on $m$ Examples

- Remember that
$$J(w,b) = \frac{1}{m} \sum_{i=1}^{m}{\mathcal{L}(a^{(i)}, y^{(i)})}$$
$$a^{(i)} = \hat{y}^{(i)} = \sigma(z^{(i)}) = \sigma(w^T x^{(i)} + b)$$


- The derivative of the cost function with respect to $w_1$ would look like this:
$$ \frac{\partial}{\partial w_1}J(w,b) = \frac{1}{m}\sum_{i=1}^{m}{\frac{\partial}{\partial w_1} \mathcal{L}(a^{(i)}, y^{(i)})}$$


## Logistic Regression Algorithm for $m$ Examples, Two Features
- One GD step:
1. Initialize $J = 0$, $dw_1 = 0$, $dw_2 = 0$, $db = 0$`
2. For $i=1$ to $m$:
  - $z^{(i)} = w^T x^{(i)} + b$
  - $a^{(i)} = \sigma(z^{(i)})$
  - $J += -\big[ y^{(i)}\log{a^{(i)}} - (1-y^{(i)}) \log{(1-a^{(i)})} \big]$
  - $dz^{(i)} = a^{(i)} - y^{(i)}$
  - $dw_1 \text{ += } x_1^{(i)} * dz^{(i)}$
  - $dw_2 \text{ += } x_2^{(i)} * dz^{(i)}$
  - $db \text{ += } dz^{(i)}$
3. $J \text{ /= } m$
4. $dw_1 \text{ /= } m$
5. $dw_2 \text{ /= } m$
6. $db \text{ /= } m$

- But this implementation is not as good, because it has two for loops, one over the examples and another over the features
  - Makes it slower