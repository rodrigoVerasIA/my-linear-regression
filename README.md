### What is linear regression ?

$$ y = ax + b $$

* <var>x</var>: input features
* <var>w</var>: weight (slope)
* <var>b</var>: bias (intercept)
* <var>y</var>: predicted

for example:

$$ y = x² + 1 $$

dataset example:

| x | y |
|---|---|
| 1 | 2 |
| 2 | 5 |
| 3 | 10|

$$
Y = \begin{bmatrix}
y_1 \\
y_2 \\
y_3 \\
\vdots \\
y_n
\end{bmatrix}
$$

$$
\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
\vdots \\
x_n
\end{bmatrix}
\cdot
\begin{bmatrix}
w_1
\end{bmatrix} + b
= \begin{bmatrix}
x_1w_1 + b \\
x_2w_1 + b \\
x_3w_1 + b \\
\vdots \\
x_nw_1 + b \\
\end{bmatrix}
= Ŷ
$$

that is

$$
Ŷ = \begin{bmatrix}
ŷ_1 \\
ŷ_2 \\
ŷ_3 \\
\vdots \\
ŷ_n
\end{bmatrix}
$$

$$
errors = Ŷ - Y
$$

# Descent gradients

* $$ Y = WX^T + b $$
* $$ MSE = \frac{errors²}{n} $$
* $$ errors = Ŷ - (WX^T + b) $$

$$ \frac{\delta MSE}{\delta W} = \frac{\delta MSE}{\delta errors} \cdot \frac{\delta errors}{\delta W} $$

$$ \frac{\delta MSE}{\delta W} = \frac{-2X^Terrors}{n} $$
$$ \implies $$
$$ \frac{\delta MSE}{\delta W} = \frac{X^Terrors}{n}$$

$$ \frac{\delta MSE}{\delta b} = \frac{\delta MSE}{\delta errors} \cdot \frac{\delta errors}{\delta b} $$

$$  \frac{\delta MSE}{\delta b} = \frac{-2errors}{n} $$
$$ \implies $$
$$ \frac{\delta MSE}{\delta b} = \frac{errors}{n} $$

## update weights and bias

$$ new_W = old_W - \alpha\cdot \frac{\delta MSE}{\delta W} $$

$$ new_b = old_b - \alpha\cdot \frac{\delta MSE}{\delta b} $$