# Physical Model

## Signal Model

- **narrow-band**: $\frac{BW}{f_0} \ll 1 \Leftrightarrow s_0(t)$ change slowly
- **far-field**: same incident angles for all antennas

assume signal at the *reference point*

$$
s(t) = s_0(t)e^{jwt} = [a(t)e^{j\phi(t)}]e^{jwt}
$$

at $\vec{r}$

$$
s_r(t) = s(t - \frac{\vec{r}\cdot\hat{k}}{c})  = s_0(t - \frac{\vec{r}\cdot\hat{k}}{c})e^{j(wt - \vec{r}\cdot\vec{k})}\approx s(t)e^{-j\vec{r}\cdot\vec{k}}
$$

assume $N$ antennas, $S$ signal sources

$$
\boldsymbol{S_r}(t) = \begin{pmatrix}s_{r_1}(t)\\s_{r_2}(t)\\ \vdots\\ s_{r_N}(t)\end{pmatrix} + \begin{pmatrix}n_{1}(t)\\n_{2}(t)\\ \vdots\\ n_{N}(t)\end{pmatrix}
= \begin{pmatrix}
e^{-j \vec{r_1}\cdot\vec{k_1}} & e^{-j \vec{r_1}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_1}\cdot\vec{k_S}}\\
e^{-j \vec{r_2}\cdot\vec{k_1}} & e^{-j \vec{r_2}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_2}\cdot\vec{k_S}}\\
\vdots & \vdots &  & \vdots\\
e^{-j \vec{r_N}\cdot\vec{k_1}} & e^{-j \vec{r_N}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_N}\cdot\vec{k_S}}
\end{pmatrix}
\begin{pmatrix}s_{1}(t)\\s_{2}(t)\\ \vdots \\ s_{S}(t)\end{pmatrix} + \boldsymbol{N}\\
=\begin{pmatrix}\boldsymbol{a}(\theta_1, \phi_1) & \boldsymbol{a}(\theta_2, \phi_2) & \cdots & \boldsymbol{a}(\theta_S, \phi_S)\end{pmatrix}
\begin{pmatrix}s_{1}(t)\\s_{2}(t)\\ \vdots \\ s_{S}(t)\end{pmatrix} + \boldsymbol{N} = \boldsymbol{A}(\boldsymbol{\theta}, \boldsymbol{\phi})\boldsymbol{S}(t) + \boldsymbol{N}
$$

- $\boldsymbol{a}(\theta, \phi)$ is called *array manifold*
- $n_i(t)$: *independent-steady-Gaussian-white* noise $N(0, \sigma^2)$
- $\theta$ is the *elevation angle*; $\phi$ is the *azimuth angle*

## Common Arraysl

### 1. Uniform Linear Array

- signal sources and array *in-plane*
- set the $1^{\text{st}}$ antenna as reference
- wave number: $k$
- antenna spacing: $d$

$$
\boldsymbol{a}(\theta) = \begin{pmatrix}1 & e^{-jkdsin\theta} & e^{-2jkdsin\theta} & \cdots & e^{-(N - 1)jkdsin\theta}\end{pmatrix}^{T}
$$

### 2. Uniform Circular Array

$$
\boldsymbol{a}(\theta, \phi) = \begin{pmatrix}1 & e^{-jkdsin\theta} & e^{-2jkdsin\theta} & \cdots & e^{-(N - 1)jkdsin\theta}\end{pmatrix}^{T}
$$
