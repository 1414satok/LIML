# LIML
以下の同時方程式を考える。
```math
  \begin{cases}
    y_1 = \alpha_1 + \gamma_1 y_2 + \delta_1 x_1 + \epsilon_1 \\
    y_2 = \alpha_2 + \gamma_2 y_1 + \delta_2 x_2 + \epsilon_2
  \end{cases}
```

この式を$y_1, y_2$について解くと、
```math
  \begin{cases}
    y_1 = \frac{1}{1 - \gamma_1 \gamma_2} (\alpha_1 + \gamma_1 \alpha_2 + \delta_1 x_1 + \gamma_1 \delta_2 x_2 + \epsilon_1 + \gamma_1 \epsilon_2) \\
    y_2 = \frac{1}{1 - \gamma_1 \gamma_2} (\alpha_2 + \gamma_2 \alpha_1 + \gamma_2 \delta_1 x_1 + \delta_2 x_2 + \epsilon_2 + \gamma_2 \epsilon_1)
  \end{cases}
```
となる。さらに、行列を用いて表すと、
```math
  \vec{y}=\begin{pmatrix}
    \lambda\\
    \Gamma
  \end{pmatrix}X + e
```
where
```math
\begin{eqnarray*}
  \vec{y}&=&\begin{pmatrix}
    y_1\\
    y_2
  \end{pmatrix}\\
  \lambda&=&\begin{pmatrix}
    \frac{\alpha_1+\gamma_1 \alpha_2}{1-\gamma_1 \gamma_2}&
    \frac{\delta_1}{1-\gamma_1 \gamma_2} &
    \frac{\gamma_1 \delta_2}{1-\gamma_1 \gamma_2}
  \end{pmatrix}\\
  \Gamma&=&\begin{pmatrix}
    \frac{\alpha_2+\gamma_2 \alpha_1}{1-\gamma_1 \gamma_2}&
    \frac{\gamma_2 \delta_1}{1-\gamma_1 \gamma_2} &
    \frac{\delta_2}{1-\gamma_1 \gamma_2}
  \end{pmatrix}\\
  X&=&\begin{pmatrix}
    1&x_1&x_2
  \end{pmatrix}^{\prime}\\
  e&=&\begin{pmatrix}
    e_1\\
    e_2
  \end{pmatrix}= \begin{pmatrix}
    \epsilon_1 + \gamma_1 \epsilon_2\\
    \epsilon_2 + \gamma_2 \epsilon_1
  \end{pmatrix}
\end{eqnarray*}
```
これをさらに
```math
  \vec{y}=\Pi_0^{\prime}+\Pi_1^{\prime}x_1+\Pi_2^{\prime}x_2+e
```
where
```math
\begin{eqnarray*}
  \Pi_0&=&\begin{pmatrix}
    \frac{\alpha_1+\gamma_1 \alpha_2}{1-\gamma_1 \gamma_2}&
    \frac{\alpha_2+\gamma_2 \alpha_1}{1-\gamma_1 \gamma_2}
  \end{pmatrix}\\
  \Pi_1&=&\begin{pmatrix}
    \frac{\delta_1}{1-\gamma_1 \gamma_2}&
    \frac{\gamma_2 \delta_1}{1-\gamma_1 \gamma_2}
  \end{pmatrix}\\
  \Pi_2&=&\begin{pmatrix}
    \frac{\gamma_1 \delta_2}{1-\gamma_1 \gamma_2}&
    \frac{\delta_2}{1-\gamma_1 \gamma_2}
  \end{pmatrix}
\end{eqnarray*}
```
と書き直す。このとき、$\Pi_2$に対して
```math
  \Pi_2\gamma=0\qquad\text{where}\quad\gamma=\begin{pmatrix}
    1\\
    -\gamma_1
  \end{pmatrix}
```
が成り立つ。