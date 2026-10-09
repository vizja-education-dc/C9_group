# Exercise 6. Parameter and Invertibility

## 1. Problem Statement

Given the parameterized family of matrices:
$$
A(t) = \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix}, \qquad t \in \mathbb{R}
$$

1. Find all values of $t$ for which the matrix $A(t)$ is not invertible.
2. Explain the fundamental connection between non-invertibility and the vanishing of the determinant.

---

## 2. Theoretical Background and Concepts

### Determinant and Invertibility Theorem
For any square matrix $M \in M_n(\mathbb{R})$:
$$
M \text{ is invertible} \iff \det(M) \neq 0
$$
Conversely, $M$ is **not invertible (singular)** if and only if its determinant is zero:
$$
M \text{ is singular} \iff \det(M) = 0
$$

### Geometric and Algebraic Interpretation of $\det M = 0$
- **Algebraic perspective:** When $\det M = 0$, the rows (and columns) of $M$ are linearly dependent. The rank of $M$ is strictly less than $n$, and the linear system $Mx = 0$ has non-trivial solutions ($\ker(M) \neq \{0\}$).
- **Geometric perspective:** The linear map $x \mapsto Mx$ squashes $n$-dimensional volume to zero (for $n=2$, it collapses the 2D plane onto a 1D line or a point), making the mapping non-bijective and hence irreversible.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing the Determinant as a Function of $t$

Apply the $2 \times 2$ determinant formula:
$$
\det A(t) = \begin{vmatrix} t & 1 \\ 2 & t \end{vmatrix} = (t)(t) - (1)(2) = t^2 - 2
$$

---

### 3.2. Solving for Values of Non-Invertibility

Set the determinant equal to zero:
$$
\det A(t) = 0 \iff t^2 - 2 = 0 \iff t^2 = 2
$$
Solving for $t$:
$$
t = \sqrt{2} \quad \text{or} \quad t = -\sqrt{2}
$$

$$
\boxed{t = \pm\sqrt{2}}
$$

Thus, the matrix $A(t)$ fails to be invertible precisely when $t \in \{-\sqrt{2}, \sqrt{2}\}$.

---

### 3.3. Explaining the Connection to $\det = 0$

1. **For $t = \sqrt{2}$:**
   $$
   A(\sqrt{2}) = \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix}
   $$
   Observe that the second row is a direct multiple of the first row:
   $$
   R_2 = \begin{pmatrix} 2 & \sqrt{2} \end{pmatrix} = \sqrt{2} \begin{pmatrix} \sqrt{2} & 1 \end{pmatrix} = \sqrt{2} R_1
   $$
   The rows are linearly dependent, so the column vectors lie along the same line, resulting in $\det = 0$ and non-invertibility.

2. **For $t = -\sqrt{2}$:**
   $$
   A(-\sqrt{2}) = \begin{pmatrix} -\sqrt{2} & 1 \\ 2 & -\sqrt{2} \end{pmatrix}
   $$
   Observe that:
   $$
   R_2 = \begin{pmatrix} 2 & -\sqrt{2} \end{pmatrix} = -\sqrt{2} \begin{pmatrix} -\sqrt{2} & 1 \end{pmatrix} = -\sqrt{2} R_1
   $$
   Again, the rows are collinear and proportional, resulting in $\det = 0$ and non-invertibility.

For any $t \neq \pm\sqrt{2}$, $\det A(t) \neq 0$ and the rows are linearly independent, ensuring an inverse exists:
$$
A(t)^{-1} = \frac{1}{t^2 - 2} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix}
$$

---

## 4. Verification and Consistency Checks

1. **Kernel / Null Space Check for $t = \sqrt{2}$:**
   Solve $A(\sqrt{2}) x = 0$:
   $$
   \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies \sqrt{2} x_1 + x_2 = 0 \implies x_2 = -\sqrt{2} x_1
   $$
   The non-zero vector $v = \begin{pmatrix} 1 \\ -\sqrt{2} \end{pmatrix}$ satisfies $A(\sqrt{2}) v = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$.
   Since a non-trivial vector is mapped to zero, the map is not injective, confirming it cannot be invertible. $\checkmark$

2. **Inverse Formula Check for Generic $t$:**
   Compute $A(t) A(t)^{-1}$:
   $$
   \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix} \cdot \frac{1}{t^2 - 2} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix} = \frac{1}{t^2 - 2} \begin{pmatrix} t^2 - 2 & -t + t \\ 2t - 2t & -2 + t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
   $$
   The inverse is well-defined if and only if the denominator $t^2 - 2 \neq 0$, confirming $t = \pm\sqrt{2}$ are the only singular points. $\checkmark$
