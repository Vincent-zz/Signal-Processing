# Mathematical Model

## Signal Model

complex signal $s(t)$

$$
s(t) = s_0(t)e^{jwt}
$$

- complex envelope: $s_0(t)$
- carrier: $e^{jwt}$

assumptions

- **narrow-band**: $\frac{BW}{f_0} \ll 1$, envelope nearly unchanged at all antennas, $s_0(t) \approx s_0(t - \Delta t)$
- **far-field**: same incident angles at all antennas
- **ergodicity** (**stationary**): all signals we discuss bear ergodicity (stationary as well)
- **noise**
  - Gaussian-white noise $N(0, \sigma^2)$
  - irrelevant to each other: $R_{n_in_j} = 0 \times 0 = 0, i \neq j$
  - irrelevant to $s(t)$: $R_{n_is_j} = 0 \times m_s = 0, \forall i, j$

## Array Signal Model

assume signal at the *reference point*

$$
s(t) = s_0(t)e^{jwt}
$$

at $\vec{r}$

$$
s_r(t) = s(t - \frac{\vec{r}\cdot\hat{k}}{c})  = s_0(t - \frac{\vec{r}\cdot\hat{k}}{c})e^{j(wt - \vec{r}\cdot\vec{k})}\approx s(t)e^{-j\vec{r}\cdot\vec{k}}
$$

a *phase-change* is introduced

assume $N$ antennas, $S$ signal sources

$$
\begin{aligned}
\boldsymbol{X}(t) &= \boldsymbol{S_r}(t) + \boldsymbol{N}(t) = \begin{pmatrix}s_{r_1}(t)\\s_{r_2}(t)\\ \vdots\\ s_{r_N}(t)\end{pmatrix} + \begin{pmatrix}n_{1}(t)\\n_{2}(t)\\ \vdots\\ n_{N}(t)\end{pmatrix}\\
\boldsymbol{S}_r(t) &= \boldsymbol{A}(\boldsymbol{\theta}, \boldsymbol{\phi})\boldsymbol{S}(t) = \begin{pmatrix}
e^{-j \vec{r_1}\cdot\vec{k_1}} & e^{-j \vec{r_1}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_1}\cdot\vec{k_S}}\\
e^{-j \vec{r_2}\cdot\vec{k_1}} & e^{-j \vec{r_2}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_2}\cdot\vec{k_S}}\\
\vdots & \vdots &  & \vdots\\
e^{-j \vec{r_N}\cdot\vec{k_1}} & e^{-j \vec{r_N}\cdot\vec{k_2}} & \cdots & e^{-j \vec{r_N}\cdot\vec{k_S}}
\end{pmatrix}
\begin{pmatrix}s_{1}(t)\\s_{2}(t)\\ \vdots \\ s_{S}(t)\end{pmatrix}\\
&= \begin{pmatrix}\boldsymbol{a}(\theta_1, \phi_1) & \boldsymbol{a}(\theta_2, \phi_2) & \cdots & \boldsymbol{a}(\theta_S, \phi_S)\end{pmatrix}\boldsymbol{S}(t)
\end{aligned}
$$

- $\boldsymbol{a}(\theta, \phi)$: array manifold
- $\theta$: elevation angle
- $\phi$: azimuth angle

## Common Arrays

### 1. Uniform Linear Array

model

- signal sources and array in-plane ($\phi = 0$)
- set the $1^{\text{st}}$ antenna (*closest to signal source*) as reference

parameters

- number of antenna: $N$
- wave number: $k$
- antenna spacing: $D$

$$
\boldsymbol{a}(\theta) = \begin{pmatrix}1 & e^{-jkDsin\theta} & e^{-2jkDsin\theta} & \cdots & e^{-(N - 1)jkDsin\theta}\end{pmatrix}^{T}
$$

### 2. Uniform Circular Array

model

- array in plane $xOy$
- common spherical coordinate
- set $O$ as reference
- marked anticlockwisely, setting antenna at $x$ as the $1^{\text{st}}$ antenna

parameters

- number of antenna: $N$
- wave number: $k$
- radius: $R$

$$
\boldsymbol{a}(\theta, \phi) = \begin{pmatrix}e^{jkRsin\theta cos\phi} & e^{jkRsin\theta cos(\phi - \frac{2\pi}{N})} & e^{jkRsin\theta cos(\phi - 2\frac{2\pi}{N})} & \cdots & e^{jkRsin\theta cos(\phi - (N - 1)\frac{2\pi}{N})}\end{pmatrix}^{T}
$$

### 3. L-form Array

model

- array in plane $xOy$
- common spherical coordinate
- set the antenna at $O$ (*farthest to signal source*) as reference

parameters

- number of antenna: $N + M - 1$
  - $N$ on $Ox$
  - $M$ on $Oy$
- wave number: $k$
- antenna spacing: $D$

$$
\boldsymbol{a}_x(\theta, \phi) = \begin{pmatrix}1 & e^{jk(Dcos\phi)sin\theta} & e^{2jk(Dcos\phi)sin\theta} & \cdots & e^{(N - 1)jk(Dcos\phi)sin\theta}\end{pmatrix}^{T}\\
\boldsymbol{a}_y(\theta, \phi) = \begin{pmatrix}1 & e^{jk(Dsin\phi)sin\theta} & e^{2jk(Dsin\phi)sin\theta} & \cdots & e^{(M - 1)jk(Dsin\phi)sin\theta}\end{pmatrix}^{T}
$$
