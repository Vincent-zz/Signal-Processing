# Basis of Fourier Theory

The whole picture:

- FS
  - DTFS
  - CTFS
- FT
  - DTFT --> Z
  - CTFT --> L
- DFT <-- DTFT

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

- **CT to DT**--Sampling:

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

- **FS to FT**:

$$
X(w) = 2\pi \sum_{-\infty}^{+\infty}X_k \delta(w-kw_0)
$$

- **DTFT to DFT**



- **CTFT to L**



- **DTFT to Z**


