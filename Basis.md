# Basis of Fourier Theory

## 1. Fourier-Series/Transform

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

- **FS to FT**

$$
X(w) = 2\pi \sum_{-\infty}^{+\infty}X_k \delta(w-kw_0)
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

ROC of L/Z Transform:

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

$\quad$|Left-sided|Right-sided|Double-sided(infinite)|Finite|Rational
:---:|:---:|:---:|:---:|:---:|:---:
L-$\text{Re}\{s\}$|$(-\infty, \sigma_H)$|$(\sigma_L, +\infty)$|$(\sigma_L, \sigma_H)$|$(-\infty, +\infty)$|bounded by poles
Z-$\|z\|$|$(0, r_H)$|$(r_L, +\infty)$|$(r_L, r_H)$|$(0, +\infty)$|bounded by poles

</div>

\* rational transform: ($m$ zeros, $n$ poles)

$$
H(s/z) = \frac{\prod_M ((s/z) - z_k)}{\prod_N ((s/z) - p_k)}
$$

\* whether boundries like $0, \infty$ are included in ROC depends on specific $h[n]$
