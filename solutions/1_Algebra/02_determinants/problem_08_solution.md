# Exercise 8. Determinant of a Product

## 1. Problem Statement

Let $A$ and $B$ be square matrices of the same dimension such that:
$$
\det A = 3, \qquad \det B = -5
$$

1. Compute $\det(AB)$.
2. Compute $\det(BA)$.
3. Determine whether $\det(A^{-1}B)$ exists, and if so, compute its value.
4. Explain why $\det(AB) = \det(BA)$ holds even though in general matrix multiplication is non-commutative ($AB \neq BA$).

---

## 2. Theoretical Background and Concepts

### Product Rule for Determinants (Cauchy–Binet Theorem)
For any square matrices $M, N \in M_n(\mathbb{R})$ of identical size:
$$
\det(MN) = \det(M) \det(N)
$$

### Determinant of an Inverse Matrix
If a square matrix $M$ is invertible ($\det M \neq 0$), then $M M^{-1} = I$. Taking determinants of both sides:
$$
\det(M M^{-1}) = \det(M) \det(M^{-1}) = \det(I) = 1
$$
$$
\det(M^{-1}) = \frac{1}{\det(M)}
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $\det(AB)$
Using the multiplicativity of determinants:
$$
\det(AB) = \det(A) \cdot \det(B) = (3) \cdot (-5) = -15
$$

$$
\boxed{\det(AB) = -15}
$$

---

### 3.2. Computing $\det(BA)$
Using the multiplicativity of determinants:
$$
\det(BA) = \det(B) \cdot \det(A) = (-5) \cdot (3) = -15
$$

$$
\boxed{\det(BA) = -15}
$$

---

### 3.3. Existence and Computation of $\det(A^{-1}B)$
- **Existence check:** The inverse $A^{-1}$ exists if and only if $\det A \neq 0$. Since $\det A = 3 \neq 0$, $A$ is invertible and $A^{-1}$ exists.
- **Determinant computation:**
  $$
  \det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}
  $$
  $$
  \det(A^{-1}B) = \det(A^{-1}) \cdot \det(B) = \frac{1}{3} \cdot (-5) = -\frac{5}{3}
  $$

$$
\boxed{\det(A^{-1}B) = -\frac{5}{3}}
$$

---

### 3.4. Why $\det(AB) = \det(BA)$ Even When $AB \neq BA$

1. **Matrix multiplication takes place in $M_n(\mathbb{R})$:**
   In the ring of matrices, multiplication does not commute ($AB \neq BA$ in general). The matrices $AB$ and $BA$ represent different geometric transformations and have different entries.
2. **Determinants take values in the scalar field $\mathbb{R}$:**
   The determinant map $\det: M_n(\mathbb{R}) \to \mathbb{R}$ maps matrices to real numbers.
   Applying the product property converts the matrix product into a scalar product:
   $$
   \det(AB) = \det(A) \cdot \det(B)
   $$
   $$
   \det(BA) = \det(B) \cdot \det(A)
   $$
   Because multiplication of real numbers is strictly commutative:
   $$
   \det(A) \cdot \det(B) = \det(B) \cdot \det(A) \quad \text{for all } \det(A), \det(B) \in \mathbb{R}
   $$
Therefore, although the resulting matrices $AB$ and $BA$ are distinct, they always enclose the same oriented volume distortion factor, making their determinants identical.

---

## 4. Verification and Consistency Checks

1. **Concrete Example Check:**
   Let $A = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix}$ ($\det A = 3$) and $B = \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix}$ ($\det B = -5$).
   - Compute $AB$:
     $$
     AB = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix} = \begin{pmatrix} 3 & 0 \\ 2 & -5 \end{pmatrix} \implies \det(AB) = (3)(-5) - 0 = -15 \quad \checkmark
     $$
   - Compute $BA$:
     $$
     BA = \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3 & 0 \\ 6 & -5 \end{pmatrix} \implies \det(BA) = (3)(-5) - 0 = -15 \quad \checkmark
     $$
   Notice that $AB = \begin{pmatrix} 3 & 0 \\ 2 & -5 \end{pmatrix} \neq \begin{pmatrix} 3 & 0 \\ 6 & -5 \end{pmatrix} = BA$, yet $\det(AB) = \det(BA) = -15$.

2. **Inverse Product Check:**
   $A^{-1} = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix}$.
   $$
   A^{-1}B = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix} = \begin{pmatrix} 1/3 & 0 \\ 2 & -5 \end{pmatrix}
   $$
   $\det(A^{-1}B) = (1/3)(-5) - 0 = -5/3 \quad \checkmark$
