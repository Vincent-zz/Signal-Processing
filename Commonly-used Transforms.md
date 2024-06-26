# Commonly-used Transforms

## Periodical Signals

- Sampling $\delta$ Function:

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

$x$|FS
:---:|:---:
$x[n] = \sum_{-\infty}^{+\infty} \delta[n - kN]$|$X_k = \frac{1}{N}$
$x(t) = \sum_{-\infty}^{+\infty} \delta(t - kT)$|$X_k = \frac{1}{T}$

</div>

- Square-Wave: (between 0 and 1, even, duty: $\alpha T$)

$$
X_k = \frac{sin(\alpha k\pi)}{k\pi}
$$

## non-Periodical Signals

- Low-Pass

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

$x$|FT
:---:|:---:
$x(t) = 1, -t_0 \le t \le t_0$|$X(jw) = \frac{sin(wt_0)}{\frac{w}{2}}$
$x(t) = \frac{sin(w_0 t)}{\pi t}$|$X(jw) = 1, -w_0 \le t \le w_0$
$x[n] = 1, -n_0 \le t \le n_0$|$X(e^{jw}) = \frac{sin(w\frac{2n_0 + 1}{2})}{sin(\frac{w}{2})}$
$x[n] = \frac{sin(w_0n)}{\pi n}$|$X(e^{jw}) = 1, -w_0 \le t \le w_0$

</div>

- $1$ and $\delta$

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

$x$|FT|L/Z
:---:|:---:|:---:
$x(t) = 1$|$X(jw) = 2\pi \delta(w)$|-
$x(t) = \delta(t)$|$X(jw) = 1$|$X(s) = 1, s \in C$
$x[n] = 1$|$X(e^{jw}) = 2\pi\sum_{-\infty}^{+\infty}\delta(w-2\pi k)$|-
$x[n] = \delta[n]$|$X(e^{jw}) = 1$|$X(z) = 1, z \in C$

</div>

- Unit-Step

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

$x$|FT
:---:|:---:
$u(t) - \frac{1}{2}$|$X(jw) = \frac{1}{jw}$
$u[n] - \frac{1}{2}$|$X(e^{jw}) = \frac{1}{1 - e^{-jw}}$

</div>

- Sinusoid

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

$x$|FT
:---:|:---:
$cos(w_c t)$|$X(jw) = \pi [\delta(w + w_c) + \delta(w - w_c)]$
$sin(w_ct)$|$X(jw) = j\pi [\delta(w + w_c) - \delta(w - w_c)]$

</div>

## L/Z transforms

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

$x$|L/Z
:---:|:---:
$e^{at}u(t)$|$X(s) = \frac{1}{s - a},\text{Re}\{s\}>a$
$-e^{at}u(-t)$|$X(s) = \frac{1}{s - a},\text{Re}\{s\}<a$
$a^nu[n]$|$X(z) = \frac{z}{z-a},\|z\|>\|a\|$
$-a^nu[-n-1]$|$X(z) = \frac{z}{z-a},\|z\|<\|a\|$

</div>
