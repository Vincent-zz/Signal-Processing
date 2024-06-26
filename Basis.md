# Basis of Fourier Theory

## 1. Fourier-Series and Transform

From the perspective of *Linear Space*:

- $x(t)$: Vector, the siganl
- $\alpha_w(t)$: Basis, namely $e^{jwt}$
- $X(w)$: Coordinate, the freq-spectrum

We have the relationships below:

$$
\begin{cases}
X(w) = <x(t), \alpha_w(t)>&,\ Inner\ Product\\
x(t) = sum(X(w)\alpha_w(t))&,\ Summation\\
\end{cases}
$$

Also, we have **Parseval's Theorem**:

$$
<x(t), x(t)> = sum(X(w)X^*(w))
$$

For **periodic**/**non-periodic** signals, namely **F-Series**/**F-Transform**:

<style>
.center 
{
  width: auto;
  display: table;
  margin-left: auto;
  margin-right: auto;
}
</style>
<div class="center">

Fourier- |Series|Transform
:---:|:---:|:---:
$<x, \alpha>$|$\frac{1}{T} \int x\alpha^*$ / $\frac{1}{N} \sum x\alpha^*$|$\int x\alpha^*$ / $\sum x\alpha^*$
$sum()$|$\int$ / $\sum$|$\frac{1}{2\pi}\int$

</div>

\* Actually, only FS fully matches the theory of *Linear Space*. FT is like a less rigorous *pseudo*-version. (simply for easier memorizing)

\* If we want to get FT unified as FS, we need to consider $\frac{1}{\sqrt{2\pi}}e^{jwt}$ as basis in FT.

## 2. Connections

- **CT to DT**--*sampling*

<style>
.center 
{
  width: auto;
  display: table;
  margin-left: auto;
  margin-right: auto;
}
</style>
<div class="center">

$x(t)$ |$x_c(t) = x(t)\sum_{-\infty}^{+\infty}\delta(t-kT_s)$|$x[n] = x(nT_s)$
:---:|:---:|:---:
$X(jw)$|$X_c(jw) = \frac{1}{T_s}X(jw)R_{w_s}$|$X(e^{jw}) = X_c(jw\times \frac{w_s}{2\pi})$
\- |Periodical-Extension($w_s$)|Scaling($w_s$ to $2\pi$)
</div>

- **FS to FT**

$$
X(w) = 2\pi \sum_{-\infty}^{+\infty}X_k \delta(w-kw_0)
$$

- **DTFT to DFT**--*sampling in frequency domain*

$$
x[n], 0 \le n \le N - 1\\
X[k] = X(e^{jw})\large{|}_{w = \frac{2\pi}{N}k}
$$

- **DTFS to DFT**

$$
x[n], 0 \le n \le N - 1\\
\tilde{x}[n] = x[n]R_N\\
X[k] = \tilde{X}_k
$$

- **CTFT to L**

$$
\text{basis: }e^{jwt} \rightarrow e^{st}\\
s = \sigma + jw\\
X(s) = \mathcal{L}\{x(t)\} = \int x(t)e^{-st}dt = \mathcal{F}\{x(t)e^{-\sigma t}\}
$$

- **DTFT to Z**

$$
\text{basis: }e^{jwn} \rightarrow z^n\\
z = re^{jw}\\
X(z) = \mathcal{Z}\{x[n]\} = \sum x[n]z^{-n} = \mathcal{F}\{x[n]r^{-n}\}
$$

\* Summary: The whole picture

$$
\begin{cases}
  \text{FS}
  \begin{cases}
    \text{DTFS}\\
    \text{CTFS}
  \end{cases}\\
  \text{FT}
  \begin{cases}
    \text{DFFT} \Rightarrow \text{Z}\\
    \text{CTFT} \Rightarrow \text{L}
  \end{cases}\\
  \text{DFT} \Leftarrow \text{DTFT}
\end{cases}
$$

## 3. Convergence

(not rigorous at all)

<style>
.center 
{
  width: auto;
  display: table;
  margin-left: auto;
  margin-right: auto;
}
</style>
<div class="center">

Transform|Condition for Convergence|ROC
:---:|:---:|:---:
FS|$\int_T/\sum_N \|x\| < \infty$|$1\in \text{ROC}_Z$
FT|$\int_\infty/\sum_\infty \|x\| < \infty$|$0\in \text{ROC}_L$
Z|$\mathcal{F}\{x[n]r^{-n}\}$ Converge|$\text{ROC}_Z(\|z\|)$
L|$\mathcal{F}\{x(t)e^{-\sigma t}\}$ Converge|$\text{ROC}_L(\text{Re}\{s\})$

</div>
