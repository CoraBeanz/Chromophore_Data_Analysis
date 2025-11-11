# Reaction Scheme

<div align="center">

$$
D + A \xrightarrow{k_{bind}} C, \qquad
C + O \xrightarrow{k_{bleach}} A + B
$$

</div>

---

## Mass-Action Rates

<div align="center">

$$
r_{bind} = k_{bind}[D][A], \qquad
r_{bleach} = k_{bleach}[C][O]
$$

</div>

---

## Full ODE System (Mass-Action Kinetics)

<div align="center">

$$
\begin{aligned}
\frac{d[D]}{dt} &= -k_{bind}[D][A], \\
\frac{d[A]}{dt} &= -k_{bind}[D][A] + k_{bleach}[C][O], \\
\frac{d[C]}{dt} &= k_{bind}[D][A] - k_{bleach}[C][O], \\
\frac{d[B]}{dt} &= k_{bleach}[C][O]
\end{aligned}
$$

</div>

---

## Conservation Relations

<div align="center">

$$
A_{tot} = [A] + [C], \qquad
D_{tot} = [D] + [C] + [B]
$$

</div>

---

## Quantity of Interest

<div align="center">

$$
\frac{d[B]}{dt} = k_{bleach}[C][O]
$$

</div>

---

## Pseudo-First-Order Approximation

Assume $[D](t) \approx D_0$ and $[O](t) \approx O_0$ (constants).

Define the effective bleaching rate:

<div align="center">

$$
k_{bleach}^{eff} = k_{bleach} O_0
$$

</div>

Substitute $[A] = A_{tot} - [C]$ and $[D] \approx D_0$:

<div align="center">

$$
\frac{d[C]}{dt}
= k_{bind} D_0 (A_{tot} - [C]) - k_{bleach} O_0 [C]
= k_{bind} D_0 A_{tot} - (k_{bind} D_0 + k_{bleach} O_0)[C]
$$

</div>

---

## Linear ODE Form

<div align="center">

$$
\frac{d[C]}{dt} + \lambda [C] = \alpha
$$

$$
\lambda = k_{bind} D_0 + k_{bleach} O_0, \qquad
\alpha = k_{bind} D_0 A_{tot}
$$

</div>

---

## Solution by Integrating Factor (General $C_0$)

<div align="center">

$$
[C](t) = C_0 e^{-\lambda t} + \frac{\alpha}{\lambda} (1 - e^{-\lambda t})
$$

$$
[C](t) = C_0 e^{-(k_{bind} D_0 + k_{bleach} O_0)t} + 
\frac{k_{bind} D_0 A_{tot}}{k_{bind} D_0 + k_{bleach} O_0} 
(1 - e^{-(k_{bind} D_0 + k_{bleach} O_0)t})
$$

</div>

---

## Special Case (Initially No Complex, $C_0 = 0$)

<div align="center">

$$
[C](t) = \frac{k_{bind} D_0 A_{tot}}{k_{bind} D_0 + k_{bleach} O_0} 
(1 - e^{-(k_{bind} D_0 + k_{bleach} O_0)t})
$$

</div>

---

## Instantaneous Dye Consumption Rate

General $C_0$:

<div align="center">

$$
\frac{d[B]}{dt} = k_{bleach} O_0 
\left[
C_0 e^{-(k_{bind} D_0 + k_{bleach} O_0)t} +
\frac{k_{bind} D_0 A_{tot}}{k_{bind} D_0 + k_{bleach} O_0} 
(1 - e^{-(k_{bind} D_0 + k_{bleach} O_0)t})
\right]
$$

</div>

For $C_0 = 0$:

<div align="center">

$$
\frac{d[B]}{dt} =
\frac{k_{bleach} O_0 k_{bind} D_0 A_{tot}}
{k_{bind} D_0 + k_{bleach} O_0}
\left(1 - e^{-(k_{bind} D_0 + k_{bleach} O_0)t}\right)
$$

</div>

---

## Integrated Consumed Dye $B(t)$

Define $\lambda = k_{bind} D_0 + k_{bleach} O_0$ and $\alpha = k_{bind} D_0 A_{tot}$.

General $C_0$:

<div align="center">

$$
B(t) = \frac{k_{bleach} O_0 C_0}{\lambda}(1 - e^{-\lambda t}) + 
\frac{k_{bleach} O_0 \alpha}{\lambda} \left(t - \frac{1 - e^{-\lambda t}}{\lambda}\right)
$$

</div>

For $C_0 = 0$:

<div align="center">

$$
B(t) =
\frac{k_{bleach} O_0 k_{bind} D_0 A_{tot}}
{k_{bind} D_0 + k_{bleach} O_0}
\left[
t - \frac{1 - e^{-(k_{bind} D_0 + k_{bleach} O_0)t}}{k_{bind} D_0 + k_{bleach} O_0}
\right]
$$

</div>

---

## Notes

- With $[O]$ in large excess, the photobleaching $k_{bleach}[C][O]$ reduces to an effective first-order rate $k_{bleach} O_0 [C]$.  
- If $[O]$ is not in large excess, $[O](t)$ must be solved simultaneously (no simple analytical form).  
- Units: $k_{bleach}$ → M$^{-1}$s$^{-1}$; $k_{bleach} O_0$ → s$^{-1}$.
