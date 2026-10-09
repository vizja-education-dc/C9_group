# Exercise 7. Using Properties Instead of Recomputing

## 1. Problem Statement

Let $A$ be a $3 \times 3$ matrix with:
$$
\det A = -4
$$
Using the algebraic properties of determinants, compute:
$$
\det(2A), \qquad \det(A^T), \qquad \det(A^2), \qquad \det(-A)
$$
Justify each result by stating the corresponding determinant property.

---

## 2. Theoretical Background and Concepts

For any $n \times n$ matrices $M, N$ and scalar $c \in \mathbb{R}$:

1. **Scalar Multiplication Property:**
   Multiplying an entire $n \times n$ matrix by a scalar $c$ multiplies each of its $n$ rows by $c$. By multilinearity:
   $$
   \det(cM) = c^n \det(M)
   $$

2. **Transposition Invariance:**
   Transposing a matrix does not change its determinant:
   $$
   \det(M^T) = \det(M)
   $$

3. **Multiplicativity Property:**
   The determinant of a product is the product of determinants:
   $$
   \det(MN) = \det(M) \det(N) \implies \det(M^k) = (\det M)^k
   $$

4. **Negation Property:**
   Negation is scalar multiplication by $c = -1$:
   $$
   \det(-M) = \det((-1)M) = (-1)^n \det(M)
   $$

---

## 3. Detailed Step-by-Step Solution

Here, the dimension is $n = 3$, and $\det A = -4$.

### 3.1. Computing $\det(2A)$
Applying the scalar multiplication property with $c = 2$ and $n = 3$:
$$
\det(2A) = 2^3 \det(A) = 8 \cdot (-4) = -32
$$

$$
\boxed{\det(2A) = -32}
$$

---

### 3.2. Computing $\det(A^T)$
Applying transposition invariance:
$$
\det(A^T) = \det(A) = -4
$$

$$
\boxed{\det(A^T) = -4}
$$

---

### 3.3. Computing $\det(A^2)$
Applying the multiplicative property of determinants with $k = 2$:
$$
\det(A^2) = (\det A)^2 = (-4)^2 = 16
$$

$$
\boxed{\det(A^2) = 16}
$$

---

### 3.4. Computing $\det(-A)$
Applying the scalar multiplication property with $c = -1$ and $n = 3$:
$$
\det(-A) = (-1)^3 \det(A) = -1 \cdot (-4) = 4
$$

$$
\boxed{\det(-A) = 4}
$$

---

## 4. Verification and Consistency Checks

1. **Concrete Diagonal Matrix Test:**
   Construct a simple diagonal $3 \times 3$ matrix with determinant $-4$:
   $$
   A_0 = \begin{pmatrix} -4 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det A_0 = (-4)(1)(1) = -4
   $$
   - **Check $2A_0$:**
     $$
     2A_0 = \begin{pmatrix} -8 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} \implies \det(2A_0) = (-8)(2)(2) = -32 \quad \checkmark
     $$
   - **Check $A_0^T$:**
     $$
     A_0^T = A_0 \implies \det(A_0^T) = -4 \quad \checkmark
     $$
   - **Check $A_0^2$:**
     $$
     A_0^2 = \begin{pmatrix} 16 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det(A_0^2) = 16 \quad \checkmark
     $$
   - **Check $-A_0$:**
     $$
     -A_0 = \begin{pmatrix} 4 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & -1 \end{pmatrix} \implies \det(-A_0) = (4)(-1)(-1) = 4 \quad \checkmark
     $$
   All properties hold consistently.

