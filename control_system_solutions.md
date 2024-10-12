
# Control System Problem Set Solutions

## P3.1: Spring-Mass-Damper System State Space Representation

### Problem:
Given the spring-mass-damper system in Figure P3.1:
1. Identify a suitable set of state variables.
2. Obtain the set of first-order differential equations in terms of the state variables.
3. Write the state differential equation.

### Solution:

The differential equation for the spring-mass-damper system is:
\[
M \ddot{y}(t) + b \dot{y}(t) + k y(t) = F(t)
\]
where:
- \( M \) = mass,
- \( b \) = damping coefficient,
- \( k \) = spring constant,
- \( F(t) \) = input force,
- \( y(t) \) = output displacement.

#### Step 1: Define State Variables
Let:
- \( x_1(t) = y(t) \) (position),
- \( x_2(t) = \dot{y}(t) \) (velocity).

#### Step 2: Obtain First-Order Differential Equations
The state equations are:
\[
\dot{x}_1(t) = x_2(t)
\]
\[
M \dot{x}_2(t) = F(t) - b x_2(t) - k x_1(t)
\]
or equivalently:
\[
\dot{x}_2(t) = rac{F(t) - b x_2(t) - k x_1(t)}{M}
\]

#### Step 3: State Differential Equation (Matrix Form)
In matrix form, the state-space representation is:
\[
egin{bmatrix}
\dot{x}_1(t) \
\dot{x}_2(t)
\end{bmatrix}
=
egin{bmatrix}
0 & 1 \
-rac{k}{M} & -rac{b}{M}
\end{bmatrix}
egin{bmatrix}
x_1(t) \
x_2(t)
\end{bmatrix}
+
egin{bmatrix}
0 \
rac{1}{M}
\end{bmatrix} F(t)
\]

---

## P3.3: RLC Circuit State Space Representation

### Problem:
An RLC network is shown in Figure P3.3. Define the state variables as:
\[
x_1(t) = i_L(t), \quad x_2(t) = v_C(t)
\]
Obtain the state differential equations.

### Solution:

Using Kirchhoff's laws:
- Inductor voltage-current relation: \( v_L(t) = L rac{di_L(t)}{dt} \),
- Capacitor voltage-current relation: \( i_C(t) = C rac{dv_C(t)}{dt} \),
- Kirchhoff's Voltage Law (KVL): \( v_1(t) = v_C(t) + i_R(t) R + v_L(t) \).

#### Step 1: State Variables
Let:
- \( x_1(t) = i_L(t) \) (inductor current),
- \( x_2(t) = v_C(t) \) (capacitor voltage).

#### Step 2: State Differential Equations
The state equations are:
\[
\dot{x}_1(t) = rac{v_1(t) - x_2(t)}{L} - rac{R}{L} x_1(t)
\]
\[
\dot{x}_2(t) = rac{x_1(t)}{C}
\]

#### Step 3: State Differential Equation (Matrix Form)
The state-space representation in matrix form is:
\[
egin{bmatrix}
\dot{x}_1(t) \
\dot{x}_2(t)
\end{bmatrix}
=
egin{bmatrix}
-rac{R}{L} & -rac{1}{L} \
rac{1}{C} & 0
\end{bmatrix}
egin{bmatrix}
x_1(t) \
x_2(t)
\end{bmatrix}
+
egin{bmatrix}
rac{1}{L} \
0
\end{bmatrix} v_1(t)
\]

---

## P3.5: Closed-Loop Transfer Function and State Variable Model

### Problem:
1. Determine the closed-loop transfer function \( T(s) = rac{Y(s)}{R(s)} \).
2. Determine a state variable model and sketch a block diagram model in phase-variable form.

### Solution:

#### 1. Closed-Loop Transfer Function

Given the open-loop transfer functions:
\[
G(s) = rac{s + 2}{s + 8}, \quad H(s) = rac{1}{s - 3}
\]
The closed-loop transfer function is:
\[
T(s) = rac{G(s)}{1 + G(s) H(s)} = rac{rac{s + 2}{s + 8}}{1 + rac{s + 2}{s + 8} \cdot rac{1}{s - 3}}
\]
Simplifying:
\[
T(s) = rac{(s + 2)(s - 3)}{(s + 8)(s - 3) + (s + 2)} = rac{s^2 - s - 6}{s^2 + 5s + 22}
\]

#### 2. State Variable Model

Define the state variables:
\[
x_1(t) = V_1(t), \quad x_2(t) = \dot{V}_1(t)
\]
The state-space representation is:
\[
\dot{x}_1(t) = x_2(t)
\]
\[
\dot{x}_2(t) = -5x_2(t) - 22x_1(t) + R(t)
\]

The block diagram is a standard feedback system with the state variables representing the system dynamics.

---

## P3.12: State Variable Model and Transition Matrix

### Problem:
A system is described by its transfer function:
\[
T(s) = rac{Y(s)}{R(s)} = rac{8(s + 5)}{s^3 + 12s^2 + 44s + 48}
\]
1. Determine a state variable model.
2. Determine the state transition matrix \( \Phi(t) \).

### Solution:

#### 1. State Variable Model

Since the transfer function is a third-order system, we define three state variables:
\[
x_1(t) = y(t), \quad x_2(t) = \dot{y}(t), \quad x_3(t) = \ddot{y}(t)
\]
The state-space model is:
\[
\dot{x}_1(t) = x_2(t)
\]
\[
\dot{x}_2(t) = x_3(t)
\]
\[
\dot{x}_3(t) = -12x_3(t) - 44x_2(t) - 48x_1(t) + 8r(t)
\]

#### 2. State Transition Matrix \( \Phi(t) \)

The state transition matrix \( \Phi(t) \) is given by:
\[
\Phi(t) = e^{At}
\]
where \( A \) is the system matrix. Computing \( e^{At} \) provides the transition matrix for the system's time response.

---

## P3.17: State-Space to Transfer Function

### Problem:
The state equations are:
\[
\dot{x}(t) = egin{bmatrix} 1 & 1 & -1 \ 4 & 3 & 0 \ -2 & 1 & 10 \end{bmatrix} x(t) + egin{bmatrix} 0 \ 0 \ 4 \end{bmatrix} u(t)
\]
with output:
\[
y(t) = egin{bmatrix} 1 & 0 & 0 \end{bmatrix} x(t)
\]
Determine \( G(s) = rac{Y(s)}{U(s)} \).

### Solution:

The transfer function is obtained using the formula:
\[
G(s) = C (sI - A)^{-1} B + D
\]
Substituting \( A \), \( B \), \( C \), and \( D \), we get the transfer function \( G(s) \).

---
