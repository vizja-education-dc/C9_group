# Exercise 3. Swapping Two Rows

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 2 & 1 & 1 \end{pmatrix}
$$

1. Compute $\det A$.
2. Let $B$ be the matrix obtained by swapping the first and second rows of $A$. Predict $\det B$ using the theoretical properties of determinants.
3. Compute $\det B$ directly and verify the prediction.

---

## 2. Theoretical Background and Concepts

### Row Swap Property (Alternating Property)
The determinant is an alternating multilinear form with respect to its rows. If a matrix $B$ is obtained from $A$ by swapping any two rows ($R_i \leftrightarrow R_j$, $i \neq j$), the determinant changes sign:
$$
\det B = -\det A
$$
This corresponds algebraically to multiplying $A$ by an elementary permutation matrix $P$ with $\det P = -1$:
$$
\det B = \det(PA) = \det(P) \det(A) = (-1) \det(A)
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $\det A$

Expanding along the first row (or third column) of $A$:
$$
\det A = 1 \cdot \begin{vmatrix} 3 & 1 \\ 1 & 1 \end{vmatrix} - 2 \cdot \begin{vmatrix} 0 & 1 \\ 2 & 1 \end{vmatrix} + 0 \cdot \begin{vmatrix} 0 & 3 \\ 2 & 1 \end{vmatrix}
$$

Compute the $2 \times 2$ determinants:
- $\begin{vmatrix} 3 & 1 \\ 1 & 1 \end{vmatrix} = (3)(1) - (1)(1) = 3 - 1 = 2$
- $\begin{vmatrix} 0 & 1 \\ 2 & 1 \end{vmatrix} = (0)(1) - (1)(2) = 0 - 2 = -2$

Substitute:
$$
\det A = 1(2) - 2(-2) + 0 = 2 + 4 = 6
$$

$$
\boxed{\det A = 6}
$$

---

### 3.2. Formulating Matrix $B$ and Predicting $\det B$

Swap the first and second rows of $A$ ($R_1 \leftrightarrow R_2$):
$$
B = \begin{pmatrix} 0 & 3 & 1 \\ 1 & 2 & 0 \\ 2 & 1 & 1 \end{pmatrix}
$$

**Theoretical Prediction:**
Because $B$ is obtained by a single row transposition, its determinant must satisfy:
$$
\det B = -\det A = -6
$$

$$
\boxed{\text{Prediction: } \det B = -6}
$$

---

### 3.3. Direct Computation of $\det B$

Expand along the first row of $B$:
$$
\det B = 0 \cdot C_{11} - 3 \cdot \begin{vmatrix} 1 & 0 \\ 2 & 1 \end{vmatrix} + 1 \cdot \begin{vmatrix} 1 & 2 \\ 2 & 1 \end{vmatrix}
$$

Compute the minors:
- $\begin{vmatrix} 1 & 0 \\ 2 & 1 \end{vmatrix} = (1)(1) - (0)(2) = 1$
- $\begin{vmatrix} 1 & 2 \\ 2 & 1 \end{vmatrix} = (1)(1) - (2)(2) = 1 - 4 = -3$

Substitute:
$$
\det B = 0 - 3(1) + 1(-3) = -3 - 3 = -6
$$

$$
\boxed{\det B = -6}
$$
The direct calculation confirms the prediction $\det B = -\det A = -6$.

---

## 4. Verification and Consistency Checks

1. **Sarrus' Rule Check for $B$:**
   $$
   \begin{matrix}
   0 & 3 & 1 & 0 & 3 \\
   1 & 2 & 0 & 1 & 2 \\
   2 & 1 & 1 & 2 & 1
   \end{matrix}
   $$
   - Main diagonals: $(0 \cdot 2 \cdot 1) + (3 \cdot 0 \cdot 2) + (1 \cdot 1 \cdot 1) = 0 + 0 + 1 = 1$.
   - Anti-diagonals: $(2 \cdot 2 \cdot 1) + (1 \cdot 0 \cdot 0) + (1 \cdot 1 \cdot 3) = 4 + 0 + 3 = 7$.
   - $\det B = 1 - 7 = -6 \quad \checkmark$

2. **Elementary Matrix Verification:**
   The row swap $R_1 \leftrightarrow R_2$ corresponds to $B = PA$ where:
   $$
   P = \begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}
   $$
   $\det P = 0(0) - 1(1 - 0) + 0 = -1$.
   Therefore, $\det B = \det(PA) = \det(P)\det(A) = (-1)(6) = -6 \quad \checkmark$
