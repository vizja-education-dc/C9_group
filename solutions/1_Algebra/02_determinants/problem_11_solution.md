# Exercise 11. Shortening the Calculation with Row Operations

## 1. Problem Statement

Compute the determinant:
$$
\det A = \det \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}
$$
by first performing elementary row operations to create as many zeros as possible. Explicitly state which operations do not change the determinant.

---

## 2. Theoretical Background and Concepts

### Determinant-Preserving Operations
The elementary row operation of adding a scalar multiple of row $j$ to row $i$ ($R_i \leftarrow R_i + c R_j$, with $i \neq j$) leaves the determinant **strictly invariant**:
$$
\det(A') = \det(A)
$$
By using the pivot $a_{11} = 1$ to create zeros in the first column, and subsequent pivots to eliminate lower entries, the matrix is transformed into an upper triangular matrix $U$ without altering the determinant:
$$
\det A = \det U = \prod_{i=1}^n u_{ii}
$$

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}
$$

---

### Step 1: Eliminate Entries in Column 1 Below the First Pivot

Perform two row operations simultaneously using Row 1:
1. $R_2 \leftarrow R_2 - R_1$
   - **Operation type:** Adding $(-1) \times R_1$ to $R_2$.
   - **Determinant effect:** Unchanged.
   - **New Row 2:** $(1 - 1, 3 - 2, 4 - 3) = (0, 1, 1)$.
2. $R_3 \leftarrow R_3 - R_1$
   - **Operation type:** Adding $(-1) \times R_1$ to $R_3$.
   - **Determinant effect:** Unchanged.
   - **New Row 3:** $(1 - 1, 4 - 2, 6 - 3) = (0, 2, 3)$.

Matrix after Step 1:
$$
A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix}, \qquad \det A = \det A_1
$$

---

### Step 2: Eliminate Entry in Column 2 Below the Second Pivot

Using the pivot in row 2 ($a_{22} = 1$), eliminate the entry in row 3:
- $R_3 \leftarrow R_3 - 2 R_2$
  - **Operation type:** Adding $(-2) \times R_2$ to $R_3$.
  - **Determinant effect:** Unchanged.
  - **New Row 3:** $(0 - 2(0), 2 - 2(1), 3 - 2(1)) = (0, 0, 1)$.

Matrix after Step 2:
$$
A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det A_2
$$

---

### Step 3: Evaluating the Triangular Determinant

Matrix $A_2$ is in upper triangular form with diagonal entries $1, 1, 1$:
$$
\det A_2 = 1 \cdot 1 \cdot 1 = 1
$$

Since all row operations performed were row additions ($R_i \leftarrow R_i + c R_j$), the determinant remained unchanged throughout the entire process:
$$
\boxed{\det A = 1}
$$

---

## 4. Verification and Consistency Checks

1. **Direct Verification via Sarrus' Rule:**
   $$
   \begin{matrix}
   1 & 2 & 3 & 1 & 2 \\
   1 & 3 & 4 & 1 & 3 \\
   1 & 4 & 6 & 1 & 4
   \end{matrix}
   $$
   - **Main Diagonals:**
     $$
     (1 \cdot 3 \cdot 6) + (2 \cdot 4 \cdot 1) + (3 \cdot 1 \cdot 4) = 18 + 8 + 12 = 38
     $$
   - **Anti-Diagonals:**
     $$
     (1 \cdot 3 \cdot 3) + (4 \cdot 4 \cdot 1) + (6 \cdot 1 \cdot 2) = 9 + 16 + 12 = 37
     $$
   - **Determinant:**
     $$
     \det A = 38 - 37 = 1 \quad \checkmark
     $$

2. **Column Operation Invariance Check:**
   Alternatively, perform column operations $C_2 \leftarrow C_2 - 2C_1$ and $C_3 \leftarrow C_3 - 3C_1$:
   $$
   \begin{pmatrix} 1 & 0 & 0 \\ 1 & 1 & 1 \\ 1 & 2 & 3 \end{pmatrix} \implies \det = 1 \cdot (1 \cdot 3 - 1 \cdot 2) = 1(3 - 2) = 1 \quad \checkmark
   $$
