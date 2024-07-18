# Sub-Space Theory

$N$ antennas, $S$ signal sources ($N \ge S$)

$$
\begin{aligned}
\boldsymbol{X}(t) &= \boldsymbol{S_r}(t) + \boldsymbol{N}(t) = \begin{pmatrix}s_{r_1}(t)\\s_{r_2}(t)\\ \vdots\\ s_{r_N}(t)\end{pmatrix} + \begin{pmatrix}n_{1}(t)\\n_{2}(t)\\ \vdots\\ n_{N}(t)\end{pmatrix}\\
\boldsymbol{S}_r(t) &= \boldsymbol{A}(\boldsymbol{\theta}, \boldsymbol{\phi})\boldsymbol{S}(t) = \boldsymbol{A}(\boldsymbol{\theta}, \boldsymbol{\phi}) \begin{pmatrix}s_{1}(t)\\s_{2}(t)\\ \vdots \\ s_{S}(t)\end{pmatrix}
\end{aligned}
$$

## Correlation Matrix

$$
\boldsymbol{R}_X = E\{\boldsymbol{X}(t)\boldsymbol{X}^H(t)\}= \begin{pmatrix}
R_{ij}
\end{pmatrix}_{N \times N}
$$

as for $R_{ij}$

$$
\begin{aligned}
R_{ij} &= E\{x_i(t)x^*_j(t)\}= E\{[s_{r_i}(t) + n_i(t)][s_{r_j}(t) + n_j(t)]^*\}\\
&= E\{s_{r_i}(t)s^*_{r_j}(t)\} + \begin{cases}\sigma^2, i = j\\0, i \neq j\end{cases}
\end{aligned}
$$

finally we have

$$
\begin{aligned}
\boldsymbol{R}_X &= \bold{A}\boldsymbol{R}_S\boldsymbol{A}^H + \sigma^2\boldsymbol{I}
\end{aligned}
$$

- $\boldsymbol{R}_X$, $\boldsymbol{R}_S$ are Hermitian
- $\boldsymbol{R}_X$ is full-rank
- $\boldsymbol{R}_S$ is full-rank if no coherence occurs in $\boldsymbol{X}$

## EVD of Correlation Matrix

As a Hermitian matrix, $\boldsymbol{R}_X$ can be EVDecomposed

It can be proven that

$$
\lambda_1 \ge \lambda_2 \ge \cdots \ge \lambda_S > \lambda_{S + 1} = \cdots = \lambda_{N} = \sigma^2
$$

(this can be used to estimate the number of sources $S$)

then $\boldsymbol{R}_X$ can be decomposed as

$$
\boldsymbol{R}_X = \boldsymbol{V}_s \boldsymbol{\Lambda}_s \boldsymbol{V}_s^H + \boldsymbol{V}_n \boldsymbol{\Lambda}_n \boldsymbol{V}_n^H
$$

$$
\begin{cases}
\boldsymbol{\Lambda}_s = diag(\lambda_1, \lambda_2, \cdots, \lambda_S)\\
\boldsymbol{\Lambda}_n = diag(\lambda_{S+1}, \lambda_{S+2}, \cdots, \lambda_N) = \sigma^2 \boldsymbol{I}
\end{cases}
$$

- $\boldsymbol{V}_s$ is the **signal sub-space**
- $\boldsymbol{V}_n$ is the **noise sub-space**

## Properties of Sub-Space

- $\boldsymbol{V}_s$ and $\boldsymbol{A}$ represent the same sub-space
- $\boldsymbol{V}_s$ and $\boldsymbol{V}_n$ are orthogonal
