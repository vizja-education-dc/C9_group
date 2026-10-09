# Exercise 4. Triangular Matrix

## 1. Problem Statement

Given the matrix:
$$
T = \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}
$$

1. Without carrying out a full standard expansion, compute $\det T$.
2. State the general theorem for the determinant of an arbitrary triangular matrix.
3. Explain why this rule holds using the given example.

---

## 2. Theoretical Background and Concepts

### Triangular Matrices
- An **upper triangular matrix** is a square matrix where all entries below the main diagonal are zero ($a_{ij} = 0$ for all $i > j$).
- A **lower triangular matrix** is a square matrix where all entries above the main diagonal are zero ($a_{ij} = 0$ for all $i < j$).
- A **diagonal matrix** is both upper and lower triangular ($a_{ij} = 0$ for all $i \neq j$).

### General Theorem
The determinant of any upper triangular, lower triangular, or diagonal matrix equals the **product of the entries on its main diagonal**:
$$
\det T = \prod_{i=1}^n t_{ii} = t_{11} \cdot t_{22} \cdots t_{nn}
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Identifying Matrix Structure and Main Diagonal

Matrix $T$ is upper triangular because all entries in positions $(2,1)$, $(3,1)$, and $(3,2)$ are zero:
$$
T = \begin{pmatrix} \mathbf{2} & 4 & 1 \\ 0 & \mathbf{-3} & 5 \\ 0 & 0 & \mathbf{7} \end{pmatrix}
$$
The entries along the main diagonal are:
$$
t_{11} = 2, \qquad t_{22} = -3, \qquad t_{33} = 7
$$

---

### 3.2. Computing the Determinant

Applying the triangular matrix product rule directly:
$$
\det T = t_{11} \cdot t_{22} \cdot t_{33} = (2) \cdot (-3) \cdot (7) = -42
$$

$$
\boxed{\det T = -42}
$$

---

### 3.3. Explanation via Successive Laplace Expansion

To understand why the product of diagonal elements always emerges:
1. Expand $\det T$ along the **first column**, which contains only one non-zero entry at $(1,1)$:
   $$
   \det T = 2 \cdot \begin{vmatrix} -3 & 5 \\ 0 & 7 \end{vmatrix} - 0 \cdot C_{21} + 0 \cdot C_{31} = 2 \cdot \begin{vmatrix} -3 & 5 \\ 0 & 7 \end{vmatrix}
   $$
2. The remaining $2 \times 2$ minor is itself an upper triangular matrix. Expanding it along its first column:
   $$
   \begin{vmatrix} -3 & 5 \\ 0 & 7 \end{vmatrix} = (-3)(7) - (5)(0) = (-3)(7)
   $$
3. Combining these steps gives:
   $$
   \det T = 2 \cdot [(-3) \cdot 7] = -42
   $$
Each successive step along the first column isolates exactly one diagonal entry, proving that all off-diagonal entries have zero contribution.

---

## 4. Verification and Consistency Checks

1. **Verification via Sarrus' Rule:**
   $$
   \begin{matrix}
   2 & 4 & 1 & 2 & 4 \\
   0 & -3 & 5 & 0 & -3 \\
   0 & 0 & 7 & 0 & 0
   \end{matrix}
   $$
   - Main diagonals: $(2 \cdot (-3) \cdot 7) + (4 \cdot 5 \cdot 0) + (1 \cdot 0 \cdot 0) = -42 + 0 + 0 = -42$.
   - Anti-diagonals: $(0 \cdot (-3) \cdot 1) + (0 \cdot 5 \cdot 2) + (7 \cdot 0 \cdot 4) = 0 + 0 + 0 = 0$.
   - $\det T = -42 - 0 = -42 \quad \checkmark$
   Notice that all products except the main diagonal contain at least one factor of zero.

2. **Eigenvalue Check:**
   The eigenvalues of any triangular matrix are simply its diagonal entries $\lambda_1 = 2$, $\lambda_2 = -3$, $\lambda_3 = 7$.
   Since the determinant is the product of all eigenvalues:
   $$
   \det T = \lambda_1 \lambda_2 \lambda_3 = 2 \times (-3) \times 7 = -42 \quad \checkmark$

