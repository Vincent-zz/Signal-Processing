# Properties

## **1. Shared Properties**

between FT and FS, L, Z

$$
[X_k]_{FS}\stackrel{w \leftarrow kw_0}{\Leftarrow}[X(w)]_{FT}
\begin{cases}
[X(jw)]_{CTFT}\stackrel{jw \leftarrow s}{\Rightarrow}[X(s)]_L\\
[X(e^{jw})]_{DTFT}\stackrel{e^{jw} \leftarrow z}{\Rightarrow}[X(z)]_Z
\end{cases}
$$

## Shifting

- **Time-Shift**:

$$
x(t - t') \leftrightarrow X(w)e^{-jwt'}\\
x[n - n'] \leftrightarrow X(w)e^{-jwn'}
$$

- **Frequency-Shift**:

$$
x(t)e^{jw't} \leftrightarrow X(w-w')\\
x[n]e^{jw'n} \leftrightarrow X(w-w')
$$

## Differential and Integration

- **Differential**:

$$
\begin{aligned}
x'(t) &\leftrightarrow jw X(w)\\
x[n] - x[n - 1] &\leftrightarrow (1 - e^{-jw}) X(w)
\end{aligned}
$$

- **Integration/Accumulation**:

  for FS, L, Z: Inversion of Differential

  for FT:

$$
\begin{aligned}
\int_{-\infty}^{t} x(t)dt &= x(t) \ast u(t)\\
\sum_{-\infty}^{n} x[n] &= x[n] \ast u[n]
\end{aligned}
$$

## Conjugate

$$
x(t)^* \leftrightarrow X^*((jw)^*)\\
x[n]^* \leftrightarrow X^*((e^{jw})^*)
$$

## Time-Inversion

$$
x(-t) \leftrightarrow X(-(jw))\\
x[-n] \leftrightarrow X((e^{jw})^{-1})
$$

## **2. Convolution and Multiplication**

- **FT**:

$$
\begin{aligned}
x \ast y &\leftrightarrow X(w)Y(w)\\
xy &\leftrightarrow \frac{1}{2\pi}X(w)(\ast/\circledast)Y(w)
\end{aligned}
$$

- **FS**:

$$
\begin{aligned}
x \circledast y &\leftrightarrow(T/N)X_kY_k\\
xy &\leftrightarrow X_k(\ast/\circledast)Y_k\\
\end{aligned}
$$

- **L, Z**:

$$
\begin{aligned}
x(t) \ast y(t) &\leftrightarrow X(s)Y(s)\\
x[n] \ast y[n] &\leftrightarrow X(z)Y(z)\\
\end{aligned}
$$

\* about $\circledast$:

$$
\tilde{x}[n] \circledast \tilde{y}[n] = x[n] \ast \tilde{y}[n] = \tilde{x}[n] \ast y[n] = (x[n] \ast y[n])R_N\\
\begin{cases}
\tilde{x}[n] = x[n]R_N\\
\tilde{y}[n] = y[n]R_N
\end{cases}
$$

## **3. Some Conclusions**

- **F**:

$$
x\text{--real} \leftrightarrow
\begin{cases}
|X|\text{--even}\\
\angle X\text{--odd}
\end{cases}
$$

$$
\begin{cases}
x\text{--real, even} &\leftrightarrow X\text{--real, even}\\
x\text{--real, odd} &\leftrightarrow X\text{--pure imaginary, odd}
\end{cases}
$$

- **L, Z**:

$$
x\text{--real} \leftrightarrow \text{zeros(/poles) show up in conjugate pairs}
$$
