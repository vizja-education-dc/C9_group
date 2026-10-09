# Exercise 2. Addition and Scalar Multiplication

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \qquad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}
$$

1. Compute $A + B$.
2. Compute $A - B$.
3. Compute $3A - 2B$.
4. Explain why matrix addition is possible only for matrices of the same size.

---

## 2. Theoretical Background and Concepts

### Matrix Addition and Subtraction
Let $A = (a_{ij})$ and $B = (b_{ij})$ be two matrices of the same size $m \times n$. 
The sum $A + B$ is an $m \times n$ matrix whose entries are defined element-wise:
$$
(A + B)_{ij} = a_{ij} + b_{ij} \quad \text{for all } 1 \le i \le m, \, 1 \le j \le n.
$$
Similarly, the difference $A - B$ is defined element-wise:
$$
(A - B)_{ij} = a_{ij} - b_{ij} \quad \text{for all } 1 \le i \le m, \, 1 \le j \le n.
$$

### Scalar Multiplication
Given a scalar $c \in \mathbb{R}$ and an $m \times n$ matrix $A = (a_{ij})$, the scalar product $cA$ is an $m \times n$ matrix whose entries are:
$$
(cA)_{ij} = c \cdot a_{ij} \quad \text{for all } 1 \le i \le m, \, 1 \le j \le n.
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computation of $A + B$

Both matrices $A$ and $B$ have size $2 \times 2$, so their sum is well-defined:
$$
A + B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}
$$

Add corresponding entries:
- Row 1, Column 1: $1 + 4 = 5$
- Row 1, Column 2: $2 + (-2) = 0$
- Row 2, Column 1: $-1 + 0 = -1$
- Row 2, Column 2: $3 + 5 = 8$

$$
\boxed{A + B = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}}
$$

---

### 3.2. Computation of $A - B$

Subtract corresponding entries:
$$
A - B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}
$$

- Row 1, Column 1: $1 - 4 = -3$
- Row 1, Column 2: $2 - (-2) = 2 + 2 = 4$
- Row 2, Column 1: $-1 - 0 = -1$
- Row 2, Column 2: $3 - 5 = -2$

$$
\boxed{A - B = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}}
$$

---

### 3.3. Computation of $3A - 2B$

First, compute the scalar multiples $3A$ and $2B$:

$$
3A = 3 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 3 \cdot 1 & 3 \cdot 2 \\ 3 \cdot (-1) & 3 \cdot 3 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}
$$

$$
2B = 2 \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 2 \cdot 4 & 2 \cdot (-2) \\ 2 \cdot 0 & 2 \cdot 5 \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}
$$

Now subtract $2B$ from $3A$:
$$
3A - 2B = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} - \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}
$$

- Row 1, Column 1: $3 - 8 = -5$
- Row 1, Column 2: $6 - (-4) = 6 + 4 = 10$
- Row 2, Column 1: $-3 - 0 = -3$
- Row 2, Column 2: $9 - 10 = -1$

$$
\boxed{3A - 2B = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}}
$$

---

### 3.4. Why Matrix Addition Requires Identical Dimensions

Matrix addition is defined strictly as an **element-wise (entry-by-entry)** operation:
$$
(A + B)_{ij} = a_{ij} + b_{ij}
$$

For this binary operation to be defined on every component:
1. Every position $(i, j)$ in $A$ must correspond to a uniquely defined position $(i, j)$ in $B$.
2. If two matrices have different dimensions (for example, if matrix $A$ has dimensions $m_1 \times n_1$ and matrix $B$ has dimensions $m_2 \times n_2$ with $m_1 \neq m_2$ or $n_1 \neq n_2$), there will be entries in one matrix that have no corresponding counterpart in the other matrix.

Therefore, the operation cannot be performed because addition in the underlying scalar field (here $\mathbb{R}$) is a binary operation requiring exactly two operands for each position $(i, j)$.

---

## 4. Verification and Consistency Checks

1. **Verification of $A + B$:**
   $$
   (A + B) - B = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 5 - 4 & 0 - (-2) \\ -1 - 0 & 8 - 5 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A \quad \checkmark
   $$

2. **Verification of $A - B$:**
   $$
   (A - B) + B = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} -3 + 4 & 4 + (-2) \\ -1 + 0 & -2 + 5 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A \quad \checkmark
   $$

3. **Verification of $3A - 2B$:**
   $$
   (3A - 2B) + 2B = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix} + \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix} = \begin{pmatrix} -5 + 8 & 10 + (-4) \\ -3 + 0 & -1 + 10 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} = 3A \quad \checkmark
   $$
   Dividing each entry by $3$ recovers $A$:
   $$
   \frac{1}{3}(3A) = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A \quad \checkmark
   $$

