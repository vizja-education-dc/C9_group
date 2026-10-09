# Exercise 1. Determinant of a 2×2 Matrix

## 1. Problem Statement

Compute the determinants of the following matrices:
$$
M_1 = \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}, \qquad M_2 = \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}
$$
Determine which of these matrices is invertible and justify your answer using the calculated determinants.

---

## 2. Theoretical Background and Concepts

### Determinant of a $2 \times 2$ Matrix
For an arbitrary $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the determinant is defined by the formula:
$$
\det(M) = \begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc
$$

### Determinant and Invertibility Criterion
A square matrix $M$ is invertible (nonsingular) if and only if its determinant is non-zero:
$$
M \text{ is invertible} \iff \det(M) \neq 0
$$
- If $\det(M) \neq 0$, the inverse exists and is given by $M^{-1} = \frac{1}{\det(M)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$.
- If $\det(M) = 0$, the rows (and columns) are linearly dependent, the matrix has rank strictly less than its dimension, and no multiplicative inverse exists.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $\det(M_1)$
For $M_1 = \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}$:
$$
\det(M_1) = (3)(4) - (-2)(5) = 12 - (-10) = 12 + 10 = 22
$$

$$
\boxed{\det(M_1) = 22}
$$

---

### 3.2. Computing $\det(M_2)$
For $M_2 = \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}$:
$$
\det(M_2) = (1)(14) - (7)(2) = 14 - 14 = 0
$$

$$
\boxed{\det(M_2) = 0}
$$

---

### 3.3. Invertibility Analysis

- **Matrix $M_1$:** Since $\det(M_1) = 22 \neq 0$, matrix $M_1$ is **invertible**. Its inverse is well-defined:
  $$
  M_1^{-1} = \frac{1}{22} \begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix}
  $$
- **Matrix $M_2$:** Since $\det(M_2) = 0$, matrix $M_2$ is **not invertible** (singular).

$$
\boxed{\text{Only matrix } M_1 \text{ is invertible, because } \det(M_1) \neq 0, \text{ whereas } \det(M_2) = 0.}
$$

---

## 4. Verification and Consistency Checks

1. **Linear Dependence Check for $M_2$:**
   Notice that the second row of $M_2$ is a direct scalar multiple of the first row:
   $$
   R_2 = \begin{pmatrix} 2 & 14 \end{pmatrix} = 2 \begin{pmatrix} 1 & 7 \end{pmatrix} = 2 R_1
   $$
   Since the rows are linearly dependent, the rows span a 1-dimensional subspace (a line) rather than $\mathbb{R}^2$. A matrix whose rows are linearly dependent must have determinant equal to zero. $\checkmark$

2. **Inverse Verification for $M_1$:**
   Multiply $M_1$ by its computed inverse $M_1^{-1} = \frac{1}{22} \begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix}$:
   $$
   M_1 M_1^{-1} = \frac{1}{22} \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix} \begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 12 + 10 & 6 - 6 \\ 20 - 20 & 10 + 12 \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 22 & 0 \\ 0 & 22 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark
   $$

