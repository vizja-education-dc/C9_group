# Exercise 12. A Parameter Revealed by a Row Operation

## 1. Problem Statement

Given the parameterized matrix:
$$
A(t) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & t \\ 0 & 1 & 1 \end{pmatrix}, \qquad t \in \mathbb{R}
$$

1. Perform the row operation $R_2 \leftarrow R_2 - 2R_1$ before evaluating the determinant.
2. Use the structure of the resulting matrix to find the value of $t$ for which $A(t)$ is not invertible.
3. Explain what special geometric/algebraic relationship occurs among the rows of the original matrix for the critical value of $t$.

---

## 2. Theoretical Background and Concepts

### Invertibility and Determinant
A matrix $A(t)$ is non-invertible if and only if $\det A(t) = 0$.

### Elementary Row Operations and Pivots
Performing a row replacement $R_i \leftarrow R_i + c R_j$ preserves the determinant exactly:
$$
\det(A') = \det(A)
$$
If a choice of parameter causes an entire row to become zero after Gaussian elimination, the rank is strictly less than full, the determinant is zero, and the matrix is singular.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Performing the Operation $R_2 \leftarrow R_2 - 2R_1$

Compute the new second row:
$$
R_2 - 2R_1 = \begin{pmatrix} 2 & 4 & t \end{pmatrix} - 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 4 - 4 & t - 6 \end{pmatrix} = \begin{pmatrix} 0 & 0 & t - 6 \end{pmatrix}
$$

The transformed matrix is:
$$
A_1(t) = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & t - 6 \\ 0 & 1 & 1 \end{pmatrix}
$$
Because row replacement preserves the determinant:
$$
\det A(t) = \det A_1(t)
$$

---

### 3.2. Evaluating $\det A_1(t)$ Using Its Sparse Structure

Swap $R_2$ and $R_3$ to put the matrix into upper triangular form ($R_2 \leftrightarrow R_3$):
$$
A_2(t) = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & t - 6 \end{pmatrix}
$$
Because a row swap negates the determinant:
$$
\det A_1(t) = -\det A_2(t)
$$
Since $A_2(t)$ is upper triangular, its determinant is the product of diagonal entries:
$$
\det A_2(t) = (1) \cdot (1) \cdot (t - 6) = t - 6
$$
Therefore:
$$
\det A(t) = -(t - 6) = 6 - t
$$

---

### 3.3. Finding the Singular Parameter Value

The matrix $A(t)$ is not invertible if and only if:
$$
\det A(t) = 0 \iff 6 - t = 0 \iff t = 6
$$

$$
\boxed{t = 6}
$$

---

### 3.4. What Happens to the Rows When $t = 6$

Substitute $t = 6$ back into the original matrix:
$$
A(6) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix}
$$
- **Proportionality:** Notice that row 2 is an exact scalar multiple of row 1:
  $$
  R_2 = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix} = 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = 2 R_1
  $$
- **Row of Zeros:** Under the operation $R_2 \leftarrow R_2 - 2R_1$, the entire second row collapses to the zero vector $\begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$.
- **Dimensionality:** The three row vectors span only a 2-dimensional subspace in $\mathbb{R}^3$, making the matrix rank-deficient ($\operatorname{rank} = 2 < 3$) and hence non-invertible.

---

## 4. Verification and Consistency Checks

1. **Direct Sarrus' Rule Expansion of $A(t)$:**
   $$
   \begin{matrix}
   1 & 2 & 3 & 1 & 2 \\
   2 & 4 & t & 2 & 4 \\
   0 & 1 & 1 & 0 & 1
   \end{matrix}
   $$
   - Main diagonals: $(1 \cdot 4 \cdot 1) + (2 \cdot t \cdot 0) + (3 \cdot 2 \cdot 1) = 4 + 0 + 6 = 10$.
   - Anti-diagonals: $(0 \cdot 4 \cdot 3) + (1 \cdot t \cdot 1) + (1 \cdot 2 \cdot 2) = 0 + t + 4 = t + 4$.
   - Determinant:
     $$
     \det A(t) = 10 - (t + 4) = 6 - t \quad \checkmark
     $$
   Setting $6 - t = 0$ confirms $t = 6$.

2. **Rank Check for $t \neq 6$:**
   If $t = 7$, $\det A(7) = 6 - 7 = -1 \neq 0$ (invertible).
   If $t = 5$, $\det A(5) = 6 - 5 = 1 \neq 0$ (invertible).
   Only $t = 6$ causes linear dependence between the first two rows.
