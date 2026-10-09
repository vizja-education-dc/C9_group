# Exercise 2. Determinant of a 3×3 Matrix

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 & 1 & 5 \end{pmatrix}
$$

1. Compute $\det A$ using Sarrus' rule.
2. Perform a verification check using another property or method (such as Laplace expansion along the first column).

---

## 2. Theoretical Background and Concepts

### Sarrus' Rule (for $3 \times 3$ matrices only)
For a general $3 \times 3$ matrix:
$$
A = \begin{pmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{pmatrix}
$$
Sarrus' rule computes the determinant by adding the products of the three main diagonals and subtracting the products of the three anti-diagonals:
$$
\det A = (a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32}) - (a_{13}a_{22}a_{31} + a_{11}a_{23}a_{32} + a_{12}a_{21}a_{33})
$$

### Laplace (Cofactor) Expansion
The determinant can also be computed by expanding along any row or column. Expanding along column $j$:
$$
\det A = \sum_{i=1}^n (-1)^{i+j} a_{ij} \det(M_{ij})
$$
where $M_{ij}$ is the $(n-1) \times (n-1)$ submatrix obtained by deleting row $i$ and column $j$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computation via Sarrus' Rule

Write the matrix entries and repeat the first two columns to visualize the diagonals:
$$
\begin{matrix}
1 & 2 & -1 & 1 & 2 \\
0 & 3 & 4 & 0 & 3 \\
2 & 1 & 5 & 2 & 1
\end{matrix}
$$

**Main Diagonals (down-right, with positive sign):**
1. First diagonal: $1 \cdot 3 \cdot 5 = 15$
2. Second diagonal: $2 \cdot 4 \cdot 2 = 16$
3. Third diagonal: $(-1) \cdot 0 \cdot 1 = 0$
$$
\text{Sum of main diagonals} = 15 + 16 + 0 = 31
$$

**Anti-Diagonals (up-right, with negative sign):**
1. First anti-diagonal: $2 \cdot 3 \cdot (-1) = -6$
2. Second anti-diagonal: $1 \cdot 4 \cdot 1 = 4$
3. Third anti-diagonal: $5 \cdot 0 \cdot 2 = 0$
$$
\text{Sum of anti-diagonals} = (-6) + 4 + 0 = -2
$$

**Compute the Determinant:**
$$
\det A = 31 - (-2) = 31 + 2 = 33
$$

$$
\boxed{\det A = 33}
$$

---

## 4. Verification and Consistency Checks

### Laplace Expansion Along Column 1
Because column 1 contains a zero ($a_{21} = 0$), expanding along this column simplifies the evaluation and provides an independent verification:

$$
\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}
$$
$$
\det A = 1 \cdot (-1)^{1+1} \begin{vmatrix} 3 & 4 \\ 1 & 5 \end{vmatrix} + 0 + 2 \cdot (-1)^{3+1} \begin{vmatrix} 2 & -1 \\ 3 & 4 \end{vmatrix}
$$

Evaluate the two $2 \times 2$ minors:
1. $\begin{vmatrix} 3 & 4 \\ 1 & 5 \end{vmatrix} = (3)(5) - (4)(1) = 15 - 4 = 11$
2. $\begin{vmatrix} 2 & -1 \\ 3 & 4 \end{vmatrix} = (2)(4) - (-1)(3) = 8 - (-3) = 8 + 3 = 11$

Substitute back:
$$
\det A = 1 \cdot (11) + 2 \cdot (11) = 11 + 22 = 33 \quad \checkmark
$$

Both Sarrus' rule and Laplace expansion yield exactly $33$, verifying the calculation.

