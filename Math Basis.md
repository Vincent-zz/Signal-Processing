# Math Basis

## **Linear Algebra**

for $\boldsymbol{A} \in C^{n\times n}$

$$
\begin{aligned}
&\text{non-singular} \Leftrightarrow \text{full rank}\Leftrightarrow \text{invertible}\\
\Leftrightarrow &\boldsymbol{A}\boldsymbol{x} = \boldsymbol{O} \text{ with unique solution } \boldsymbol{x} = \boldsymbol{O}\\
\Leftrightarrow &\boldsymbol{A} = \begin{pmatrix} \boldsymbol{v}_1 & \boldsymbol{v}_2 & \cdots & \boldsymbol{v}_n \end{pmatrix}\text{ linearly independent}
\end{aligned}
$$

## 1. Matrix

- Hermitian

$$
\boldsymbol{A} \in C^{n\times n}\\
\boldsymbol{A} = \boldsymbol{A}^H
$$

- unitary

$$
\boldsymbol{A} \in C^{n\times n}\\
\boldsymbol{A}\boldsymbol{A}^H = \boldsymbol{A}^H\boldsymbol{A} = \boldsymbol{I}
$$

- Toeplitz

$$
\boldsymbol{A} \in C^{n\times n}\\
\boldsymbol{A} = \begin{pmatrix}
a_0 & a_{-1} & a_{-2} & \cdots & a_{-n+1}\\
a_1 & a_{0} & a_{-1} & \cdots & a_{-n+2}\\
a_2 & a_{1} & a_{0} & \cdots & a_{-n+3}\\
\vdots & \vdots & \vdots & & \vdots\\
a_{n-1} & a_{n-2} & a_{n-3} & \cdots & a_0
\end{pmatrix}\\

$$

## 2. Eigen-Value Decomposition

### Eigen-Value and Sub-Space

$$
\boldsymbol{A} \in C^{n\times n}\\
\boldsymbol{A}\boldsymbol{v} = \lambda \boldsymbol{v}, \boldsymbol{v} \neq \boldsymbol{O}
$$

- number of non-zero $\lambda$: $rank(\boldsymbol{A})$
- $\sum \lambda_i = tr(\boldsymbol{A})$
- $\prod \lambda_i = |\boldsymbol{A}|$

$$
|\boldsymbol{A}-\lambda \boldsymbol{I}| = 0 \Rightarrow (\lambda - \lambda_1)^{k_1}(\lambda - \lambda_2)^{k_2}\cdots(\lambda - \lambda_m)^{k_m} = 0
$$

for $\lambda_i$ and its *sub-space* $\boldsymbol{V}_i$ ($i = 1, 2, \cdots, m$)

$$
\begin{cases}
\boldsymbol{A}\boldsymbol{V}_i = \lambda_i \boldsymbol{V}_i\\
\boldsymbol{V}_i = \begin{pmatrix}\boldsymbol{v}^1_{i}&\boldsymbol{v}^2_{i}&\cdots&\boldsymbol{v}^{s_i}_{i}\end{pmatrix}
\end{cases}
$$

we have

- $\sum k = n$
- $1 \le s_i \le k_i$
- $\boldsymbol{v}_1 \in \boldsymbol{V}_1$, $\boldsymbol{v}_2 \in \boldsymbol{V}_2$, ..., $\boldsymbol{v}_m \in \boldsymbol{V}_m$ are linearly independent

### Decomposition

if $s_i = k_i$, $\boldsymbol{A}$ can be decomposed

$$
\boldsymbol{A} = \boldsymbol{V} \boldsymbol{\Lambda} \boldsymbol{V}^H = \boldsymbol{V}_a \boldsymbol{\Lambda}_a \boldsymbol{V}_a^H + \boldsymbol{V}_b \boldsymbol{\Lambda}_b \boldsymbol{V}_b^H = \sum_{i = 1}^{n} \boldsymbol{v_i} \lambda_i \boldsymbol{v_i}^H
$$

where

$$
\boldsymbol{\Lambda} = diag(\overbrace{\lambda_1, \cdots, \lambda_1}^{k_1},\overbrace{\lambda_2, \cdots, \lambda_2}^{k_2}, \cdots, \overbrace{\lambda_m, \cdots, \lambda_m}^{k_m})\\
\boldsymbol{V} = \begin{pmatrix}\boldsymbol{V}_1&\boldsymbol{V}_2&\cdots&\boldsymbol{V}_m\end{pmatrix} = \begin{pmatrix}\boldsymbol{v}_1&\boldsymbol{v}_2&\cdots&\boldsymbol{v}_n\end{pmatrix}
$$

\* *sufficient condition*: $\boldsymbol{A}$ is Hermitian $\Rightarrow$ $\boldsymbol{A}$ can be decomposed

## 3. Singular-Value Decomposition

### Singular-Value

$$
\boldsymbol{A} \in C^{m\times n}\\
(\boldsymbol{A}^H\boldsymbol{A})\boldsymbol{v} = \lambda \boldsymbol{v}, \boldsymbol{v} \neq \boldsymbol{O}\\
\sigma = \sqrt{\lambda}
$$

### Decomposition

$$
\boldsymbol{A} = \boldsymbol{U} \boldsymbol{\Sigma} \boldsymbol{V}^H
$$

where

$$
\boldsymbol{\Sigma} = \begin{pmatrix}\sigma_1 & 0 & \cdots & 0\\0 & \sigma_2 & \cdots & 0\\0 & 0 & \cdots & \sigma_n\\0 & 0 & \cdots & 0\\\vdots & \vdots & & \vdots\\0 & 0 & \cdots & 0\end{pmatrix}\in C^{m\times n}\\
\text{unitary matrix: }\boldsymbol{U}\in C^{m\times m}, \boldsymbol{V}\in C^{n\times n}
$$

## **Random Process**

## 1. Random Signal

$x(t)$, fully written as $x(\boldsymbol{\alpha}, t)$

$\boldsymbol{\alpha}$ is the information that we want to transmit, deciding the exact form of this signal

- $x(\boldsymbol{\alpha}, t_0)$: a random variable at $t_0$
- $x(\boldsymbol{\alpha}_0, t)$: fixed signal, function of time

## 2. Coherence

$x_i(t)$ and $x_j(t)$ are coherent

$$
x_i(t) = Cx_j(t)
$$

$C$ is a complex constant

## 3. Correlation

- mutual-correlation $R_{xy}(t, t + \tau) = E\{x(t)y^*(t + \tau)\}$
  - if irrelevant, $R_{xy}(t, t + \tau) = m_xm_y$
- instantaneous self-correlation power $x(t)x^*(t + \tau)$
  - $\tau = 0 \Rightarrow$ instantaneous power $x(t)x^*(t)$

**Correlation Matrix** $\boldsymbol{R}$, the statistical-average correlation power

$$
\boldsymbol{X} = \begin{pmatrix}x_1(t) & \cdots & x_N(t)\end{pmatrix}^T
$$

$$
\boldsymbol{R}_X = \boldsymbol{R}_X(t, t + \tau)|_{\tau = 0} = E\{\boldsymbol{X}(t)\boldsymbol{X}^H(t)\}= \begin{pmatrix}
E\{x_i(t)x^*_j(t)\}
\end{pmatrix}_{N \times N}
$$

**properties** of $\boldsymbol{R}$

- Hermitian: $\boldsymbol{R}_X = \boldsymbol{R}^H_X$
- full-rank $\Leftrightarrow$ $\forall i \neq j$, $x_i(t)$ and $x_j(t)$ is incoherent

## 4. Average

- time-average

$$
\begin{aligned}
x_{\text{DC}} &= \overline{x(t)}\\
\overline{P}(\tau) &= \overline{x(t)x^*(t + \tau)}
\end{aligned}
$$

- statistical-average

$$
\begin{aligned}
m_x(t) &= E\{x(t)\}\\
R_x(t, t + \tau) &= E\{x(t)x^*(t + \tau)\}
\end{aligned}
$$

**Ergodicity**: time-average $=$ statistical-average

$$
\begin{aligned}
\overline{x(t)} &= E\{x(t)\}\\
\overline{x(t)x^*(t + \tau)} &= E\{x(t)x^*(t + \tau)\}
\end{aligned}
$$

**Stationary**: statistical-average is irrelevant to time

$$
\begin{aligned}
m_x(t) &= m_x\\
R_x(t, t + \tau) &= R_x(\tau)
\end{aligned}
$$

\* ergodicity $\Rightarrow$ stationary
