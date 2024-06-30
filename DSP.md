# Digital Signal Processing

## **Part I: DSP System (Stable, LTI)**

$$
x(t) \rightarrow [\text{C/D} \rightarrow H(z) \rightarrow \text{D/C}] \rightarrow y(t)
$$

**Effective system function $H_{eff}(s)$**:

$$
x(t) \rightarrow [ \quad \quad \quad H_{eff}(s) \quad \quad \quad ] \rightarrow y(t)
$$

**Effective frequency response**:

$$
H_{eff}(s = jw) = \text{fundamental period of }H(z = e^{jw})\text{, scaling}(2\pi\text{ to }w_s)
$$

## 1. C/D

$$
\text{No-Aliasing} \Leftrightarrow \text{Ideal-Reconstruction} 
$$

**Sampling**：

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
\- |$\text{Vertical: }\frac{1}{T_s}\\\text{Horizonal: Extending to }kw_s$|$\text{Horizonal: Scaling }kw_s \text{ to } k2\pi$
</div>

**Sub-Sampling**:

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

$x[n]$ |$x[n] \rightarrow \downarrow M \rightarrow x_d[n]$|$x[n] \rightarrow \uparrow L \rightarrow x_e[n]$
:---:|:---:|:---:
$x[n]$|$x_d[n] = x[Mn]$|$x_e[n] = \begin{cases}x[\frac{n}{L}]&, n = kL\\0&,\text{otherwise}\end{cases}$
$X(e^{jw})$|$\text{Vertical: }\frac{1}{M}\\\text{Horizonal: Stretching } M \text{ around }2k\pi$|$\text{Horizonal: Compressing } L$
</div>

## 2. Implementations of $H(s)$

(1) **Difference-Equation**

Firstly, we have the traditional way of system implementation: *Difference-Equation*

$$
\sum_N y[n - i]= \sum_M x[n - j] \Leftrightarrow H(z) = \frac{Y(z)}{X(z)} = \frac{\sum_M z^{-j}}{\sum_N z^{-i}}\\
$$

It's easy to implement the procedure of *difference* by digital chips

(2) **Convolution**

For a *finite signal sequence*

$$
x[n], 0 \le n \le N - 1
$$

It's easy to implement its *Convolution* with finite $h[n], 0 \le n \le N - 1$ by digital chips

## 3. DSP Systems

(1) **All-Pass System**

$$
H(z) = \prod \frac{z^{-1} - z_0}{1-z^*_0z^{-1}}
$$

implemented by difference-equation

(2) **Linear-Phase System**

$$
\theta(w) = -\alpha w + \beta
$$

*Causual, linear-phase, finite* LTI digital system:

$$
h[n], 0 \le n \le M\\
$$

about system function $H(z)$:

$$
H(z) = \begin{cases}
z^{-M}H(z^{-1}), \text{for: I II}\\
-z^{-M}H(z^{-1}), \text{for: III IV}
\end{cases}
$$

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

Type|Symmetry|$\alpha = \frac{M}{2}$|$\beta$|System Function
:---:|:---:|:---:|:---:|:---:
I|$h[n] = h[M - n]$|$M\text{ is even}$|$0$|$z^{-M}H(z^{-1})$
II|$h[n] = h[M - n]$|$M\text{ is odd}$|$0$|$z^{-M}H(z^{-1})$
III|$h[n] = -h[M - n]$|$M\text{ is even}$|$\frac{\pi}{2}$|$-z^{-M}H(z^{-1})$
IV|$h[n] = -h[M - n]$|$M\text{ is odd}$|$\frac{\pi}{2}$|$-z^{-M}H(z^{-1})$

</div>

(3) **Min-Phase System**

All zeros and poles of casual, stable $H(z)$ are within unit-circle

## **Part II: Frequency Analyze of Digital Signal**

Digital chips can only process *discrete sequences*

If we want to do some analyzes in frequency domain digitally, we need sampling as well in frequency domain

## 1. DFT

For a *finite signal sequence*

$$
x[n], 0 \le n \le N - 1
$$

How to derive DFT

- **Defination**: Frequency Sampling

$$
  X[k] = X(e^{jw})\Large{|}_{w = \frac{2\pi}{N}k}
$$

- **DTFS of Extension**

$$
\tilde{x}[n] = x[n]R_N\\
X[k] = \tilde{X}_k
$$

Properties of DFT $\Leftarrow$ Properties of DTFS

## 2. Short-Time FT

For an infinite input signal $x[n]$, we can only derive DFT for *a finite part* of it by digital chips to estimate its frequency spectrum

$$
v[n] = x[n]w[n]
$$

Window function: $w[n], 0 \le n \le N - 1$

There are many types of window function: Rectangle, Hanning, Hamming, Blackman, etc

## 3. DFT Algorithm: FFT


