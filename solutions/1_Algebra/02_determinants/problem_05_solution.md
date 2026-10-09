# Exercise 5. Row Operations

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}
$$

Find $\det A$ by simplifying the matrix into upper triangular form using elementary row operations. At each step, record explicitly whether and how the operation affects the value of the determinant.

---

## 2. Theoretical Background and Concepts

### Effect of Elementary Row Operations on Determinants
1. **Row Replacement ($R_i \leftarrow R_i + c R_j$, $i \neq j$):**
   Adding a scalar multiple of another row to row $i$ **does not change the determinant**:
   $$
   \det(A') = \det(A)
   $$
2. **Row Swap ($R_i \leftrightarrow R_j$):**
   Interchanging two rows **negates the determinant**:
   $$
   \det(A') = -\det(A)
   $$
3. **Row Scaling ($R_i \leftarrow c R_i$, $c \neq 0$):**
   Multiplying a row by a scalar $c$ **multiplies the determinant by $c$**:
   $$
   \det(A') = c \det(A) \iff \det(A) = \frac{1}{c} \det(A')
   $$

By applying row replacements to reach upper triangular form, the determinant of the original matrix is simply equal to the product of the diagonal elements of the resulting matrix.

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}
$$

---

### Step 1: $R_2 \leftarrow R_2 - 2R_1$
- **Operation:** Add $-2$ times row 1 to row 2.
- **Effect on Determinant:** Determinant is unchanged ($\det A = \det A_1$).
- **Computation:**
  $$
  \begin{pmatrix} 2 & 1 & 0 \end{pmatrix} - 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 1 - 4 & 0 - 6 \end{pmatrix} = \begin{pmatrix} 0 & -3 & -6 \end{pmatrix}
  $$
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ -1 & 4 & 2 \end{pmatrix}, \qquad \det A = \det A_1
$$

---

### Step 2: $R_3 \leftarrow R_3 + R_1$
- **Operation:** Add $1$ times row 1 to row 3.
- **Effect on Determinant:** Determinant is unchanged ($\det A_1 = \det A_2$).
- **Computation:**
  $$
  \begin{pmatrix} -1 & 4 & 2 \end{pmatrix} + \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} -1 + 1 & 4 + 2 & 2 + 3 \end{pmatrix} = \begin{pmatrix} 0 & 6 & 5 \end{pmatrix}
  $$
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 6 & 5 \end{pmatrix}, \qquad \det A = \det A_2
$$

---

### Step 3: $R_3 \leftarrow R_3 + 2R_2$
- **Operation:** Add $2$ times row 2 to row 3.
- **Effect on Determinant:** Determinant is unchanged ($\det A_2 = \det A_3$).
- **Computation:**
  $$
  \begin{pmatrix} 0 & 6 & 5 \end{pmatrix} + 2 \begin{pmatrix} 0 & -3 & -6 \end{pmatrix} = \begin{pmatrix} 0 & 6 - 6 & 5 - 12 \end{pmatrix} = \begin{pmatrix} 0 & 0 & -7 \end{pmatrix}
  $$
$$
A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 0 & -7 \end{pmatrix}, \qquad \det A = \det A_3
$$

---

### Step 4: Computing the Determinant of Triangular Matrix $A_3$

Matrix $A_3$ is in upper triangular form. Its determinant is the product of its diagonal elements:
$$
\det A_3 = (1) \cdot (-3) \cdot (-7) = 21
$$

Since every row operation performed was a row replacement ($R_i \leftarrow R_i + c R_j$), none of them altered the determinant:
$$
\boxed{\det A = \det A_3 = 21}
$$

---

## 4. Verification and Consistency Checks

### Direct Sarrus' Rule Verification on Matrix $A$:
$$
\begin{matrix}
1 & 2 & 3 & 1 & 2 \\
2 & 1 & 0 & 2 & 1 \\
-1 & 4 & 2 & -1 & 4
\end{matrix}
$$

- **Main Diagonals:**
  $$
  (1 \cdot 1 \cdot 2) + (2 \cdot 0 \cdot (-1)) + (3 \cdot 2 \cdot 4) = 2 + 0 + 24 = 26
  $$
- **Anti-Diagonals:**
  $$
  ((-1) \cdot 1 \cdot 3) + (4 \cdot 0 \cdot 1) + (2 \cdot 2 \cdot 2) = -3 + 0 + 8 = 5
  $$
- **Determinant:**
  $$
  \det A = 26 - 5 = 21 \quad \checkmark
  $$

The result obtained via row reduction matches the result from direct formula expansion.

