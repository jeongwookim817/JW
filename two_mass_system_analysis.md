
# Two-Mass System Analysis

## Problem Overview
In a two-mass system, the given parameters are:

- Masses: 
  - \( m_1 = m_2 = 1 \)
- Spring constants: 
  - \( K_1 = K_2 = 1 \)

### Objective:
1. Derive the equations of motion (a).
2. Calculate the transfer function from \( U(s) \) to \( Y(s) \) (b).

## 1. Equation of Motion Derivation (a)

### First Mass \( m_1 \):
The forces acting on the first mass \( m_1 \) are:
- Restoring force by spring \( K_1 \): \( -K_1 x(t) \)
- Interaction with mass \( m_2 \) via spring \( K_2 \): \( K_2 (y(t) - x(t)) \)

Thus, the equation of motion for \( m_1 \) is:
\[
m_1 \ddot{x}(t) = -K_1 x(t) + K_2 (y(t) - x(t))
\]
Substituting \( m_1 = 1 \), \( K_1 = 1 \), and \( K_2 = 1 \):
\[
\ddot{x}(t) = -x(t) + (y(t) - x(t)) = -2x(t) + y(t)
\]

### Second Mass \( m_2 \):
The forces acting on the second mass \( m_2 \) are:
- Interaction with mass \( m_1 \) via spring \( K_2 \): \( -K_2 (y(t) - x(t)) \)
- External input force \( u(t) \)

Thus, the equation of motion for \( m_2 \) is:
\[
m_2 \ddot{y}(t) = K_2 (x(t) - y(t)) + u(t)
\]
Substituting \( m_2 = 1 \) and \( K_2 = 1 \):
\[
\ddot{y}(t) = (x(t) - y(t)) + u(t)
\]

## 2. Transfer Function Calculation (b)
We apply Laplace transforms to convert the equations into the frequency domain. Assume initial conditions are zero.

### First Equation's Laplace Transform:
\[
s^2 X(s) = -2 X(s) + Y(s)
\]
Rearranging:
\[
(s^2 + 2) X(s) = Y(s)
\]
Thus:
\[
X(s) = rac{Y(s)}{s^2 + 2}
\]

### Second Equation's Laplace Transform:
\[
s^2 Y(s) = X(s) - Y(s) + U(s)
\]
Rearranging:
\[
(s^2 + 1) Y(s) = X(s) + U(s)
\]
Substitute \( X(s) \) from the first equation:
\[
(s^2 + 1) Y(s) = rac{Y(s)}{s^2 + 2} + U(s)
\]
Multiplying through by \( (s^2 + 2) \):
\[
(s^2 + 1)(s^2 + 2) Y(s) = Y(s) + (s^2 + 2) U(s)
\]
Simplifying:
\[
(s^4 + 3s^2 + 2) Y(s) = Y(s) + (s^2 + 2) U(s)
\]
\[
(s^4 + 3s^2 + 1) Y(s) = (s^2 + 2) U(s)
\]
Thus, the transfer function \( rac{Y(s)}{U(s)} \) is:
\[
rac{Y(s)}{U(s)} = rac{s^2 + 2}{s^4 + 3s^2 + 1}
\]
