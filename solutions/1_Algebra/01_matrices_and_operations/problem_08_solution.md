# Exercise 8. Row Operations and Their Reversibility

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

Perform, in order:
1. $R_2 \leftarrow R_2 - 2R_1$
2. $R_3 \leftarrow R_3 + R_1$
3. Interchange $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)

Write the resulting matrix after each step. Then, for each of the three operations, state an elementary row operation that reverses it.

---

## 2. Theoretical Background and Concepts

### Elementary Row Operations
There are three types of elementary row operations:
1. **Row addition/replacement:** Adding a scalar multiple of row $j$ to row $i$: $R_i \leftarrow R_i + c R_j$ ($i \neq j$).
2. **Row scaling:** Multiplying a row by a non-zero scalar: $R_i \leftarrow c R_i$ ($c \neq 0$).
3. **Row interchange (swap):** Swapping two rows: $R_i \leftrightarrow R_j$.

### Reversibility
Every elementary row operation is strictly invertible:
- The inverse of $R_i \leftarrow R_i + c R_j$ is $R_i \leftarrow R_i - c R_j$.
- The inverse of $R_i \leftarrow c R_i$ is $R_i \leftarrow \frac{1}{c} R_i$.
- The inverse of $R_i \leftrightarrow R_j$ is $R_i \leftrightarrow R_j$ (self-inverse).

Each elementary row operation corresponds algebraically to multiplying $A$ on the left by an elementary matrix $E$: $A' = EA$. Because elementary matrices are invertible, applying row operations preserves the row space and the solution set of linear systems.

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$
A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}
$$

---

### Step 1: $R_2 \leftarrow R_2 - 2R_1$

Compute new row 2:
$$
R_2 - 2R_1 = \begin{pmatrix} 2 & 4 & 1 \end{pmatrix} - 2 \begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} 2 - 2 & 4 - 4 & 1 - (-2) \end{pmatrix} = \begin{pmatrix} 0 & 0 & 3 \end{pmatrix}
$$

Matrix after Step 1:
$$
\boxed{A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}}
$$

**Reversing operation:**
$$
\boxed{R_2 \leftarrow R_2 + 2R_1}
$$

---

### Step 2: $R_3 \leftarrow R_3 + R_1$

Compute new row 3:
$$
R_3 + R_1 = \begin{pmatrix} -1 & 1 & 3 \end{pmatrix} + \begin{pmatrix} 1 & 2 & -1 \end{pmatrix} = \begin{pmatrix} -1 + 1 & 1 + 2 & 3 + (-1) \end{pmatrix} = \begin{pmatrix} 0 & 3 & 2 \end{pmatrix}
$$

Matrix after Step 2:
$$
\boxed{A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}}
$$

**Reversing operation:**
$$
\boxed{R_3 \leftarrow R_3 - R_1}
$$

---

### Step 3: Interchange $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)

Swap the second and third rows:
$$
\boxed{A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}}
$$

**Reversing operation:**
$$
\boxed{R_2 \leftrightarrow R_3}
$$
(Interchanging the rows again restores their original positions).

---

## 4. Verification and Consistency Checks

1. **Reconstruction Check (Reversing the Steps in Reverse Order):**
   Start from $A_3$ and apply the reverse operations in reverse sequence:
   - Apply $R_2 \leftrightarrow R_3$ to $A_3$:
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix} \xrightarrow{R_2 \leftrightarrow R_3} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} = A_2 \quad \checkmark
     $$
   - Apply $R_3 \leftarrow R_3 - R_1$ to $A_2$:
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} \xrightarrow{R_3 \leftarrow R_3 - R_1} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} = A_1 \quad \checkmark
     $$
   - Apply $R_2 \leftarrow R_2 + 2R_1$ to $A_1$:
     $$
     \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 + 2R_1} \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix} = A \quad \checkmark
     $$
   The original matrix $A$ is precisely recovered.

2. **Form of the Resulting Matrix:**
   Notice that $A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}$ is an **upper triangular matrix** in row echelon form with non-zero pivots $1, 3, 3$.
   Its determinant is the product of the diagonal entries: $1 \times 3 \times 3 = 9$.
   Since row replacement preserves the determinant and row swap negates it:
   $$
   \det(A) = -\det(A_3) = -9
   $$
   Direct expansion of original matrix $A$:
   $$
   \det(A) = 1(12 - 1) - 2(6 - (-1)) - 1(2 - (-4)) = 11 - 2(7) - 1(6) = 11 - 14 - 6 = -9 \quad \checkmark
   $$
