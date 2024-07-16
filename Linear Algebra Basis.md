# Linear Algebra

for $A \in C^{n\times n}$

$$
\begin{aligned}
&\text{non-singular} \Leftrightarrow \text{full rank}\Leftrightarrow \text{invertible}\\
\Leftrightarrow &Ax = 0 \text{ with unique solution } x = O\\
\Leftrightarrow &A = \begin{pmatrix} v_1 & v_2 & \cdots & v_n \end{pmatrix}\text{ linearly independent}
\end{aligned}
$$

## Matrix

- Hermitian

$$
A \in C^{n\times n}\\
A = A^H
$$

- unitary

$$
A \in C^{n\times n}\\
AA^H = A^HA = I
$$

- Toeplitz

$$
A \in C^{n\times n}\\
A = \begin{pmatrix}
a_0 & a_{-1} & a_{-2} & \cdots & a_{-n+1}\\
a_1 & a_{0} & a_{-1} & \cdots & a_{-n+2}\\
a_2 & a_{1} & a_{0} & \cdots & a_{-n+3}\\
\vdots & \vdots & \vdots & & \vdots\\
a_{n-1} & a_{n-2} & a_{n-3} & \cdots & a_0
\end{pmatrix}\\

$$

## Eigen-Value Decomposition

### Eigen-Value and Sub-Space

$$
A \in C^{n\times n}\\
Av = \lambda v, v \neq O
$$

- number of non-zero $\lambda$: $rank(A)$
- $\sum \lambda_i = tr(A)$
- $\prod \lambda_i = |A|$

for $A \in C^{n\times n}$, assume that

$$
|A-\lambda I| = 0 \Rightarrow (\lambda - \lambda_1)^{k_1}(\lambda - \lambda_2)^{k_2}\cdots(\lambda - \lambda_m)^{k_m} = 0
$$

for $\lambda_i$ and its *sub-space* $V_i$ ($i = 1, 2, \cdots, m$)

$$
\begin{cases}
AV_i = \lambda_i V_i\\
V_i = \begin{pmatrix}v^1_{i}&v^2_{i}&\cdots&v^{s_i}_{i}\end{pmatrix}
\end{cases}
$$

we have

- $\sum k = n$
- $1 \le s_i \le k_i$
- $v_1 \in V_1$, $v_2 \in V_2$, ..., $v_m \in V_m$ are linearly independent

### Decomposition

if $s_i = k_i$, $A$ can be decomposed

$$
A = V\Lambda V^H
$$

where

$$
\Lambda = diag(\overbrace{\lambda_1, \cdots, \lambda_1}^{k_1},\overbrace{\lambda_2, \cdots, \lambda_2}^{k_2}, \cdots, \overbrace{\lambda_m, \cdots, \lambda_m}^{k_m})\\
V = \begin{pmatrix}V_1&V_2&\cdots&V_m\end{pmatrix}
$$

\* *sufficient condition*: $A$ is Hermitian $\Rightarrow$ $A$ can be decomposed

## Singular-Value Decomposition

### Singular-Value

$$
A \in C^{m\times n}\\
(A^HA)v = \lambda v, v \neq O\\
\sigma = \sqrt{\lambda}
$$

### Decomposition

$$
A = U\Sigma V^H
$$

where

$$
\Sigma = \begin{pmatrix}\sigma_1 & 0 & \cdots & 0\\0 & \sigma_2 & \cdots & 0\\0 & 0 & \cdots & \sigma_n\\0 & 0 & \cdots & 0\\\vdots & \vdots & & \vdots\\0 & 0 & \cdots & 0\end{pmatrix}\in C^{m\times n}\\
\text{unitary matrix: }U\in C^{m\times m}, V\in C^{n\times n}
$$
