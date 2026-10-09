# Exercise 1. Matrix Size and Entries

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & 5 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & 1 \end{pmatrix}
$$

1. State the sizes (dimensions) of matrices $A$ and $B$.
2. Read off the specific entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

---

## 2. Theoretical Background and Concepts

### Matrix Dimensions
A matrix with $m$ rows and $n$ columns is of size $m \times n$ (or dimension $m \times n$). When specifying the dimension $\dim(M) = m \times n$, the number of horizontal rows is always written first, followed by the number of vertical columns.

### Index Notation
In standard mathematical notation, the entry in the $i$-th row and $j$-th column of matrix $M$ is denoted $m_{ij}$:
- $i \in \{1, \dots, m\}$ denotes the row index.
- $j \in \{1, \dots, n\}$ denotes the column index.

### Row and Column Vectors
- The $i$-th row vector of an $m \times n$ matrix is a $1 \times n$ row vector: $(m_{i1}, m_{i2}, \dots, m_{in})$.
- The $j$-th column vector of an $m \times n$ matrix is an $m \times 1$ column vector: $\begin{pmatrix} m_{1j} \\ m_{2j} \\ \vdots \\ m_{mj} \end{pmatrix}$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Matrix Sizes

- Matrix $A$ has 2 horizontal rows and 3 vertical columns:
  $$
  \boxed{\dim(A) = 2 \times 3}
  $$

- Matrix $B$ has 3 horizontal rows and 2 vertical columns:
  $$
  \boxed{\dim(B) = 3 \times 2}
  $$

---

### 3.2. Matrix Entries

- $a_{12}$ (row 1, column 2 of $A$):
  $$
  \boxed{a_{12} = -1}
  $$

- $a_{23}$ (row 2, column 3 of $A$):
  $$
  \boxed{a_{23} = 5}
  $$

- $b_{21}$ (row 2, column 1 of $B$):
  $$
  \boxed{b_{21} = -2}
  $$

- $b_{32}$ (row 3, column 2 of $B$):
  $$
  \boxed{b_{32} = 1}
  $$

---

### 3.3. Row and Column Vectors

- Second row of $A$ ($i = 2$):
  $$
  \boxed{\begin{pmatrix} 0 & 4 & 5 \end{pmatrix}}
  $$

- First column of $B$ ($j = 1$):
  $$
  \boxed{\begin{pmatrix} 1 \\ -2 \\ 4 \end{pmatrix}}
  $$

---

## 4. Verification and Consistency Checks

1. **Dimensional Consistency**:
   - Total number of entries in $A$: $2 \times 3 = 6$ entries ($2, -1, 3, 0, 4, 5$). $\checkmark$
   - Total number of entries in $B$: $3 \times 2 = 6$ entries ($1, 0, -2, 3, 4, 1$). $\checkmark$
   - The second row of $A$ has $3$ entries, matching the number of columns in $A$. $\checkmark$
   - The first column of $B$ has $3$ entries, matching the number of rows in $B$. $\checkmark$

2. **Index Boundaries**:
   - For $A \in \mathbb{R}^{2 \times 3}$, valid indices are $1 \le i \le 2$ and $1 \le j \le 3$. Both $a_{12}$ and $a_{23}$ lie strictly within valid bounds. $\checkmark$
   - For $B \in \mathbb{R}^{3 \times 2}$, valid indices are $1 \le i \le 3$ and $1 \le j \le 2$. Both $b_{21}$ and $b_{32}$ lie strictly within valid bounds. $\checkmark$
