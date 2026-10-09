# Exercise 10. Detecting Dependence

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix}
$$

1. Without carrying out a full determinant expansion, explain why $\det A = 0$.
2. Identify a specific linear dependence between the rows.
3. Connect this linear dependence with the non-invertibility of matrix $A$.

---

## 2. Theoretical Background and Concepts

### Linear Dependence and Determinants
A set of vectors $\{v_1, \dots, v_n\}$ is **linearly dependent** if there exist scalars $c_1, \dots, c_n$, not all zero, such that:
$$
c_1 v_1 + \cdots + c_n v_n = 0
$$

- **Zero Determinant Criterion:** If the rows (or columns) of an $n \times n$ matrix are linearly dependent, then:
  $$
  \det A = 0
  $$
- **Invertible Matrix Theorem:** For an $n \times n$ matrix $A$, the following statements are equivalent:
  1. $A$ is invertible ($A^{-1}$ exists).
  2. $\det A \neq 0$.
  3. The rows (and columns) of $A$ are linearly independent.
  4. $\operatorname{rank}(A) = n$.
  5. The null space of $A$ is trivial: $\ker(A) = \{0\}$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Identifying the Row Dependence

Inspect the rows of matrix $A$:
$$
R_1 = \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
$$
$$
R_2 = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix}
$$
$$
R_3 = \begin{pmatrix} 0 & 1 & 5 \end{pmatrix}
$$

Notice that the second row is an exact scalar multiple of the first row:
$$
R_2 = 2 R_1 \iff 2 R_1 - R_2 + 0 R_3 = \begin{pmatrix} 0 & 0 & 0 \end{pmatrix}
$$
This establishes that rows $R_1, R_2, R_3$ are **linearly dependent**.

---

### 3.2. Why $\det A = 0$ Without Full Expansion

Apply the elementary row operation $R_2 \leftarrow R_2 - 2 R_1$. 
Since row replacement does not change the determinant:
$$
\det A = \det \begin{pmatrix} 1 & 2 & 3 \\ 2 - 2(1) & 4 - 2(2) & 6 - 2(3) \\ 0 & 1 & 5 \end{pmatrix} = \det \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 1 & 5 \end{pmatrix}
$$
Expanding along the second row (which consists entirely of zeros):
$$
\det A = 0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0
$$

$$
\boxed{\det A = 0}
$$

---

### 3.3. Connection with Non-Invertibility

1. **Rank Defect:**
   Since $R_2$ adds no new dimension beyond $R_1$, the row space $\operatorname{span}(R_1, R_2, R_3) = \operatorname{span}(R_1, R_3)$ has dimension at most $2$. Therefore:
   $$
   \operatorname{rank}(A) \le 2 < 3
   $$
2. **Non-Trivial Kernel (Loss of Injectivity):**
   Because the columns are also linearly dependent, there exist non-zero vectors $x \neq 0$ such that $Ax = 0$. For instance, notice columns $c_1, c_2, c_3$:
   $$
   c_1 = \begin{pmatrix} 1 \\ 2 \\ 0 \end{pmatrix}, \quad c_2 = \begin{pmatrix} 2 \\ 4 \\ 1 \end{pmatrix}, \quad c_3 = \begin{pmatrix} 3 \\ 6 \\ 5 \end{pmatrix} \implies 7 c_1 - 5 c_2 + c_3 = 0
   $$
   Thus $v = \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix}$ satisfies $Av = 0$.
3. **Conclusion:**
   Because $A$ collapses 3-dimensional space onto a 2-dimensional plane, different input vectors are mapped to the same output. Such a transformation cannot be reversed; hence, **matrix $A$ is not invertible**.

---

## 4. Verification and Consistency Checks

1. **Direct Formula Expansion Verification:**
   Using Sarrus' rule:
   - Main diagonals: $(1 \cdot 4 \cdot 5) + (2 \cdot 6 \cdot 0) + (3 \cdot 2 \cdot 1) = 20 + 0 + 6 = 26$.
   - Anti-diagonals: $(0 \cdot 4 \cdot 3) + (1 \cdot 6 \cdot 1) + (5 \cdot 2 \cdot 2) = 0 + 6 + 20 = 26$.
   - Difference: $\det A = 26 - 26 = 0 \quad \checkmark$

2. **Null Space Verification:**
   Compute $Av$ for $v = \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix}$:
   $$
   \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix} = \begin{pmatrix} 1(7) + 2(-5) + 3(1) \\ 2(7) + 4(-5) + 6(1) \\ 0(7) + 1(-5) + 5(1) \end{pmatrix} = \begin{pmatrix} 7 - 10 + 3 \\ 14 - 20 + 6 \\ 0 - 5 + 5 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} \quad \checkmark
   $$
