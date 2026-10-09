# Exercise 14. A System of Equations and the Determinant

## 1. Problem Statement

Consider the linear system $Ax = b$, where:
$$
A = \begin{pmatrix} 1 & 2 \\ k & 4 \end{pmatrix}, \qquad k \in \mathbb{R}
$$

1. For which values of the parameter $k$ does the system have a unique solution for every right-hand side vector $b$?
2. For the remaining (exceptional) value of $k$:
   - Provide an example of a right-hand side $b$ for which the system has **infinitely many solutions**.
   - Provide an example of a right-hand side $b$ for which the system has **no solutions**.

---

## 2. Theoretical Background and Concepts

### Rouché–Capelli Theorem and Determinants for Square Systems
For a square system of linear equations $Ax = b$ with $A \in \mathbb{R}^{n \times n}$:
- **Case 1 ($\det A \neq 0$):** Matrix $A$ is invertible ($A^{-1}$ exists). The system has a **unique solution** for every vector $b \in \mathbb{R}^n$, given explicitly by:
  $$
  x = A^{-1}b
  $$
- **Case 2 ($\det A = 0$):** Matrix $A$ is singular. The system cannot have a unique solution. By the Rouché–Capelli theorem:
  - If $b \in \operatorname{col}(A)$ (the right-hand side lies in the column space of $A$), the system is consistent and possesses **infinitely many solutions** with at least one free parameter.
  - If $b \notin \operatorname{col}(A)$, the system is inconsistent and possesses **no solutions**.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Condition for a Unique Solution

Compute the determinant of coefficient matrix $A$:
$$
\det A = \begin{vmatrix} 1 & 2 \\ k & 4 \end{vmatrix} = (1)(4) - (2)(k) = 4 - 2k
$$

The system has a unique solution for every $b$ if and only if $\det A \neq 0$:
$$
4 - 2k \neq 0 \iff 2k \neq 4 \iff k \neq 2
$$

$$
\boxed{k \in \mathbb{R} \setminus \{2\} \quad (k \neq 2)}
$$

---

### 3.2. Analysis of the Exceptional Case $k = 2$

When $k = 2$, the matrix is:
$$
A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix}
$$
The system $Ax = b$ corresponds to the two scalar equations:
$$
\begin{cases}
x_1 + 2x_2 = b_1 \\
2x_1 + 4x_2 = b_2
\end{cases}
$$
Notice that the left-hand side of the second equation is exactly twice the left-hand side of the first equation:
$$
2(x_1 + 2x_2) = 2x_1 + 4x_2
$$

---

### 3.3. Example with Infinitely Many Solutions

For the system to be consistent, the right-hand sides must satisfy the exact same linear relation $b_2 = 2b_1$.

- **Choose:**
  $$
  \boxed{b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}}
  $$
- **System:**
  $$
  \begin{cases}
  x_1 + 2x_2 = 1 \\
  2x_1 + 4x_2 = 2
  \end{cases}
  $$
- **Solution:**
  Multiplying the first equation by $2$ produces the second equation; thus, the second equation provides no new information.
  Express $x_1$ in terms of free variable $x_2 = t \in \mathbb{R}$:
  $$
  x_1 = 1 - 2t
  $$
  General solution set:
  $$
  x = \begin{pmatrix} 1 - 2t \\ t \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -2 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}
  $$
  There are **infinitely many solutions**.

---

### 3.4. Example with No Solution

For the system to be inconsistent, choose a right-hand side where $b_2 \neq 2b_1$.

- **Choose:**
  $$
  \boxed{b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}}
  $$
- **System:**
  $$
  \begin{cases}
  x_1 + 2x_2 = 1 \\
  2x_1 + 4x_2 = 3
  \end{cases}
  $$
- **Contradiction:**
  Multiply the first equation by $2$:
  $$
  2x_1 + 4x_2 = 2(1) = 2
  $$
  Comparing with the second equation yields:
  $$
  2 = 3
  $$
  This is a mathematical contradiction ($0 = 1$). Therefore, there is **no solution**.

---

## 4. Verification and Consistency Checks

1. **Rank Comparison (Rouché–Capelli):**
   - For $k = 2$ and $b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$:
     $$
     [A \mid b] = \begin{pmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \end{pmatrix} \xrightarrow{R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 1 \\ 0 & 0 & 0 \end{pmatrix}
     $$
     $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 1 < 2$ (number of unknowns). By Rouché–Capelli, the system is consistent with $2 - 1 = 1$ degree of freedom (infinitely many solutions). $\checkmark$

   - For $k = 2$ and $b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$:
     $$
     [A \mid b] = \begin{pmatrix} 1 & 2 & 1 \\ 2 & 4 & 3 \end{pmatrix} \xrightarrow{R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 1 \\ 0 & 0 & 1 \end{pmatrix}
     $$
     $\operatorname{rank}(A) = 1 \neq \operatorname{rank}([A \mid b]) = 2$. By Rouché–Capelli, the system is inconsistent (no solutions). $\checkmark$
