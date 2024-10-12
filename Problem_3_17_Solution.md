
# Problem 3.17 Solution

## Given State-Space Representation

The system is described by the following state-space equations:

\[
\dot{x}(t) = 
\begin{pmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 10
\end{pmatrix}
x(t) + 
\begin{pmatrix}
0 \\
0 \\
4
\end{pmatrix}
u(t)
\]

The output equation is:

\[
y(t) = [1 \ 0 \ 0] x(t)
\]

## Step 1: Finding the Transfer Function \( G(s) \)

We can express the system in the Laplace domain as:

\[
sX(s) = A X(s) + B U(s)
\]

Rearranging for \( X(s) \):

\[
(sI - A) X(s) = B U(s)
\]

So, we can write:

\[
X(s) = (sI - A)^{-1} B U(s)
\]

The output equation in the Laplace domain is:

\[
Y(s) = C X(s)
\]

Thus, the transfer function is:

\[
G(s) = \frac{Y(s)}{U(s)} = C (sI - A)^{-1} B
\]

## Step 2: Compute \( sI - A \)

The matrix \( A \) is:

\[
A = 
\begin{pmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 10
\end{pmatrix}
\]

The identity matrix \( I \) is:

\[
I = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
\]

Therefore, \( sI - A \) is:

\[
sI - A = 
\begin{pmatrix}
s-1 & -1 & 1 \\
-4 & s-3 & 0 \\
2 & -1 & s-10
\end{pmatrix}
\]

## Step 3: Compute \( (sI - A)^{-1} \)

The inverse of \( sI - A \) is:

\[
(sI - A)^{-1} = 
\begin{pmatrix}
\frac{4800}{4800s - 12800} & \frac{-1760}{4800s - 12800} & \frac{480}{4800s - 12800} \\
\frac{-1600}{1200s - 3200} & \frac{5s - 6}{15s - 40} & \frac{-160}{1200s - 3200} \\
\frac{40}{120s - 320} & \frac{-s - 1}{30s - 80} & \frac{3s - 7}{30s - 80}
\end{pmatrix}
\]

## Step 4: Compute the Transfer Function

Given \( C = [1 \ 0 \ 0] \) and \( B = 
\begin{pmatrix}
0 \\
0 \\
4
\end{pmatrix}
\), we compute:

\[
G(s) = C (sI - A)^{-1} B
\]

This simplifies to:

\[
G(s) = \frac{4(3 - s)}{s^3 - 14s^2 + 37s + 20}
\]

## Final Transfer Function

Thus, the final transfer function is:

\[
G(s) = \frac{4(3 - s)}{s^3 - 14s^2 + 37s + 20}
\]
