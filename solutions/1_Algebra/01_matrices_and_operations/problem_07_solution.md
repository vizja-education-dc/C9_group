# Exercise 7. Identity Matrix, Zero Matrix, and Powers

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

1. Compute $AI$ and $IA$.
2. Compute $A + 0$.
3. Compute $A^2$ and $A^3$.
4. Explain the algebraic roles of the identity matrix $I$ and the zero matrix $0$.
5. Describe the pattern observed in successive powers of $A$.

---

## 2. Theoretical Background and Concepts

### Identity Matrix ($I$)
The identity matrix of size $n \times n$ (here $n = 2$, $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$) is the **multiplicative neutral element** in the ring of square matrices $M_n(\mathbb{R})$:
$$
MI = IM = M \quad \text{for any } M \in M_n(\mathbb{R})
$$

### Zero Matrix ($0$)
The zero matrix of size $n \times n$ ($0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$) is the **additive neutral element**:
$$
M + 0 = 0 + M = M
$$
and acts as an absorbing element under multiplication: $M \cdot 0 = 0 \cdot M = 0$.

### Powers of an Upper Triangular Matrix
A matrix of the form $A = \begin{pmatrix} \lambda & 1 \\ 0 & \lambda \end{pmatrix}$ (a Jordan block of size $2$) can be split into:
$$
A = \lambda I + N, \qquad \text{where } N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$
Because the scalar matrix $\lambda I$ commutes with any matrix ($(\lambda I)N = N(\lambda I)$), the binomial theorem applies:
$$
A^k = (\lambda I + N)^k = \sum_{j=0}^k \binom{k}{j} (\lambda I)^{k-j} N^j
$$
Since $N^2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$, all terms for $j \ge 2$ vanish, yielding:
$$
A^k = \lambda^k I + k \lambda^{k-1} N = \begin{pmatrix} \lambda^k & k \lambda^{k-1} \\ 0 & \lambda^k \end{pmatrix}
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $AI$ and $IA$
Let $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$:

$$
AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} (2)(1) + (1)(0) & (2)(0) + (1)(1) \\ (0)(1) + (2)(0) & (0)(0) + (2)(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
$$

$$
IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} (1)(2) + (0)(0) & (1)(1) + (0)(2) \\ (0)(2) + (1)(0) & (0)(1) + (1)(2) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
$$

$$
\boxed{AI = IA = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A}
$$

---

### 3.2. Computing $A + 0$
Let $0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$:

$$
A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2+0 & 1+0 \\ 0+0 & 2+0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

$$
\boxed{A + 0 = A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}}
$$

---

### 3.3. Computing $A^2$ and $A^3$

**Computing $A^2 = A \cdot A$:**
$$
A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} (2)(2) + (1)(0) & (2)(1) + (1)(2) \\ (0)(2) + (2)(0) & (0)(1) + (2)(2) \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}
$$

$$
\boxed{A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}}
$$

**Computing $A^3 = A^2 \cdot A$:**
$$
A^3 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} (4)(2) + (4)(0) & (4)(1) + (4)(2) \\ (0)(2) + (4)(0) & (0)(1) + (4)(2) \end{pmatrix} = \begin{pmatrix} 8 & 4 + 8 \\ 0 & 8 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}
$$

$$
\boxed{A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}}
$$

---

### 3.4. Role of Matrices $I$ and $0$

1. **Identity Matrix $I$**: Serves as the **neutral element of matrix multiplication**, analogous to the number $1$ in real arithmetic. It satisfies $AI = IA = A$ for any compatible matrix $A$, preserving both the dimensions and values of the operand.
2. **Zero Matrix $0$**: Serves as the **neutral element of matrix addition**, analogous to the number $0$ in real arithmetic, satisfying $A + 0 = 0 + A = A$.

---

### 3.5. Pattern in Successive Powers of $A$

Examining the successive powers:
- $A^1 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2^1 & 1 \cdot 2^0 \\ 0 & 2^1 \end{pmatrix}$
- $A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 2^2 & 2 \cdot 2^1 \\ 0 & 2^2 \end{pmatrix}$
- $A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix} = \begin{pmatrix} 2^3 & 3 \cdot 2^2 \\ 0 & 2^3 \end{pmatrix}$

**Pattern / General Formula:**
For any integer $k \ge 1$:
$$
\boxed{A^k = \begin{pmatrix} 2^k & k \cdot 2^{k-1} \\ 0 & 2^k \end{pmatrix}}
$$
- The diagonal entries double with each power ($2^k$).
- The bottom-left entry remains zero ($0$).
- The top-right entry grows as $k \cdot 2^{k-1}$.

---

## 4. Verification and Consistency Checks

1. **Associativity of Powers Check for $A^3$**:
   Compute $A \cdot A^2$:
   $$
   A \cdot A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} (2)(4) + (1)(0) & (2)(4) + (1)(4) \\ (0)(4) + (2)(0) & (0)(4) + (2)(4) \end{pmatrix} = \begin{pmatrix} 8 & 8 + 4 \\ 0 & 8 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}
   $$
   This matches $A^2 \cdot A = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix} \quad \checkmark$

2. **Determinant Multiplicativity Check**:
   - $\det(A) = 2 \cdot 2 - 1 \cdot 0 = 4$
   - $\det(A^2) = 4 \cdot 4 - 4 \cdot 0 = 16 = (\det(A))^2 \quad \checkmark$
   - $\det(A^3) = 8 \cdot 8 - 12 \cdot 0 = 64 = (\det(A))^3 \quad \checkmark$

