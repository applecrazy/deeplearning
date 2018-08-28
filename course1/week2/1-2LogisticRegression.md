# 1.2: Logistic Regression

- Used when the output labels are 0 or 1

## Logistic Regression Overview
- Given $x \in \mathbb{R}^{n_x}$, want prediction $\hat{y}$, which is $P(y=1|x)$
- Parameters: $w \in \mathbb{R}^{n_x}$, $b \in \mathbb{R}$
- Output: $\hat{y} = \sigma(w^T x + b)$
  - Sigmoid function: $\sigma(z) = \frac{1}{1 + e^{-z}}$
    - If $z$ large, $\sigma \approx 1$
    - If $z$ large negative, $\sigma \approx 0$ 