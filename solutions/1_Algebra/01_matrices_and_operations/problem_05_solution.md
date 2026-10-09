# Exercise 5. Matrix Times Vector

## 1. Problem Statement

Given the matrix $A$ and vector $x$:
$$
A = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}, \qquad x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}
$$

1. Compute $Ax$.
2. Express $Ax$ as a linear combination of the columns of $A$, with coefficients coming from the vector $x$.

---

## 2. Theoretical Background and Concepts

### Matrix-Vector Multiplication: Two Perspectives
There are two complementary, equivalent ways to view matrix-vector multiplication $Ax$:

1. **Row Perspective (Inner Products / Dot Products):**
   Each entry of the resulting vector is the dot product of the corresponding row of $A$ with $x$:
   $$
   (Ax)_i = \sum_{j=1}^n a_{ij} x_j
   $$

2. **Column Perspective (Linear Combination of Columns):**
   If the columns of $A$ are denoted by $a_1, a_2, \ldots, a_n \in \mathbb{R}^m$, then:
   $$
   A = \begin{pmatrix} | & | & & | \\ a_1 & a_2 & \cdots & a_n \\ | & | & & | \end{pmatrix}
   $$
   The product $Ax$ is precisely the **linear combination of the columns of $A$ weighted by the components of $x$**:
   $$
   Ax = x_1 a_1 + x_2 a_2 + \cdots + x_n a_n
   $$

This column perspective is fundamental in linear algebra because it shows that the image (column space) of $A$ consists of all possible linear combinations of the columns of $A$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Standard Computation (Row Perspective)

Evaluating $Ax$ using the rows of $A$:
$$
Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} (2)(4) + (-1)(2) \\ (1)(4) + (3)(2) \end{pmatrix}
$$

- First component: $8 - 2 = 6$
- Second component: $4 + 6 = 10$

$$
\boxed{Ax = \begin{pmatrix} 6 \\ 10 \end{pmatrix}}
$$

---

### 3.2. Column Perspective (Linear Combination)

Identify the column vectors of matrix $A$:
$$
a_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \qquad a_2 = \begin{pmatrix} -1 \\ 3 \end{pmatrix}
$$
and the components of vector $x$:
$$
x_1 = 4, \qquad x_2 = 2
$$

Expressing $Ax$ as a linear combination:
$$
Ax = x_1 a_1 + x_2 a_2 = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}
$$

Evaluating this sum:
$$
4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 4 \cdot 2 \\ 4 \cdot 1 \end{pmatrix} + \begin{pmatrix} 2 \cdot (-1) \\ 2 \cdot 3 \end{pmatrix} = \begin{pmatrix} 8 \\ 4 \end{pmatrix} + \begin{pmatrix} -2 \\ 6 \end{pmatrix} = \begin{pmatrix} 8 + (-2) \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}
$$

$$
\boxed{Ax = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}}
$$

---

## 4. Verification and Consistency Checks

1. **Equivalence of Perspectives**:
   - Row perspective calculation: $\begin{pmatrix} 6 \\ 10 \end{pmatrix}$
   - Column perspective calculation: $\begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$
   Both methods yield the exact same vector $\begin{pmatrix} 6 \\ 10 \end{pmatrix} \quad \checkmark$

2. **Linearity Check**:
   Vector $x$ can be decomposed into canonical basis vectors $e_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ and $e_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$:
   $$
   x = 4 e_1 + 2 e_2
   $$
   By linearity:
   $$
   A(4e_1 + 2e_2) = 4 Ae_1 + 2 Ae_2
   $$
   Since $Ae_1$ is the first column of $A$ and $Ae_2$ is the second column of $A$:
   $$
   4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix} \quad \checkmark
   $$

