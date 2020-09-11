# Derivative in Logistic Regression

Sigmoid function:

$\sigma(s) = \frac{1}{1+e^{-s}}$ with $s=\theta x$

Cost Function

$Cost(\sigma(s), y)=\left\{\begin{matrix}
-ln(\sigma(s)), y = 1\\
-ln(1-\sigma(s)),y=0
\end{matrix}\right.$

We have

$\frac{\partial \sigma}{\partial s}=\frac{e^{-s}}{(1+e^{-s})^2}=\frac{1}{1+e^{-s}}.\frac{e^{-s}+1-1}{(1+e^{-s})^2}=\sigma(s)(1-\sigma(s))$(1)

Compress cost function

> $Cost(\sigma(s),y)=-y.ln(\sigma(s))-(1-y)ln(1-\sigma(s))$

## $J(\theta)$ in Gradient Descent

> $J(\theta) = \frac{1}{m}\sum_{i=1}^{m}Cost(\sigma(x),y)$

This is `cross-entropy` use to measure the distance between 2 probability distributions.

## Derivative of $J(\theta)$

$\frac{\partial J(\theta;x,y)}{\partial\theta}=\frac{\partial J}{\partial\sigma}.\frac{\partial \sigma}{\partial \theta}$ (Chain Rule)

$=\left ( \frac{-y}{\sigma} + \frac{1-y}{1-\sigma} \right)\frac{\partial\sigma}{\partial\theta}=\frac{\sigma-y}{\sigma(1-\sigma)}\frac{\partial\sigma}{\partial\theta}$(2)

Apply chain rule and we had $\frac{\partial\sigma}{\partial s}$

$\frac{\partial\sigma}{\partial\theta}=\frac{\partial\sigma}{\partial s}\frac{\partial s}{\partial \theta}=\sigma(1-\sigma).x$

Summary:

$(2)=\frac{\sigma-y}{\sigma(1-\sigma)}\frac{\partial\sigma}{\partial\theta}=\frac{\sigma-y}{\sigma(1-\sigma)}\frac{\partial\sigma}{\partial s}\frac{\partial s}{\partial \theta}=(\sigma-y)x$

As you see, GD of logistic regression same GD of linear regression.
