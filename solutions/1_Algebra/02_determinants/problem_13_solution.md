# Exercise 13. Determinant by Elimination

## 1. Problem Statement

Compute the determinant of the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}
$$
using Gaussian elimination to reduce the matrix to upper triangular form. Carefully record the effect of every row operation on the value of the determinant.

---

## 2. Theoretical Background and Concepts

### Gaussian Elimination and Determinant Invariance
During Gaussian elimination, three types of row operations may be used:
1. **Row addition ($R_i \leftarrow R_i + c R_j$, $i \neq j$):** Leaves the determinant **unchanged** ($\text{factor} = 1$).
2. **Row swap ($R_i \leftrightarrow R_j$):** Multiplies the determinant by **$-1$**.
3. **Row scaling ($R_i \leftarrow c R_i$, $c \neq 0$):** Multiplies the determinant by **$c$**.

Once the matrix is in upper triangular form $U$, its determinant is the product of its main diagonal entries:
$$
\det U = \prod_{i=1}^n u_{ii}
$$
Accounting for all factors introduced along the way:
$$
\det A = \frac{1}{\prod \text{factors}} \det U
$$

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}
$$

---

### Step 1: Eliminate Entries in Column 1 Below the First Pivot ($a_{11} = 1$)

1. **Operation: $R_2 \leftarrow R_2 - 2R_1$**
   - **Type:** Row replacement (add $-2$ times row 1 to row 2).
   - **Effect on Determinant:** Unchanged ($\det A = \det A_1'$).
   - **Calculation:**
     $$
     \begin{pmatrix} 2 & 5 & 7 \end{pmatrix} - 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 5 - 4 & 7 - 6 \end{pmatrix} = \begin{pmatrix} 0 & 1 & 1 \end{pmatrix}
     $$

2. **Operation: $R_3 \leftarrow R_3 - R_1$**
   - **Type:** Row replacement (add $-1$ times row 1 to row 3).
   - **Effect on Determinant:** Unchanged ($\det A_1' = \det A_1$).
   - **Calculation:**
     $$
     \begin{pmatrix} 1 & 0 & 2 \end{pmatrix} - \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 1 - 1 & 0 - 2 & 2 - 3 \end{pmatrix} = \begin{pmatrix} 0 & -2 & -1 \end{pmatrix}
     $$

Matrix after Step 1:
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & -2 & -1 \end{pmatrix}, \qquad \det A = \det A_1
$$

---

### Step 2: Eliminate Entry in Column 2 Below the Second Pivot ($a_{22} = 1$)

- **Operation: $R_3 \leftarrow R_3 + 2R_2$**
  - **Type:** Row replacement (add $2$ times row 2 to row 3).
  - **Effect on Determinant:** Unchanged ($\det A_1 = \det A_2$).
  - **Calculation:**
    $$
    \begin{pmatrix} 0 & -2 & -1 \end{pmatrix} + 2 \begin{pmatrix} 0 & 1 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -2 + 2 & -1 + 2 \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \end{pmatrix}
    $$

Matrix after Step 2:
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det A_2
$$

---

### Step 3: Computing the Determinant of Triangular Matrix $A_2$

Matrix $A_2$ is in upper triangular form with diagonal entries $u_{11} = 1$, $u_{22} = 1$, $u_{33} = 1$:
$$
\det A_2 = u_{11} \cdot u_{22} \cdot u_{33} = 1 \cdot 1 \cdot 1 = 1
$$

Since every operation performed was a determinant-preserving row addition:
$$
\boxed{\det A = 1}
$$

---

## 4. Verification and Consistency Checks

1. **Laplace Expansion Along Row 3:**
   Expanding along row 3 of the original matrix $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}$:
   $$
   \det A = 1 \cdot \begin{vmatrix} 2 & 3 \\ 5 & 7 \end{vmatrix} - 0 \cdot C_{32} + 2 \cdot \begin{vmatrix} 1 & 2 \\ 2 & 5 \end{vmatrix}
   $$
   Evaluate minors:
   - $\begin{vmatrix} 2 & 3 \\ 5 & 7 \end{vmatrix} = (2)(7) - (3)(5) = 14 - 15 = -1$
   - $\begin{vmatrix} 1 & 2 \\ 2 & 5 \end{vmatrix} = (1)(5) - (2)(2) = 5 - 4 = 1$
   $$
   \det A = 1(-1) + 2(1) = -1 + 2 = 1 \quad \checkmark
   $$

2. **Sarrus' Rule Verification:**
   - Main diagonals: $(1 \cdot 5 \cdot 2) + (2 \cdot 7 \cdot 1) + (3 \cdot 2 \cdot 0) = 10 + 14 + 0 = 24$.
   - Anti-diagonals: $(1 \cdot 5 \cdot 3) + (0 \cdot 7 \cdot 1) + (2 \cdot 2 \cdot 2) = 15 + 0 + 8 = 23$.
   - $\det A = 24 - 23 = 1 \quad \checkmark$
