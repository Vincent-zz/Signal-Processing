# System

## 1. Basic Properties

$$
x \rightarrow y
$$

- **Memoryless**: $y(t_0/n_0)$ depends only on  $x(t_0/n_0)$
- **Invertible**: $x \rightarrow y$ one-to-one mapping
- **Causality**: $y(t_0/n_0)$ depends only on $x(t/n), t/n \le t_0/n_0$
- **Stability**: $x$ is bounded $\Rightarrow$ $y$ is bounded
- **Time-Invariance**: $x(t-t_0/n-n_0) \rightarrow y(t-t_0/n-n_0)$
- **Linearity**: $ax_1 + bx_2 \rightarrow ay_1 + by_2$

## 2. LTI System

**LTI** (*Linear and Time-Invariant*) **System** can be expressed by:

$$
\begin{aligned}
y &= x \ast h\\
Y(s/z) &= X(s/z)H(s/z)
\end{aligned}
$$

Properties of LTI System:

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

Memoryless|Invertible|Causality|Stability
:---:|:---:|:---:|:---:
$h = K\delta$|$h \ast h_I = \delta$|$h = 0, t/n < 0$|$\sum_{\infty}/\int_{\infty} \|h\| < \infty$
$\quad$|$\quad$|$\text{Re}\{s\} = (\sigma, +\infty]\\\|z\| = (r, +\infty]$|$\sigma = 0 \in \text{ROC}_L\\r = 1\in \text{ROC}_Z$

</div>

## 3. Physical Implementation of LTI System

Using differential/difference-equations

$$
\begin{aligned}
\sum_N \frac{d^i y}{dt^i} = \sum_M \frac{d^j x}{dt^j} &\Leftrightarrow H(s) = \frac{Y(s)}{X(s)} = \frac{\sum_M s^j}{\sum_N s^i}\\
\sum_N y[n - i]= \sum_M x[n - j] &\Leftrightarrow H(z) = \frac{Y(z)}{X(z)} = \frac{\sum_M z^{-j}}{\sum_N z^{-i}}\\
\end{aligned}
$$

System function of LTI system that can be expressed by differential/difference-equations are all *rational*

**So, usually we only talk about rational system** 

## 4. Frequency Response of (Stable) LTI System

Using Fourier-Transform

$$
s/z = jw/e^{jw} \Rightarrow H(w)
$$

We have

$$
\begin{cases}
\text{Gain: }&G(w) = |H(w)|\\
\text{Phase Shift: }&\theta(w) = \angle H(w)\\
\text{Group Delay: }&\text{grd}(w) = -\frac{d}{dw}\angle H(w)
\end{cases}
$$

## 5. Common LTI Systems

(1) **All-Pass System**
  
$$
G(w) = \text{Const}
$$

(2) **Linear-Phase System**(Time-Shift/Delay System)

Linear phase-shift does not influence the shape of signal

$$
\theta(w) = -\alpha w + \beta\\
\text{grd}(w) = \alpha = t_0/n_0
$$

$$
\begin{aligned}
\Rightarrow y(t/n) &= \frac{1}{2\pi}\sum_{\infty} X(w)G(w)e^{-jw (\text{grd}(w))}e^{jw(t/n)}\\
&= x(t - t_0/n - n_0)
\end{aligned}
$$

(3) **Min-Phase System**

*Casual, stable* LTI system $H$ with *casual, stable* *inverse* (or *compensate*) system $H_I$

All zeros and poles must satisfy

$$
\begin{aligned}
\text{L: }&\text{Re}\{z_k/p_k\} < 0\\
\text{Z: }&|z_k/p_k| < 1
\end{aligned}
$$

any system $H = H_{all-pass}H_{min-phase}$